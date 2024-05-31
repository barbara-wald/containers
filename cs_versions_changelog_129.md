---

copyright: 
  years: 2023, 2024
lastupdated: "2024-05-30"


keywords: kubernetes, containers, change log, 129 change log, 129 updates

subcollection: containers


---

# Kubernetes version 1.29 change log
{: #changelog_129}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.29. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}

## Overview
{: #changelog_overview_129}

In clusters that run version 1.23 or earlier, the {{site.data.keyword.cloud_notm}} provider version enables Kubernetes APIs and features that are at beta. In version 1.24 and later, most new beta features are disabled by default. Kubernetes alpha features, which are subject to change, are disabled in all versions. For more information, see the [Default service settings for Kubernetes components](/docs/containers?topic=containers-service-settings) and the [feature gates](/docs/containers?topic=containers-service-settings#feature-gates) for each version.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security){: external} for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}




## Version 1.29 change log
{: #129_changelog}


Review the version 1.29 change log.
{: shortdesc}


### Change log for master fix pack 1.29.5_1540, released 29 May 2024
{: #1295_1540_M}

The following table shows the changes that are in the master fix pack 1.29.5_1540. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.9 | v1.4.10 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.5.8 | v2.5.9 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.29.4-1 | v1.29.5-1 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} for Classic plug-in and monitor | 442 | 443 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | v1.1.2 | v1.1.3 | New version contains updates and security fixes. |
| Key Management Service provider | v2.9.5 | v2.9.6 | New version contains updates and security fixes. |
| Konnectivity server and agent | v0.29.0 | v0.29.2_105_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.29.2){: external}. |
| Kubernetes | v1.29.4 | v1.29.5 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.5){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2867 | 2933 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.13 | v0.13.15 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.15){: external}. |
{: caption="Changes since version 1.29.4_1535" caption-side="bottom"}


### Change log for worker node fix pack 1.29.4_1538, released 23 May 2024
{: #1294_1538_W}

The following table shows the changes that are in the worker node fix pack 1.29.4_1538. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-177-generic | 5.4.0-182-generic | Worker node package and kernel updates [CVE-2016-9840](https://nvd.nist.gov/vuln/detail/CVE-2016-9840){: external}, [CVE-2016-9841](https://nvd.nist.gov/vuln/detail/CVE-2016-9841){: external}, [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2022-37434](https://nvd.nist.gov/vuln/detail/CVE-2022-37434){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2023-24023](https://nvd.nist.gov/vuln/detail/CVE-2023-24023){: external}, [CVE-2023-4421](https://nvd.nist.gov/vuln/detail/CVE-2023-4421){: external}, [CVE-2023-46838](https://nvd.nist.gov/vuln/detail/CVE-2023-46838){: external}, [CVE-2023-52600](https://nvd.nist.gov/vuln/detail/CVE-2023-52600){: external}, [CVE-2023-52603](https://nvd.nist.gov/vuln/detail/CVE-2023-52603){: external}, [CVE-2023-5388](https://nvd.nist.gov/vuln/detail/CVE-2023-5388){: external}, [CVE-2023-6135](https://nvd.nist.gov/vuln/detail/CVE-2023-6135){: external}, [CVE-2024-0607](https://nvd.nist.gov/vuln/detail/CVE-2024-0607){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-23851](https://nvd.nist.gov/vuln/detail/CVE-2024-23851){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}, [CVE-2024-26581](https://nvd.nist.gov/vuln/detail/CVE-2024-26581){: external}, [CVE-2024-26589](https://nvd.nist.gov/vuln/detail/CVE-2024-26589){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}, [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}, CIS benchmark compliance: [4.5.1.6](https://workbench.cisecurity.org/sections/1985958/recommendations/3181904){: external}, [4.5.1.7](https://workbench.cisecurity.org/sections/1985958/recommendations/3181905){: external}, [4.5.7](https://workbench.cisecurity.org/sections/1985957/recommendations/3181911){: external}. |
| Kubernetes | 1.29.4 | 1.29.4 | N/A |
| Containerd | 1.7.16 | 1.7.17 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.17){: external}. |
| HAProxy | d225100 | 4e826da | [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}. |
| GPU device plug-in and installer | 806184d | c0e1605 | Security fixes for [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}. |
{: caption="Changes since version 1.29.4_1537" caption-side="bottom"}


### Change log for worker node fix pack 1.29.4_1537, released 06 May 2024
{: #1294_1537_W}

The following table shows the changes that are in the worker node fix pack 1.29.4_1537. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-177-generic | 5.4.0-177-generic | Worker node package updates for [CVE-2015-1197](https://nvd.nist.gov/vuln/detail/CVE-2015-1197){: external}, [CVE-2023-7207](https://nvd.nist.gov/vuln/detail/CVE-2023-7207){: external}, [CVE-2024-28182](https://nvd.nist.gov/vuln/detail/CVE-2024-28182){: external}, [CVE-2024-32487](https://nvd.nist.gov/vuln/detail/CVE-2024-32487){: external}. CIS benchmark compliance: [1.1.2.1](https://workbench.cisecurity.org/sections/1985909/recommendations/3181638){: external}, [1.1.2.2](https://workbench.cisecurity.org/sections/1985909/recommendations/3181639){: external}, [1.1.2.3](https://workbench.cisecurity.org/sections/1985909/recommendations/3181640){: external}, and [1.1.2.4](https://workbench.cisecurity.org/sections/1985909/recommendations/3181642){: external}.  |
| Kubernetes | 1.29.4 | 1.29.4 | N/A |
| Containerd | 1.7.15 | 1.7.16 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.16){: external}. |
| HAProxy | 295dba8 | 295dba8 | N/A |
| GPU device plug-in and installer | 9fad43c | 806184d | Security fixes for [CVE-2022-48554](https://nvd.nist.gov/vuln/detail/CVE-2022-48554){: external}, [CVE-2023-2975](https://nvd.nist.gov/vuln/detail/CVE-2023-2975){: external}, [CVE-2023-3446](https://nvd.nist.gov/vuln/detail/CVE-2023-3446){: external}, [CVE-2023-5678](https://nvd.nist.gov/vuln/detail/CVE-2023-5678){: external}, [CVE-2024-22365](https://nvd.nist.gov/vuln/detail/CVE-2024-22365){: external}, [CVE-2023-7008](https://nvd.nist.gov/vuln/detail/CVE-2023-7008){: external}, [CVE-2023-3817](https://nvd.nist.gov/vuln/detail/CVE-2023-3817){: external}, [CVE-2023-6129](https://nvd.nist.gov/vuln/detail/CVE-2023-6129){: external}, [CVE-2023-6237](https://nvd.nist.gov/vuln/detail/CVE-2023-6237){: external}, [CVE-2024-0727](https://nvd.nist.gov/vuln/detail/CVE-2024-0727){: external}. |
{: caption="Changes since version 1.29.4_1536" caption-side="bottom"}


### Change log for master fix pack 1.29.4_1535, released 24 April 2024
{: #1294_1535_M}

The following table shows the changes that are in the master fix pack 1.29.4_1535. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.27.3 | v3.27.2 | See the [Calico release notes](https://docs.tigera.io/calico/3.27/release-notes/#v3.27.2){: external}. |
| Cluster health image | v1.4.8 | v1.4.9 | New version contains updates and security fixes. |
| etcd | v3.5.12 | v3.5.13 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.13){: external}. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.29.3-1 | v1.29.4-1 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | v1.1.1 | v1.1.2 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | bd30030 | 4c5d156 | New version contains updates and security fixes. |
| Key Management Service provider | v2.9.4 | v2.9.5 | New version contains updates and security fixes. |
| Kubernetes | v1.29.3 | v1.29.4 | Update resolves [CVE-2024-3177](https://nvd.nist.gov/vuln/detail/CVE-2024-3177). For more information, see the [Security Bulletin](https://www.ibm.com/support/pages/node/7148966){: external} and the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.4){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2831 | 2867 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.12 | v0.13.13 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.13){: external}. |
| Tigera Operator | v1.32.7-97-iks | v1.32.5-91-iks | See the [Tigera Operator release notes](https://github.com/tigera/operator/releases/tag/v1.32.5){: external}. |
{: caption="Changes since version 1.29.3_1531" caption-side="bottom"}


### Change log for worker node fix pack 1.29.4_1536, released 22 April 2024
{: #1294_1536_W}

The following table shows the changes that are in the worker node fix pack 1.29.4_1536. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-174-generic | 5.4.0-177-generic | Worker node and kernel package updates for [CVE-2016-9840](https://nvd.nist.gov/vuln/detail/CVE-2016-9840){: external}, [CVE-2016-9841](https://nvd.nist.gov/vuln/detail/CVE-2016-9841){: external}, [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2022-37434](https://nvd.nist.gov/vuln/detail/CVE-2022-37434){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2023-24023](https://nvd.nist.gov/vuln/detail/CVE-2023-24023){: external}, [CVE-2023-4421](https://nvd.nist.gov/vuln/detail/CVE-2023-4421){: external}, [CVE-2023-46838](https://nvd.nist.gov/vuln/detail/CVE-2023-46838){: external}, [CVE-2023-52600](https://nvd.nist.gov/vuln/detail/CVE-2023-52600){: external}, [CVE-2023-52603](https://nvd.nist.gov/vuln/detail/CVE-2023-52603){: external}, [CVE-2023-5388](https://nvd.nist.gov/vuln/detail/CVE-2023-5388){: external}, [CVE-2023-6135](https://nvd.nist.gov/vuln/detail/CVE-2023-6135){: external}, [CVE-2024-0607](https://nvd.nist.gov/vuln/detail/CVE-2024-0607){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-23851](https://nvd.nist.gov/vuln/detail/CVE-2024-23851){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}, [CVE-2024-26581](https://nvd.nist.gov/vuln/detail/CVE-2024-26581){: external}, [CVE-2024-26589](https://nvd.nist.gov/vuln/detail/CVE-2024-26589){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}, [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}. |
| Kubernetes | 1.29.3 | 1.29.4 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.29.md){: external}. |
| Containerd | 1.7.13 | 1.7.15 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.15){: external}. |
| HAProxy | 295dba8 | 4e826da | Security fixes for [CVE-2024-28834](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28834){: external}. |
| GPU device plug-in and installer | 206b5a6 | 9fad43c1 | Security fixes for [CVE-2024-1488](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-1488){: external}, [CVE-2024-28834](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28834){: external}, [CVE-2024-28835](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28835){: external}. |
{: caption="Changes since version 1.29.3_1533" caption-side="bottom"}


### Change log for worker node fix pack 1.29.3_1533, released 8 April 2024
{: #1293_1533_W}

The following table shows the changes that are in the worker node fix pack 1.29.3_1533. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-174-generic | 5.4.0-174-generic | Worker node package updates for [CVE-2024-2398](https://nvd.nist.gov/vuln/detail/CVE-2024-2398){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}. |
| Kubernetes | 1.29.3 | 1.29.3 | N/A |
| Containerd | 1.7.14 | 1.7.13 | Reverted due to a [bug](https://github.com/containerd/containerd/issues/10036){: external}. |
| HAProxy | 512b32a | 295dba8 | Security fixes for [CVE-2023-28322](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-28322){: external}, [CVE-2023-38546](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-38546){: external}, [CVE-2023-46218](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-46218){: external}, [CVE-2023-52425](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-52425){: external}
| GPU device plug-in and installer | 5b69345 | 206b5a6 | Security fixes for [CVE-2023-28322](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-28322){: external}, [CVE-2023-38546](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-38546){: external}, [CVE-2023-46218](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-46218){: external}, [CVE-2023-52425](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-52425){: external}
{: caption="Changes since version 1.29.3_1532" caption-side="bottom"}


### Change log for master fix pack 1.29.3_1531, released 27 March 2024
{: #1293_1531_M}

The following table shows the changes that are in the master fix pack 1.29.3_1531. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.27.0 | v3.27.2 | See the [Calico release notes](https://docs.tigera.io/calico/latest/release-notes/#calico-open-source-3272-bug-fix-release){: external}. |
| Cluster health image | v1.4.7 | v1.4.8 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.5.7 | v2.5.8 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.29.2-2 | v1.29.3-1 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 441 | 442 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | v1.1.0 | v1.1.1 | New version contains updates and security fixes. |
| Key Management Service provider | v2.9.2 | v2.9.4 | New version contains updates and security fixes. |
| Kubernetes | v1.29.2 | v1.29.3 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.3){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.28 | 1.23.0 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.23.0){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2807 | 2831 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.11 | v0.13.12 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.12){: external}. |
| Tigera Operator | v1.32.4-82-iks | v1.32.5-91-iks | See the [Tigera Operator release notes](https://github.com/tigera/operator/releases/tag/v1.32.6){: external}. |
{: caption="Changes since version 1.29.2_1528" caption-side="bottom"}


### Change log for worker node fix pack 1.29.3_1532, released 25 March 2024
{: #1293_1532_W}

The following table shows the changes that are in the worker node fix pack 1.29.3_1532. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-173-generic | 5.4.0-174-generic | Worker node kernel and package updates for [CVE-2012-6655](https://nvd.nist.gov/vuln/detail/CVE-2012-6655){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-22667](https://nvd.nist.gov/vuln/detail/CVE-2024-22667){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}. |
| Kubernetes | 1.29.2 | 1.29.3 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.3){: external}. |
| Containerd | 1.7.14 | 1.7.14 | N/A |
| HAProxy | 512b32 | 512b32 | N/A |
{: caption="Changes since version 1.29.2_1529" caption-side="bottom"}


### Change log for worker node fix pack 1.29.2_1529, released 13 March 2024
{: #1292_1529_W}

The following table shows the changes that are in the worker node fix pack 1.29.2_1529. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-172-generic | 5.4.0-173-generic | Worker node kernel and package updates for [CVE-2022-47695](https://nvd.nist.gov/vuln/detail/CVE-2022-47695){: external}, [CVE-2022-48063](https://nvd.nist.gov/vuln/detail/CVE-2022-48063){: external}, [CVE-2022-48065](https://nvd.nist.gov/vuln/detail/CVE-2022-48065){: external}, [CVE-2022-48624](https://nvd.nist.gov/vuln/detail/CVE-2022-48624){: external}, [CVE-2023-0340](https://nvd.nist.gov/vuln/detail/CVE-2023-0340){: external}, [CVE-2023-22995](https://nvd.nist.gov/vuln/detail/CVE-2023-22995){: external}, [CVE-2023-50782](https://nvd.nist.gov/vuln/detail/CVE-2023-50782){: external}, [CVE-2023-51779](https://nvd.nist.gov/vuln/detail/CVE-2023-51779){: external}, [CVE-2023-51781](https://nvd.nist.gov/vuln/detail/CVE-2023-51781){: external}, [CVE-2023-51782](https://nvd.nist.gov/vuln/detail/CVE-2023-51782){: external}, [CVE-2023-6915](https://nvd.nist.gov/vuln/detail/CVE-2023-6915){: external}, [CVE-2024-0565](https://nvd.nist.gov/vuln/detail/CVE-2024-0565){: external}, [CVE-2024-0646](https://nvd.nist.gov/vuln/detail/CVE-2024-0646){: external}, [CVE-2024-24806](https://nvd.nist.gov/vuln/detail/CVE-2024-24806){: external}, [CVE-2024-25062](https://nvd.nist.gov/vuln/detail/CVE-2024-25062){: external}. |
| Kubernetes | 1.29.2 | 1.29.2 | N/A |
| GPU device plug-in and installer | 71cb7f | 5b6934 | N/A |
| HAProxy | 9b0400 | 512b32 | N/A |
| Containerd | 1.7.13 | 1.7.14 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.14){: external}. |
{: caption="Changes since version 1.29.2_1530" caption-side="bottom"}


### Change log for master fix pack 1.29.2_1528, released 28 February 2024
{: #1292_1528_M}

The following table shows the changes that are in the master fix pack 1.29.2_1528. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.6 | v1.4.7 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.5.4 | v2.5.7 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.29.1-7 | v1.29.2-2 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 7185ea1 | bd30030 | New version contains updates and security fixes. |
| Key Management Service provider | v2.9.0 | v2.9.2 | New version contains updates and security fixes. |
| Kubernetes | v1.29.1 | v1.29.2 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.2){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2789 | 2807 | New version contains updates and security fixes. |
| Tigera Operator | v1.32.4-74-iks | v1.32.4-82-iks | See the [Tigera Operator release notes](https://github.com/tigera/operator/releases/tag/v1.32.4){: external}. |
{: caption="Changes since version 1.29.1_1524" caption-side="bottom"}


### Change log for worker node fix pack 1.29.2_1529, released 26 February 2024
{: #1292_1529_W_feb}

The following table shows the changes that are in the worker node fix pack 1.29.2_1529. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | N/A| 5.4.0-172-generic | Worker node kernel & package updates for [CVE-2023-4408](https://nvd.nist.gov/vuln/detail/CVE-2023-4408){: external}, [CVE-2023-4641](https://nvd.nist.gov/vuln/detail/CVE-2023-4641){: external}, [CVE-2023-50387](https://nvd.nist.gov/vuln/detail/CVE-2023-50387){: external}, [CVE-2023-50868](https://nvd.nist.gov/vuln/detail/CVE-2023-50868){: external}, [CVE-2023-51781](https://nvd.nist.gov/vuln/detail/CVE-2023-51781){: external}, [CVE-2023-5517](https://nvd.nist.gov/vuln/detail/CVE-2023-5517){: external}, [CVE-2023-6516](https://nvd.nist.gov/vuln/detail/CVE-2023-6516){: external}, [CVE-2023-6915](https://nvd.nist.gov/vuln/detail/CVE-2023-6915){: external}, [CVE-2024-0565](https://nvd.nist.gov/vuln/detail/CVE-2024-0565){: external}, [CVE-2024-0646](https://nvd.nist.gov/vuln/detail/CVE-2024-0646){: external}. |
| GPU device plug-in and installer | d992fea | 71cb7f7 | Security fixes for [CVE-2023-50387](https://nvd.nist.gov/vuln/detail/CVE-2023-50387){: external}, [CVE-2023-50868](https://nvd.nist.gov/vuln/detail/CVE-2023-50868){: external}. |
| Containerd | N/A | 1.7.13 | N/A |
{: caption="Changes since version N/A" caption-side="bottom"}


### Change log for master fix pack 1.29.1_1524 and worker node fix pack 1.29.1_1525, released 14 February 2024
{: #1291_1524M_and_1291_1525W}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.26.4 | v3.27.0 | See the [Calico release notes](https://docs.tigera.io/calico/latest/release-notes/#v3.27.0). |
| Tigera Operator | N/A | v1.32.4-74-iks | **New:** See the [Tigera Operator release notes](https://github.com/tigera/operator/releases/tag/v1.32.4). |
| etcd | v3.5.11 | v3.5.12 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.12). |
| IBM Calico extension | 1525 | N/A | Component has been removed. |
| IBM Cloud Block Storage driver and plug-in | v2.4.14 | v2.5.4 | New version contains updates and security fixes. |
| IBM Cloud Controller Manager | v1.28.6-3 | v1.29.1-7 | New version contains updates and security fixes. |
| IBM Cloud File Storage plug-in and monitor | 439 | 441 | New version contains updates and security fixes. |
| IBM Cloud Metrics Server Config Watcher | 90a78ef | v1.1.0 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.6 | v2.9.0 | New version contains updates and security fixes. In addition, both [KMS v1 and v2](https://kubernetes.io/docs/tasks/administer-cluster/kms-provider/) are now supported. KMS v1 instances are migrated to KMS v2 on upgrade and KMS v2 is now the default. |
| Konnectivity agent and server | v0.1.5_47_iks | v0.29.0 | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.29.0). |
| Kubernetes | v1.28.6 | v1.29.1 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.29.1). |
| Kubernetes configuration | N/A | N/A | See [Default service settings for Kubernetes components](https://cloud.ibm.com/docs/containers?topic=containers-service-settings). |
| Kubernetes snapshot controller | v6.2.2 | v6.3.0 | See the [Kubernetes snapshot controller release notes](https://github.com/kubernetes-csi/external-snapshotter/releases/tag/v6.3.0). |
{: caption="Changes since version 1.28" caption-side="bottom"}





