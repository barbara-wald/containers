---

copyright: 
  years: 2024, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers, change log, 130 change log, 130 updates

subcollection: containers


---

# Kubernetes version 1.30 change log
{: #changelog_130}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.30. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview_130}

In clusters that run version 1.23 or earlier, the {{site.data.keyword.cloud_notm}} provider version enables Kubernetes APIs and features that are at beta. In version 1.24 and later, most new beta features are disabled by default. Kubernetes alpha features, which are subject to change, are disabled in all versions. For more information, see the [Default service settings for Kubernetes components](/docs/containers?topic=containers-service-settings) and the [feature gates](/docs/containers?topic=containers-service-settings#feature-gates) for each version.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security){: external} for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}



## Version 1.30 change log
{: #130_changelog}

### Change log for master fix pack 1.30.1_1520 and worker node fix pack 1.30.0_1518, released 29 May 2024
{: #1301_1520M_and_1300_1518W}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| IBM Cloud Controller Manager | v1.29.5-1 | v1.30.1-2 | New version contains updates and security fixes. |
| Key Management Service provider | v2.9.6 | v2.10.1 | New version contains updates and security fixes. In addition, only [KMS v2](https://kubernetes.io/docs/tasks/administer-cluster/kms-provider/) is supported. KMS v1 instances were migrated to KMS v2 as part of the IBM Cloud Kubernetes Service version 1.29 release. |
| Konnectivity agent and server | v0.29.2_105_iks | v0.30.2 | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.30.2). |
| Kubernetes | v1.29.5 | v1.30.1 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.30.1). |
| Kubernetes add-on resizer | 1.8.19 | 1.8.20 | See the [Kubernetes add-on resizer release notes](https://github.com/kubernetes/autoscaler/releases/tag/addon-resizer-1.8.20). |
| Kubernetes configurations | N/A | N/A | See [Default service settings for Kubernetes components](https://cloud.ibm.com/docs/containers?topic=containers-service-settings). |
| Kubernetes Metrics Server | v0.6.4 | v0.7.1 | See the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-incubator/metrics-server/releases/tag/v0.7.1). |
| Kubernetes snapshot controller | v6.3.0 | v6.3.3 | See the [Kubernetes snapshot controller release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v6.3.3). |
{: caption="Changes since version 1.29" caption-side="bottom"}





