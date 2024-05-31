---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Debugging common CLI issues with clusters
{: #ts_clis}
{: troubleshoot}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}

Review the following common reasons for CLI connection issues or command failures.
{: shortdesc}


## Firewall prevents running CLI commands
{: #ts_firewall_clis}


When you run `ibmcloud`, `kubectl`, or `calicoctl` commands from the CLI, they fail.
{: tsSymptoms}


You might have corporate network policies that prevent access from your local system to public endpoints via proxies or firewalls.
{: tsCauses}


[Allow TCP access for the CLI commands to work](/docs/containers?topic=containers-firewall#firewall_bx).
{: tsResolve}

This task requires the [**Administrator** {{site.data.keyword.cloud_notm}} IAM platform access role](/docs/containers?topic=containers-iam-platform-access-roles) for the cluster.



## `kubectl` commands don't work
{: #kubectl_fails}


When you run `kubectl` commands against your cluster, your commands fail with an error message similar to the following.
{: tsSymptoms}

```sh
No resources found.
Error from server (NotAcceptable): unknown (get nodes)
```
{: screen}

```sh
invalid object doesn't have additional properties
```
{: screen}

```sh
error: No Auth Provider found for name "oidc"
```
{: screen}


You have a different version of `kubectl` than your cluster version.
{: tsCauses}

[Kubernetes does not support](https://kubernetes.io/releases/version-skew-policy/){: external} `kubectl` client versions that are 2 or more versions apart from the server version (n +/- 2). If you use a community Kubernetes cluster, you might also have the {{site.data.keyword.redhat_openshift_notm}} version of `kubectl`, which does not work with community Kubernetes clusters.

To check your client `kubectl` version against the cluster server version, run `kubectl version --short`.


[Install the version of the CLI](/docs/containers?topic=containers-cli-install) that matches the version of your cluster.
{: tsResolve}

If you have multiple clusters at different versions or different container platforms such as {{site.data.keyword.redhat_openshift_notm}}, download each `kubectl` version binary file to a separate directory. Then, you can set up an alias in your local command-line interface (CLI) profile to point to the `kubectl` binary file directory that matches the `kubectl` version of the cluster that you want to work with, or you might be able to use a tool such as `brew switch kubernetes-cli <major.minor>`.





## `kubectl` commands time out
{: #exec_logs_fail}


If you run commands such as `kubectl exec`, `kubectl attach`, `kubectl proxy`, `kubectl port-forward`, or `kubectl logs`, you see the following message.
{: tsSymptoms}

```sh
<workerIP>:10250: getsockopt: connection timed out
```
{: screen}

```sh
kubectl -n kube-system logs metrics-server-65fc69c6b7-f682d -c metrics-server
Error from server: Get “https://10.38.193.213:10250/containerLogs/kube-system/metrics-server-65fc69c6b7-f682d/metrics-server”: EOF
```
{: screen}

```sh
kubectl -n kube-system exec -it metrics-server-65fc69c6b7-f682d -c metrics-server -- sh
Error from server: error dialing backend: EOF
```
{: screen}

Review and complete the following the steps for your cluster version.
{: tsResolve}

- Version 1.21 and later the Konnectivity VPN connection between the master node and worker nodes is not functioning properly.
- The cluster has both private and public service endpoints enabled.
- Service endpoints or VRF are not enabled in the account.

To determine if VRF and service endpoints are enabled in your account, run `ibmcloud account show`. Look for the following output.

```sh
VRF Enabled:                        true
Service Endpoint Enabled:           true
```
{: screen}

To determine if your classic cluster has both public and private service endpoint enabled, run `ibmcloud ks cluster get -c <cluster_id>`. Look for output similar to the following.

```sh
Public Service Endpoint URL:    https://c105.<REGION>.containers.cloud.ibm.com:<port> 
Private Service Endpoint URL:   https://c105.private.<REGION>.containers.cloud.ibm.com:<port> 
```

If your cluster meets these conditions, [enable service endpoints and VRF](/docs/account?topic=account-vrf-service-endpoint&interface=ui#vrf) for the account.




