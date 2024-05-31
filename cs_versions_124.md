---

copyright: 
  years: 2022, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers, 1.24 update actions

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}



# 1.24 version information and update actions
{: #cs_versions_124}


Kubernetes version 1.24 is unsupported. Update your cluster to at least [version 1.25](/docs/containers?topic=containers-cs_versions_125) as soon as possible.
{: important}

Review information about version 1.24 of {{site.data.keyword.containerlong}}, released {{site.data.keyword.kubernetes_124_release_date}}.
{: shortdesc}

Looking for general information on updating {{site.data.keyword.containerlong}} clusters, or information on a different version? See [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions).
{: tip}

![This badge indicates Kubernetes version 1.24 certification for {{site.data.keyword.containerlong_notm}}](images/certified-kubernetes-color.svg){: caption="Figure 1. Kubernetes version 1.24 certification badge" caption-side="bottom"} 

{{site.data.keyword.containerlong_notm}} is a Certified Kubernetes product for version 1.24 under the CNCF Kubernetes Software Conformance Certification program. _Kubernetes® is a registered trademark of The Linux Foundation in the United States and other countries, and is used pursuant to a license from The Linux Foundation._



For more information about Kubernetes project version 1.24, see the [Kubernetes change log](https://kubernetes.io/releases/notes/.){: external}

## Release timeline 
{: #release_timeline_124}

The following table includes the expected release timeline for version 1.24 of {{site.data.keyword.containerlong}}. You can use this information for planning purposes, such as to estimate the general time that the version might become unsupported. 
{: shortdesc}

Dates that are marked with a dagger (`†`) are tentative and subject to change.
{: important}

|  Version | Supported? | {{site.data.keyword.containerlong_notm}} \n release date | {{site.data.keyword.containerlong_notm}} \n unsupported date |
|------|------|----------|----------|
| 1.24 | Yes | 09 Jun 2022 | {{site.data.keyword.kubernetes_124_unsupported_date}} |
{: caption="Release timeline for {{site.data.keyword.containerlong_notm}} version 1.24" caption-side="bottom"}

## Preparing to update
{: #prep-up-124}

This information summarizes updates that are likely to have and impact on deployed apps when you update a cluster to version 1.24. For a complete list of changes, review the [community Kubernetes change log](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.24.md){: external} and [IBM version change log](/docs/containers?topic=containers-changelog_124) for version 1.24. You can also review the [Kubernetes helpful warnings](https://kubernetes.io/blog/2020/09/03/warnings/){: external}. 
{: shortdesc}



### Update before master
{: #before_124}

[Pod security policies](https://kubernetes.io/docs/concepts/security/pod-security-policy/) are scheduled for removal in Kubernetes version 1.25. See the Kubernetes [Deprecated API migration guide](https://kubernetes.io/docs/reference/using-api/deprecation-guide/#psp-v125){: external} for more information. Customers have the option to replace Pod Security Policies with [Pod security admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/){: external} or a [third party admission webhook](https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/){: external}. IBM Cloud Kubernetes Service will make a beta version of Pod Security available in version 1.24 to aid in the migration, but this support is not yet available.
{: important}

The following table shows the actions that you must take before you update the Kubernetes master.
{: shortdesc}

| Type | Description|
| --- | --- |
| IBM Cloud Block Storage driver and plug-in installation | The IBM Cloud Block Storage driver and plug-in component is now installed on clusters running classic infrastructure. If you installed the IBM Cloud Block Storage driver and plug-in via the Helm chart, you must uninstall the Helm chart before continuing the master update. Note that your existing persistent volume claims (PVCs) will continue to work after the Helm chart is uninstalled, but you are not able to provision new PVCs until the master update is completed. To uninstall the Helm chart, see [Removing the Block Storage Helm chart](#124-rm-block-helm). |
| Updated default container network sysctls | New containers running on the pod network will have the following `sysctl` tuning applied by default: `net.ipv4.tcp_keepalive_intvl=15`, `net.ipv4.tcp_keepalive_probes=6` and `net.ipv4.tcp_keepalive_time=40`. If your apps rely on the previous defaults, you must update your app deployment to customize the `sysctl` settings. See [Optimizing network keepalive sysctl settings](/docs/containers?topic=containers-kernel#keepalive-iks) for details. |
{: caption="Changes to make after you update the master to Kubernetes 1.24" caption-side="bottom"}

#### Removing the Block Storage Helm chart
{: #124-rm-block-helm}

1. Add the `iks-charts` repo and update it.
    ```sh
    helm repo add iks-charts https://icr.io/helm/iks-charts && helm repo update
    ```
    {: pre}

1. List the Helm deployments in your cluster and make a note of the {{site.data.keyword.blockstorageshort}} plug-in deployment in the `kube-system` namespace.
    ```sh
    helm ls -A
    ```
    {: pre}

1. Delete the plug-in from your cluster by using the `helm delete` command.
    ```sh
    helm delete RELEASE -n kube-system
    ```
    {: pre}

1. List pods in the `kube-system` namespace to verify the plug-in pods have been removed.
    ```sh
    kubectl get pods -n kube-system | grep block
    ```
    {: pre}

### Update after master
{: #124_after}

The following table shows the actions that you must take after you update the Kubernetes master.
{: shortdesc}

| Type | Description|
| --- | --- |
| **Unsupported:** `kubectl expose` removes `--container-port` and `--generator` options | The `kubectl expose` command no longer supports the deprecated `--container-port` and `--generator` options. If your scripts rely on these options, update them. |
| **Unsupported:** `kubectl run` removes several options | The `kubectl run` command no longer supports the deprecated `--serviceaccount`, `--hostport`, `--requests` and `--limits` options. If your scripts rely on these options, update them. |
{: caption="Changes to make after you update the master to Kubernetes 1.24" caption-side="bottom"}


