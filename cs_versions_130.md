---

copyright: 
  years: 2024, 2024
lastupdated: "2024-05-30"


keywords: kubernetes, containers, 130, version 130, 130 update actions

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}



# 1.30 version information and update actions
{: #cs_versions_130}


Review information about version 1.30 of {{site.data.keyword.containerlong}}. For more information about Kubernetes project version 1.30, see the [Kubernetes change log](https://kubernetes.io/releases/notes/.){: external}.
{: shortdesc}


![This badge indicates Kubernetes version 1.30 certification for {{site.data.keyword.containerlong_notm}}](images/certified-kubernetes-color.svg){: caption="Figure 1. Kubernetes version 1.30 certification badge" caption-side="bottom"} 

{{site.data.keyword.containerlong_notm}} is a Certified Kubernetes product for version 1.30 under the CNCF Kubernetes Software Conformance Certification program. _Kubernetes® is a registered trademark of The Linux Foundation in the United States and other countries, and is used pursuant to a license from The Linux Foundation._



## Release timeline 
{: #release_timeline_130}

The following table includes the expected release timeline for version 1.30 of {{site.data.keyword.containerlong}}. You can use this information for planning purposes, such as to estimate the general time that the version might become unsupported. 
{: shortdesc}

Dates that are marked with a dagger (`†`) are tentative and subject to change.
{: important}

| Version | Supported? | {{site.data.keyword.containerlong_notm}} \n release date | {{site.data.keyword.containerlong_notm}} \n unsupported date |
|------|------|----------|----------|
| 1.30 | Yes | {{site.data.keyword.kubernetes_130_release_date}} | {{site.data.keyword.kubernetes_130_unsupported_date}} `†` |
{: caption="Release timeline for {{site.data.keyword.containerlong_notm}} version 1.30" caption-side="bottom"}


## Preparing to update
{: #prep-up-130}

This information summarizes updates that are likely to have an impact on deployed apps when you update a cluster to version 1.30. For a complete list of changes, review the [community Kubernetes change log](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.30.md){: external} and [IBM version change log](/docs/containers?topic=containers-changelog_130) for version 1.30. You can also review the [Kubernetes helpful warnings](https://kubernetes.io/blog/2020/09/03/warnings/){: external}.
{: shortdesc}


The Istio cluster add-on does not yet support version 1.30. If your apps use Istio, do not upgrade your cluster to version 1.30.
{: important}

The cluster autoscaler add-on does not yet support version 1.30. If your apps use cluster autoscaler, do not upgrade your cluster to version 1.30.
{: important}

[Portworx](/docs/containers?topic=containers-storage_portworx_about) does not yet support version 1.30. If your apps use Portworx, do not upgrade your cluster to version 1.30.
{: important}

VPC workers nodes provisioned at version 1.30 have the VPC Instance Metadata Service enabled. For more information, see [About VPC Instance Metadata](/docs/vpc?topic=vpc-imd-about)
{: note}


### Update before master
{: #before_130}

The following table shows the actions that you must take before you update the Kubernetes master.

| Type | Description |
| --- | --- |
| Calico operator namespace migration | If your cluster was upgraded to version 1.29, it will have had a Calico operator namespace migration started. This migration must be completed before your cluster will be allowed to upgrade to version 1.30. If the following commands do not return any data then the migration is complete: `kubectl get nodes -l projectcalico.org/operator-node-migration --no-headers --ignore-not-found ; kubectl get deployment calico-typha -n kube-system -o name --ignore-not-found`. |
{: caption="Changes to make before you update the master to Kubernetes 1.30" caption-side="bottom"}


### Update after master
{: #after_130}

The following table shows the actions that you must take after you update the Kubernetes master.

| Type | Description |
| --- | --- |
| **Deprecated:** Pod `container.apparmor.security.beta.kubernetes.io` annotations. | Pod `container.apparmor.security.beta.kubernetes.io` annotations are now deprecated. These annotations are replaced by the `securityContext.appArmorProfile` field for pods and containers. If your pods rely on these deprecated annotations, update them to use the `securityContext.appArmorProfile` field instead. For more information, see [Restrict a Container's Access to Resources with AppArmor](https://kubernetes.io/docs/tutorials/security/apparmor/). |
| **Unsupported:** `kubectl apply` `--prune-whitelist` option | The deprecated `--prune-whitelist` option on `kubectl apply` has been removed and is replaced by the `--prune-allowlist` option. If your scripts rely on the previous behavior, update them. |
| `kubectl get cronjob` output | The `kubectl get cronjob` output has been changed to include a time zone column. If your scripts rely on the previous behavior, update them. |
| Kubernetes API server audit policy | The [Kubernetes API server `default` and `verbose` audit policies](/docs/containers?topic=containers-health-audit#audit-api-server) have been updated. If your apps rely on the previous policies, update them. |
{: caption="Changes to make after you update the master to Kubernetes 1.30" caption-side="bottom"}



## Important networking changes for VPC clusters created at version 1.30
{: #understand-sbd}

Beginning with version 1.30, {{site.data.keyword.containerlong_notm}} introduced a new security feature for VPC clusters called Secure by Default Cluster VPC Networking.

At a high-level, the security posture for {{site.data.keyword.containerlong_notm}} VPC clusters has changed from allowing all outbound traffic and providing users with mechanisms to selectively block traffic as needed to now blocking all traffic that is not crucial to cluster functionality and providing users with mechanisms to selectively allow traffic as needed.

When you provision a new {{site.data.keyword.containerlong_notm}} VPC cluster at version 1.30 or later, the default provisioning behavior is to allow only the traffic that is necessary for the cluster to function. All other access is blocked. To implement Secure by Default Networking, there are changes to the default VPC security groups settings as well as new Virtual Private Endpoints (VPEs) for common IBM services.

Some key notes for Secure by Default Networking are:

- Applies to VPC clusters only. Classic clusters are not impacted.

- Does not affect existing clusters. Existing clusters in your VPC will continue to function as they do today.

- Applies only to {{site.data.keyword.containerlong_notm}} clusters newly provisioned at version 1.30. The security group configurations for existing {{site.data.keyword.containerlong_notm}} clusters that are upgraded to version 1.30, including any customizations you've made, are not changed.

- The default behavior for clusters created at version 1.30 and later is to enable Secure by Default outbound traffic protection. However, new parameters in the UI, CLI, API, and Terraform allow you to disable this feature. You can also enable and disable outbound traffic protection after you create a cluster.

- If your VPC uses a custom DNS resolver, provisioning a new version 1.30 cluster automatically adds rules allowing traffic through the resolver IP addresses on your IKS-managed security group (`kube-<clusterID>`).


For an overview of Secure by Default Cluster VPC networking, including the security groups, rules, and VPEs that are created by default, see [Understanding Secure by Default Cluster VPC Networking](/docs/openshift?topic=openshift-vpc-security-group-reference).



### Which connections are allowed?
{: #sbd-allowed-connections}

In VPC clusters with Secure by Default outbound traffic protection enabled, the following connections are allowed. 

- Accessing the internal IBM `*.icr.io` registries to pull necessary container images via a VPE gateway.
- Accessing the cluster master and {{site.data.keyword.containerlong_notm}} APIs via VPE gateways.
- Accessing other essential IBM services such as logging and monitoring over the private IBM network.
- Accessing IBM Cloud DNS.


### Which connections are blocked?
{: #sbd-blocked-connections}

Review the following examples of connections that are blocked by default. Note that you can selectively enable outbound traffic to these or other external sources that your app needs.

- Pulling images from public registries such as quay.io and Docker Hub.
- Accessing any service over the public network.


### Changes to worker-to-master backup communication
{: #backup-considerations}

VPC cluster workers use the private network to communicate with the cluster master. Previously, for VPC clusters that had the public service endpoint enabled, if the private network was blocked or unavailable, then the cluster workers could fall back to using the public network to communicate with the cluster master.

In clusters with Secure by Default outbound traffic protection, falling back to the public network is not an option because public outbound traffic from the cluster workers is blocked. You might want to disable outbound traffic protection to allow this public network backup option, however, there is a better alternative. Instead, if there a temporary issue with the worker-to-master connection over the private network, then, at that time, you can add a temporary security group rule to the `kube-clusterID` security group to allow outbound traffic to the cluster master `apiserver` port. This way you allow only traffic for the `apiserver` instead of all traffic. Later, when the problem is resolved, you can remove the temporary rule.


## Allowing outbound traffic after creating a 1.30 cluster
{: #sbd-allow-outbound-after}

If you created a version 1.30 cluster with outbound traffic protection enabled, your apps or services might experience downtime due to dependencies that require external network connections. Review the following options for enabling outbound traffic selectively or allowing all outbound traffic.

For more information, see [Managing outbound traffic protection in VPC clusters](/docs/containers?topic=containers-sbd-allow-outbound).


## Common issues and troubleshooting 
{: #sbd-common-ts}

- [After enabling outbound traffic protection on my 1.30 cluster, my app no longer works](/docs/containers?topic=containers-ts-sbd-app-not-working).
- [When I try to create version 1.30 cluster, I see a quota error](/docs/containers?topic=containers-ts-sbd-cluster-create-quota).
- [When I update my cluster to secure by default, my nodeport app no longer works](/docs/containers?topic=containers-ts-sbd-nodeport-not-working).
- [Why do I see DNS failures after adding a custom DNS resolver?](/docs/containers?topic=containers-ts-sbd-custom-dns).
- [After creating a version 1.30 cluster, applications running in other clusters in my VPC are failing](/docs/containers?topic=containers-ts-sbd-other-clusters).



