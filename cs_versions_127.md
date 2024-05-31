---

copyright: 
  years: 2023, 2024
lastupdated: "2024-05-30"


keywords: kubernetes, containers, 127, version 127, 127 update actions

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}



# 1.27 version information and update actions
{: #cs_versions_127}

Review information about version 1.27 of {{site.data.keyword.containerlong}}.
{: shortdesc}

Kubernetes version 1.27 is deprecated. Update your cluster to at least [version 1.28](/docs/containers?topic=containers-cs_versions_128) as soon as possible.
{: deprecated}

Looking for general information on updating {{site.data.keyword.containerlong}} clusters, or information on a different version? See [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions).
{: tip}



![This badge indicates Kubernetes version 1.27 certification for {{site.data.keyword.containerlong_notm}}](images/certified-kubernetes-color.svg){: caption="Figure 1. Kubernetes version 1.27 certification badge" caption-side="bottom"} 

{{site.data.keyword.containerlong_notm}} is a Certified Kubernetes product for version 1.27 under the CNCF Kubernetes Software Conformance Certification program. _Kubernetes® is a registered trademark of The Linux Foundation in the United States and other countries, and is used pursuant to a license from The Linux Foundation._



For more information about Kubernetes project version 1.27, see the [Kubernetes change log](https://kubernetes.io/releases/notes/.){: external}.

## Release timeline 
{: #release_timeline_127}

The following table includes the expected release timeline for version 1.27 of {{site.data.keyword.containerlong}}. You can use this information for planning purposes, such as to estimate the general time that the version might become unsupported. 
{: shortdesc}

Dates that are marked with a dagger (`†`) are tentative and subject to change.
{: important}

| Version | Supported? | {{site.data.keyword.containerlong_notm}} \n release date | {{site.data.keyword.containerlong_notm}} \n unsupported date |
|------|------|----------|----------|
| 1.27 | Yes | {{site.data.keyword.kubernetes_127_release_date}} | {{site.data.keyword.kubernetes_127_unsupported_date}} `†` |
{: caption="Release timeline for {{site.data.keyword.containerlong_notm}} version 1.27" caption-side="bottom"}

## Preparing to update
{: #prep-up-127}

This information summarizes updates that are likely to have and impact on deployed apps when you update a cluster to version 1.27. For a complete list of changes, review the [community Kubernetes change log](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.27.md){: external} and [IBM version change log](/docs/containers?topic=containers-changelog_127) for version 1.27. You can also review the [Kubernetes helpful warnings](https://kubernetes.io/blog/2020/09/03/warnings/){: external}.
{: shortdesc}


### Update before master
{: #before_127}

The following table shows the actions that you must take before you update the Kubernetes master.



| Type | Description |
| --- | --- |
| **Unsupported:** Beta version of the `CSIStorageCapacity` API | Migrate manifests and API clients to use the `storage.k8s.io/v1` API version, available since Kubernetes version 1.24. For more information, see [Deprecated API Migration Guide - v1.27](https://kubernetes.io/docs/reference/using-api/deprecation-guide/#v1-27){: external}. | 
| **Unsupported:** Pod `seccomp.security.alpha.kubernetes.io/pod` and `container.seccomp.security.alpha.kubernetes.io` annotations | Kubernetes no longer supports the pod `seccomp.security.alpha.kubernetes.io/pod` and `container.seccomp.security.alpha.kubernetes.io` annotations. These annotations have been deprecated since Kubernetes version 1.19 and has been replaced by the `securityContext.seccompProfile` field for pods and containers. If your pods rely on these unsupported annotations, update them to use the `securityContext.seccompProfile` field instead. For more information, see [Create Pod that uses the container runtime default `seccomp` profile](https://kubernetes.io/docs/tutorials/security/seccomp/#create-pod-that-uses-the-container-runtime-default-seccomp-profile){: external}. |
| `k8s.gcr.io` redirect to `registry.k8s.io` | Kubernetes version 1.27 release artifacts are not published to the `k8s.gcr.io` registry. Furthermore, `k8s.gcr.io` registry traffic are redirected to `registry.k8s.io`. For more information, see [k8s.gcr.io Redirect to registry.k8s.io - What You Need to Know](https://kubernetes.io/blog/2023/03/10/image-registry-redirect/){: external}. Note that IBM Cloud Kubernetes Service has already handled this migration action for all resources provided by IBM. |
| `kubelet` legacy iptables rules | `kubelet` no longer creates certain legacy iptables rules by default. It is possible that this will cause problems with some third-party components that improperly depended on those rules. For more information, see [Kubernetes’s IPTables Chains Are Not API](https://kubernetes.io/blog/2022/09/07/iptables-chains-not-api/){: external}. |
{: caption="Changes to make before you update the master to Kubernetes 1.27" caption-side="bottom"}






