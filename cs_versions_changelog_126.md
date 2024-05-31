---

copyright: 
  years: 2023, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers, change log, 126 change log, 126 updates

subcollection: containers


---

# Kubernetes version 1.26 change log
{: #changelog_126}

View information about version changes for major, minor, and patch updates that are available for your {{site.data.keyword.containerlong}} clusters that run version 1.26. Changes include updates to Kubernetes and {{site.data.keyword.cloud_notm}} Provider components.
{: shortdesc}


Kubernetes version 1.26 is deprecated. Update your cluster to at least [version 1.27](/docs/containers?topic=containers-cs_versions_127) as soon as possible.
{: deprecated}


## Overview
{: #changelog_overview_126}

In clusters that run version 1.23 or earlier, the {{site.data.keyword.cloud_notm}} provider version enables Kubernetes APIs and features that are at beta. In version 1.24 and later, most new beta features are disabled by default. Kubernetes alpha features, which are subject to change, are disabled in all versions. For more information, see the [Default service settings for Kubernetes components](/docs/containers?topic=containers-service-settings) and the [feature gates](/docs/containers?topic=containers-service-settings#feature-gates) for each version.

For more information about major, minor, and patch versions and preparation actions between minor versions, see [Kubernetes versions](/docs/containers?topic=containers-cs_versions).
{: tip}

Check the [Security Bulletins on {{site.data.keyword.cloud_notm}} Status](https://cloud.ibm.com/status?component=containers-kubernetes&selected=security){: external} for security vulnerabilities that affect {{site.data.keyword.containerlong_notm}}. You can filter the results to view only Kubernetes Cluster security bulletins that are relevant to {{site.data.keyword.containerlong_notm}}. Change log entries that address other security vulnerabilities but don't also refer to an {{site.data.keyword.IBM_notm}} security bulletin are for vulnerabilities that are not known to affect {{site.data.keyword.containerlong_notm}} in normal usage. If you run privileged containers, run commands on the workers, or execute untrusted code, then you might be at risk.

Some change logs are for _worker node fix packs_, and apply only to worker nodes. You must [apply these patches](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update) to ensure security compliance for your worker nodes. These worker node fix packs can be at a higher version than the master because some build fix packs are specific to worker nodes. Other change logs are for _master fix packs_, and apply only to the cluster master. Master fix packs might not be automatically applied. You can choose to [apply them manually](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update). For more information about patch types, see [Update types](/docs/containers?topic=containers-cs_versions#update_types).
{: note}

## Version 1.26 change log
{: #126_changelog}


Review the version 1.26 change log.
{: shortdesc}





### Change log for worker node fix pack 1.26.15_1584, released 23 May 2024
{: #12615_1584_W}

The following table shows the changes that are in the worker node fix pack 1.26.15_1584. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-177-generic | 5.4.0-182-generic | Worker node package and kernel updates [CVE-2016-9840](https://nvd.nist.gov/vuln/detail/CVE-2016-9840){: external}, [CVE-2016-9841](https://nvd.nist.gov/vuln/detail/CVE-2016-9841){: external}, [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2022-37434](https://nvd.nist.gov/vuln/detail/CVE-2022-37434){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2023-24023](https://nvd.nist.gov/vuln/detail/CVE-2023-24023){: external}, [CVE-2023-4421](https://nvd.nist.gov/vuln/detail/CVE-2023-4421){: external}, [CVE-2023-46838](https://nvd.nist.gov/vuln/detail/CVE-2023-46838){: external}, [CVE-2023-52600](https://nvd.nist.gov/vuln/detail/CVE-2023-52600){: external}, [CVE-2023-52603](https://nvd.nist.gov/vuln/detail/CVE-2023-52603){: external}, [CVE-2023-5388](https://nvd.nist.gov/vuln/detail/CVE-2023-5388){: external}, [CVE-2023-6135](https://nvd.nist.gov/vuln/detail/CVE-2023-6135){: external}, [CVE-2024-0607](https://nvd.nist.gov/vuln/detail/CVE-2024-0607){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-23851](https://nvd.nist.gov/vuln/detail/CVE-2024-23851){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}, [CVE-2024-26581](https://nvd.nist.gov/vuln/detail/CVE-2024-26581){: external}, [CVE-2024-26589](https://nvd.nist.gov/vuln/detail/CVE-2024-26589){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}, [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}, CIS benchmark compliance: [4.5.1.6](https://workbench.cisecurity.org/sections/1985958/recommendations/3181904){: external}, [4.5.1.7](https://workbench.cisecurity.org/sections/1985958/recommendations/3181905){: external}, [4.5.7](https://workbench.cisecurity.org/sections/1985957/recommendations/3181911){: external}. |
| Kubernetes | 1.26.15 | 1.26.15 | N/A |
| Containerd | 1.7.16 | 1.7.17 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.17){: external}. |
| HAProxy | d225100 | 4e826da | [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}. |
{: caption="Changes since version 1.26.15_1583" caption-side="bottom"}


### Change log for worker node fix pack 1.26.15_1583, released 06 May 2024
{: #12615_1583_W}

The following table shows the changes that are in the worker node fix pack 1.26.15_1583. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-177-generic | 5.4.0-177-generic | Worker node package updates for [CVE-2015-1197](https://nvd.nist.gov/vuln/detail/CVE-2015-1197){: external}, [CVE-2023-7207](https://nvd.nist.gov/vuln/detail/CVE-2023-7207){: external}, [CVE-2024-28182](https://nvd.nist.gov/vuln/detail/CVE-2024-28182){: external}, [CVE-2024-32487](https://nvd.nist.gov/vuln/detail/CVE-2024-32487){: external}. CIS benchmark compliance: [1.1.2.1](https://workbench.cisecurity.org/sections/1985909/recommendations/3181638){: external}, [1.1.2.2](https://workbench.cisecurity.org/sections/1985909/recommendations/3181639){: external}, [1.1.2.3](https://workbench.cisecurity.org/sections/1985909/recommendations/3181640){: external}, and [1.1.2.4](https://workbench.cisecurity.org/sections/1985909/recommendations/3181642){: external}. |
| Kubernetes | 1.26.15 | 1.26.15 | N/A |
| Containerd | 1.7.15 | 1.7.16 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.16){: external}. |
| HAProxy | 295dba8 | 295dba8 | N/A |
| GPU device plug-in and installer | 9fad43c | 806184d | Security fixes for [CVE-2022-48554](https://nvd.nist.gov/vuln/detail/CVE-2022-48554){: external}, [CVE-2023-2975](https://nvd.nist.gov/vuln/detail/CVE-2023-2975){: external}, [CVE-2023-3446](https://nvd.nist.gov/vuln/detail/CVE-2023-3446){: external}, [CVE-2023-5678](https://nvd.nist.gov/vuln/detail/CVE-2023-5678){: external}, [CVE-2024-22365](https://nvd.nist.gov/vuln/detail/CVE-2024-22365){: external}, [CVE-2023-7008](https://nvd.nist.gov/vuln/detail/CVE-2023-7008){: external}, [CVE-2023-3817](https://nvd.nist.gov/vuln/detail/CVE-2023-3817){: external}, [CVE-2023-6129](https://nvd.nist.gov/vuln/detail/CVE-2023-6129){: external}, [CVE-2023-6237](https://nvd.nist.gov/vuln/detail/CVE-2023-6237){: external}, [CVE-2024-0727](https://nvd.nist.gov/vuln/detail/CVE-2024-0727){: external}. |
{: caption="Changes since version 1.26.15_1582" caption-side="bottom"}


### Change log for master fix pack 1.26.15_1581, released 24 April 2024
{: #12615_1581_M}

The following table shows the changes that are in the master fix pack 1.26.15_1581. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.8 | v1.4.9 | New version contains updates and security fixes. |
| etcd | v3.5.12 | v3.5.13 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.13){: external}. |
| GPU device plug-in and installer | 71cb7f7 | 206b5a6 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | 803912f | 50808cc | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | bd30030 | 4c5d156 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.8 | v2.8.9 | New version contains updates and security fixes. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2831 | 2867 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.12 | v0.13.13 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.13){: external}. |
{: caption="Changes since version 1.26.15_1578" caption-side="bottom"}


### Change log for worker node fix pack 1.26.15_1582, released 22 April 2024
{: #12615_1582_W}

The following table shows the changes that are in the worker node fix pack 1.26.15_1582. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-174-generic | 5.4.0-177-generic | Worker node and kernel package updates for [CVE-2016-9840](https://nvd.nist.gov/vuln/detail/CVE-2016-9840){: external}, [CVE-2016-9841](https://nvd.nist.gov/vuln/detail/CVE-2016-9841){: external}, [CVE-2018-25032](https://nvd.nist.gov/vuln/detail/CVE-2018-25032){: external}, [CVE-2022-37434](https://nvd.nist.gov/vuln/detail/CVE-2022-37434){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2023-24023](https://nvd.nist.gov/vuln/detail/CVE-2023-24023){: external}, [CVE-2023-4421](https://nvd.nist.gov/vuln/detail/CVE-2023-4421){: external}, [CVE-2023-46838](https://nvd.nist.gov/vuln/detail/CVE-2023-46838){: external}, [CVE-2023-52600](https://nvd.nist.gov/vuln/detail/CVE-2023-52600){: external}, [CVE-2023-52603](https://nvd.nist.gov/vuln/detail/CVE-2023-52603){: external}, [CVE-2023-5388](https://nvd.nist.gov/vuln/detail/CVE-2023-5388){: external}, [CVE-2023-6135](https://nvd.nist.gov/vuln/detail/CVE-2023-6135){: external}, [CVE-2024-0607](https://nvd.nist.gov/vuln/detail/CVE-2024-0607){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-23851](https://nvd.nist.gov/vuln/detail/CVE-2024-23851){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}, [CVE-2024-26581](https://nvd.nist.gov/vuln/detail/CVE-2024-26581){: external}, [CVE-2024-26589](https://nvd.nist.gov/vuln/detail/CVE-2024-26589){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}, [CVE-2024-28834](https://nvd.nist.gov/vuln/detail/CVE-2024-28834){: external}, [CVE-2024-2961](https://nvd.nist.gov/vuln/detail/CVE-2024-2961){: external}. |
| Kubernetes | 1.26.15 | 1.26.15 | N/A |
| Containerd | 1.7.13 | 1.7.15 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.15){: external}. |
| HAProxy | 295dba8 | 4e826da | Security fixes for [CVE-2024-28834](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28834){: external}. |
| GPU device plug-in and installer | 206b5a6 | 9fad43c1 | Security fixes for [CVE-2024-1488](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-1488){: external}, [CVE-2024-28834](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28834){: external}, [CVE-2024-28835](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2024-28835){: external}. |
{: caption="Changes since version 1.26.15_1580" caption-side="bottom"}


### Change log for worker node fix pack 1.26.15_1580, released 8 April 2024
{: #12615_1580_W}

The following table shows the changes that are in the worker node fix pack 1.26.15_1580. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-174-generic | 5.4.0-174-generic | Worker node package updates for [CVE-2024-2398](https://nvd.nist.gov/vuln/detail/CVE-2024-2398){: external}, [CVE-2024-28085](https://nvd.nist.gov/vuln/detail/CVE-2024-28085){: external}. |
| Kubernetes | 1.26.15 | 1.26.15 | N/A |
| Containerd | 1.7.14 | 1.7.13 | Reverted due to a [bug](https://github.com/containerd/containerd/issues/10036){: external}. |
| HAProxy | 512b32a | 295dba8 | Security fixes for [CVE-2023-28322](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-28322){: external}, [CVE-2023-38546](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-38546){: external}, [CVE-2023-46218](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-46218){: external}, [CVE-2023-52425](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-52425){: external}
| GPU device plug-in and installer | 5b69345 | 206b5a6 | Security fixes for [CVE-2023-28322](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-28322){: external}, [CVE-2023-38546](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-38546){: external}, [CVE-2023-46218](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-46218){: external}, [CVE-2023-52425](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-52425){: external}
{: caption="Changes since version 1.26.15_1579" caption-side="bottom"}


### Change log for master fix pack 1.26.15_1578, released 27 March 2024
{: #12615_1578_M}

The following table shows the changes that are in the master fix pack 1.26.15_1578. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.7 | v1.4.8 | New version contains updates and security fixes. |
| Gateway-enabled cluster controller | 2415 | 2502 | New version contains updates and security fixes. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1534 | 1537 | New version contains security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.18 | v2.4.19 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 441 | 442 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | 90a78ef | 803912f | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.7 | v2.8.8 | New version contains updates and security fixes. |
| Kubernetes | v1.26.14 | v1.26.15 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.15){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.28 | 1.23.0 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.23.0){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2807 | 2831 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.11 | v0.13.12 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.12){: external}. |
{: caption="Changes since version 1.26.14_1575" caption-side="bottom"}


### Change log for worker node fix pack 1.26.15_1579, released 25 March 2024
{: #12615_1579_W}

The following table shows the changes that are in the worker node fix pack 1.26.15_1579. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-173-generic | 5.4.0-174-generic | Worker node kernel and package updates for [CVE-2012-6655](https://nvd.nist.gov/vuln/detail/CVE-2012-6655){: external}, [CVE-2023-23000](https://nvd.nist.gov/vuln/detail/CVE-2023-23000){: external}, [CVE-2023-23004](https://nvd.nist.gov/vuln/detail/CVE-2023-23004){: external}, [CVE-2024-1086](https://nvd.nist.gov/vuln/detail/CVE-2024-1086){: external}, [CVE-2024-22667](https://nvd.nist.gov/vuln/detail/CVE-2024-22667){: external}, [CVE-2024-24855](https://nvd.nist.gov/vuln/detail/CVE-2024-24855){: external}. |
| Kubernetes | 1.26.14 | 1.26.15 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.15){: external}. |
| Containerd | 1.7.14 | 1.7.14 | N/A |
| HAProxy | 512b32 | 512b32 | N/A |
{: caption="Changes since version 1.26.14_1577" caption-side="bottom"}


### Change log for worker node fix pack 1.26.14_1577, released 13 March 2024
{: #12614_1577_W}

The following table shows the changes that are in the worker node fix pack 1.26.14_1577. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-172-generic | 5.4.0-173-generic | Worker node kernel and package updates for [CVE-2022-47695](https://nvd.nist.gov/vuln/detail/CVE-2022-47695){: external}, [CVE-2022-48063](https://nvd.nist.gov/vuln/detail/CVE-2022-48063){: external}, [CVE-2022-48065](https://nvd.nist.gov/vuln/detail/CVE-2022-48065){: external}, [CVE-2022-48624](https://nvd.nist.gov/vuln/detail/CVE-2022-48624){: external}, [CVE-2023-0340](https://nvd.nist.gov/vuln/detail/CVE-2023-0340){: external}, [CVE-2023-22995](https://nvd.nist.gov/vuln/detail/CVE-2023-22995){: external}, [CVE-2023-50782](https://nvd.nist.gov/vuln/detail/CVE-2023-50782){: external}, [CVE-2023-51779](https://nvd.nist.gov/vuln/detail/CVE-2023-51779){: external}, [CVE-2023-51781](https://nvd.nist.gov/vuln/detail/CVE-2023-51781){: external}, [CVE-2023-51782](https://nvd.nist.gov/vuln/detail/CVE-2023-51782){: external}, [CVE-2023-6915](https://nvd.nist.gov/vuln/detail/CVE-2023-6915){: external}, [CVE-2024-0565](https://nvd.nist.gov/vuln/detail/CVE-2024-0565){: external}, [CVE-2024-0646](https://nvd.nist.gov/vuln/detail/CVE-2024-0646){: external}, [CVE-2024-24806](https://nvd.nist.gov/vuln/detail/CVE-2024-24806){: external}, [CVE-2024-25062](https://nvd.nist.gov/vuln/detail/CVE-2024-25062){: external}. |
| Kubernetes | 1.26.14 | 1.26.14 | N/A |
| HAProxy | 9b0400 | 512b32 | N/A |
| Containerd | 1.7.13 | 1.7.14 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.14){: external}. |
{: caption="Changes since version 1.26.14_1576" caption-side="bottom"}


### Change log for master fix pack 1.26.14_1575, released 28 February 2024
{: #12614_1575_M}

The following table shows the changes that are in the master fix pack 1.26.14_1575. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.6 | v1.4.7 | New version contains updates and security fixes. |
| etcd | v3.5.11 | v3.5.12 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.12){: external}. |
| GPU device plug-in and installer | 6273cd0 | d992fea | New version contains updates and security fixes. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1525 | 1534 | New version contains security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.14 | v2.4.18 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.13-3 | v1.26.13-8 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 439 | 441 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 7185ea1 | bd30030 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.6 | v2.8.7 | New version contains updates and security fixes. |
| Kubernetes | v1.26.13 | v1.26.14 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.14){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2789 | 2807 | New version contains updates and security fixes. |
{: caption="Changes since version 1.26.13_1569" caption-side="bottom"}


### Change log for worker node fix pack 1.26.14_1576, released 26 February 2024
{: #12614_1576_W}

The following table shows the changes that are in the worker node fix pack 1.26.14_1576. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-171-generic | 5.4.0-172-generic | Worker node kernel and package updates for [CVE-2023-4408](https://nvd.nist.gov/vuln/detail/CVE-2023-4408){: external}, [CVE-2023-4641](https://nvd.nist.gov/vuln/detail/CVE-2023-4641){: external}, [CVE-2023-50387](https://nvd.nist.gov/vuln/detail/CVE-2023-50387){: external}, [CVE-2023-50868](https://nvd.nist.gov/vuln/detail/CVE-2023-50868){: external}, [CVE-2023-51781](https://nvd.nist.gov/vuln/detail/CVE-2023-51781){: external}, [CVE-2023-5517](https://nvd.nist.gov/vuln/detail/CVE-2023-5517){: external}, [CVE-2023-6516](https://nvd.nist.gov/vuln/detail/CVE-2023-6516){: external}, [CVE-2023-6915](https://nvd.nist.gov/vuln/detail/CVE-2023-6915){: external}, [CVE-2024-0565](https://nvd.nist.gov/vuln/detail/CVE-2024-0565){: external}, [CVE-2024-0646](https://nvd.nist.gov/vuln/detail/CVE-2024-0646){: external}. |
| Containerd | 1.7.13 | 1.7.13 | N/A |
{: caption="Changes since version 1.26.13_1571" caption-side="bottom"}


### Change log for worker node fix pack 1.26.13_1571, released 12 February 2024
{: #12613_1571_W}

The following table shows the changes that are in the worker node fix pack 1.26.13_1571. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-170-generic | 5.4.0-171-generic | Worker node kernel and package updates for [CVE-2023-2953](https://nvd.nist.gov/vuln/detail/CVE-2023-2953){: external}, [CVE-2023-45863](https://nvd.nist.gov/vuln/detail/CVE-2023-45863){: external}, [CVE-2023-5678](https://nvd.nist.gov/vuln/detail/CVE-2023-5678){: external}, [CVE-2023-6040](https://nvd.nist.gov/vuln/detail/CVE-2023-6040){: external}, [CVE-2023-6606](https://nvd.nist.gov/vuln/detail/CVE-2023-6606){: external}, [CVE-2023-6931](https://nvd.nist.gov/vuln/detail/CVE-2023-6931){: external}, [CVE-2023-6932](https://nvd.nist.gov/vuln/detail/CVE-2023-6932){: external}, [CVE-2024-0727](https://nvd.nist.gov/vuln/detail/CVE-2024-0727){: external}. |
| Kubernetes | N/A |N/A|N/A|
| Containerd | 1.7.12 | 1.7.13 | For more information, see [change log](https://github.com/containerd/containerd/releases/tag/v1.7.13){: external} and [security bulletin for CVE-2024-21626](https://www.ibm.com/support/pages/node/7116230){: external}. |
| HAProxy | a13673 | 9b0400 | Security fixes for [CVE-2024-0553](https://nvd.nist.gov/vuln/detail/CVE-2024-0553){: external}, [CVE-2023-48795](https://nvd.nist.gov/vuln/detail/CVE-2023-48795){: external}, [CVE-2021-35937](https://nvd.nist.gov/vuln/detail/CVE-2021-35937){: external}, [CVE-2021-35938](https://nvd.nist.gov/vuln/detail/CVE-2021-35938){: external}, [CVE-2021-35939](https://nvd.nist.gov/vuln/detail/CVE-2021-35939){: external}. |
{: caption="Changes since version 1.26.13_1570" caption-side="bottom"}


### Change log for master fix pack 1.26.13_1569, released 31 January 2024
{: #12613_1569_M}

The following table shows the changes that are in the master fix pack 1.26.13_1569. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.26.3 | v3.26.4 | See the [Calico release notes](https://docs.tigera.io/calico/3.26/release-notes/#v3.26.4){: external}. |
| Cluster health image | v1.4.5 | v1.4.6 | New version contains security fixes. |
| etcd | v3.5.10 | v3.5.11 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.11){: external}. |
| GPU device plug-in and installer | 0e3950c | 6273cd0 | New version contains security fixes. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1487 | 1525 | New version contains security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.11-6 | v1.26.13-3 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | 58e69e0 | 90a78ef | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | e544e35 | 7185ea1 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.5 | v2.8.6 | New version contains updates and security fixes. |
| Kubernetes | v1.26.11 | v1.26.13 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.13){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.27 | 1.22.28 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.28){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2767 | 2789 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.10 | v0.13.11 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.11){: external}. |
{: caption="Changes since version 1.26.11_1564" caption-side="bottom"}


### Change log for worker node fix pack 1.26.13_1570, released 29 January 2024
{: #12613_1570_W}

The following table shows the changes that are in the worker node fix pack 1.26.13_1570. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-169-generic | 5.4.0-170-generic | Worker node package and kernel updates for [CVE-2020-28493](https://nvd.nist.gov/vuln/detail/CVE-2020-28493){: external}, [CVE-2022-44840](https://nvd.nist.gov/vuln/detail/CVE-2022-44840){: external}, [CVE-2022-45703](https://nvd.nist.gov/vuln/detail/CVE-2022-45703){: external}, [CVE-2022-47007](https://nvd.nist.gov/vuln/detail/CVE-2022-47007){: external}, [CVE-2022-47008](https://nvd.nist.gov/vuln/detail/CVE-2022-47008){: external}, [CVE-2022-47010](https://nvd.nist.gov/vuln/detail/CVE-2022-47010){: external}, [CVE-2022-47011](https://nvd.nist.gov/vuln/detail/CVE-2022-47011){: external}, [CVE-2023-6004](https://nvd.nist.gov/vuln/detail/CVE-2023-6004){: external}, [CVE-2023-6040](https://nvd.nist.gov/vuln/detail/CVE-2023-6040){: external}, [CVE-2023-6606](https://nvd.nist.gov/vuln/detail/CVE-2023-6606){: external}, [CVE-2023-6918](https://nvd.nist.gov/vuln/detail/CVE-2023-6918){: external}, [CVE-2023-6931](https://nvd.nist.gov/vuln/detail/CVE-2023-6931){: external}, [CVE-2023-6932](https://nvd.nist.gov/vuln/detail/CVE-2023-6932){: external}, [CVE-2024-0553](https://nvd.nist.gov/vuln/detail/CVE-2024-0553){: external}, [CVE-2024-22195](https://nvd.nist.gov/vuln/detail/CVE-2024-22195){: external}, [CVE-2024-22365](https://nvd.nist.gov/vuln/detail/CVE-2024-22365){: external}. |
| Kubernetes | 1.26.11 | 1.26.13 | For more information, see [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.13){: external}. |
| Containerd | 1.7.12 | 1.7.12 | N/A |
| HAProxy | e105dc | a13673 | Security fixes for [CVE-2023-7104](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-7104){: external}, [CVE-2023-27043](https://exchange.xforce.ibmcloud.com/vulnerabilities/CVE-2023-27043){: external}. |
{: caption="Changes since version 1.26.11_1568" caption-side="bottom"}


### Change log for worker node fix pack 1.26.11_1568, released 16 January 2024
{: #12611_1568_W}

The following table shows the changes that are in the worker node fix pack 1.26.11_1568. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-169-generic | 5.4.0-169-generic | Worker node package updates for [CVE-2021-41617](https://nvd.nist.gov/vuln/detail/CVE-2021-41617){: external}, [CVE-2022-39348](https://nvd.nist.gov/vuln/detail/CVE-2022-39348){: external}, [CVE-2023-46137](https://nvd.nist.gov/vuln/detail/CVE-2023-46137){: external}, [CVE-2023-51385](https://nvd.nist.gov/vuln/detail/CVE-2023-51385){: external}, [CVE-2023-7104](https://nvd.nist.gov/vuln/detail/CVE-2023-7104){: external}. |
| Kubernetes | 1.26.11 | 1.26.11 | N/A |
| Containerd | 1.7.11 | 1.7.12 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.12){: external}. |
| Haproxy | 3060b0 | e105dc | [CVE-2023-39615](https://nvd.nist.gov/vuln/detail/CVE-2023-39615){: external}, [CVE-2023-5981](https://nvd.nist.gov/vuln/detail/CVE-2023-5981){: external}, [CVE-2022-48560](https://nvd.nist.gov/vuln/detail/CVE-2022-48560){: external}, [CVE-2022-48564](https://nvd.nist.gov/vuln/detail/CVE-2022-48564){: external}. |
{: caption="Changes since version 1.26.11_1567" caption-side="bottom"}


### Change log for worker node fix pack 1.26.11_1567, released 02 January 2024
{: #12611_1567_W}

The following table shows the changes that are in the worker node fix pack 1.26.11_1567. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-169-generic | 5.4.0-169-generic | Worker node package updates for [CVE-2023-48795](https://nvd.nist.gov/vuln/detail/CVE-2023-48795){: external}. |
| Kubernetes | 1.26.11 | 1.26.11 | N/A |
| Containerd | 1.7.11 | 1.7.11 | N/A |
{: caption="Changes since version 1.26.11_1566" caption-side="bottom"}


### Change log for worker node fix pack 1.26.11_1566, released 18 December 2023
{: #12611_1566_W}

The following table shows the changes that are in the worker node fix pack 1.26.11_1566. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-167-generic | 5.4.0-169-generic | Worker node kernel & package updates for [CVE-2020-19726](https://nvd.nist.gov/vuln/detail/CVE-2020-19726){: external}, [CVE-2021-46174](https://nvd.nist.gov/vuln/detail/CVE-2021-46174){: external}, [CVE-2022-1725](https://nvd.nist.gov/vuln/detail/CVE-2022-1725){: external}, [CVE-2022-1771](https://nvd.nist.gov/vuln/detail/CVE-2022-1771){: external}, [CVE-2022-1897](https://nvd.nist.gov/vuln/detail/CVE-2022-1897){: external}, [CVE-2022-2000](https://nvd.nist.gov/vuln/detail/CVE-2022-2000){: external}, [CVE-2022-35205](https://nvd.nist.gov/vuln/detail/CVE-2022-35205){: external}, [CVE-2023-23931](https://nvd.nist.gov/vuln/detail/CVE-2023-23931){: external}, [CVE-2023-31085](https://nvd.nist.gov/vuln/detail/CVE-2023-31085){: external}, [CVE-2023-37453](https://nvd.nist.gov/vuln/detail/CVE-2023-37453){: external}, [CVE-2023-39192](https://nvd.nist.gov/vuln/detail/CVE-2023-39192){: external}, [CVE-2023-39193](https://nvd.nist.gov/vuln/detail/CVE-2023-39193){: external}, [CVE-2023-39804](https://nvd.nist.gov/vuln/detail/CVE-2023-39804){: external}, [CVE-2023-42754](https://nvd.nist.gov/vuln/detail/CVE-2023-42754){: external}, [CVE-2023-45539](https://nvd.nist.gov/vuln/detail/CVE-2023-45539){: external}, [CVE-2023-45871](https://nvd.nist.gov/vuln/detail/CVE-2023-45871){: external}, [CVE-2023-46218](https://nvd.nist.gov/vuln/detail/CVE-2023-46218){: external}, [CVE-2023-46246](https://nvd.nist.gov/vuln/detail/CVE-2023-46246){: external}, [CVE-2023-4806](https://nvd.nist.gov/vuln/detail/CVE-2023-4806){: external}, [CVE-2023-4813](https://nvd.nist.gov/vuln/detail/CVE-2023-4813){: external}, [CVE-2023-48231](https://nvd.nist.gov/vuln/detail/CVE-2023-48231){: external}, [CVE-2023-48233](https://nvd.nist.gov/vuln/detail/CVE-2023-48233){: external}, [CVE-2023-48234](https://nvd.nist.gov/vuln/detail/CVE-2023-48234){: external}, [CVE-2023-48235](https://nvd.nist.gov/vuln/detail/CVE-2023-48235){: external}, [CVE-2023-48236](https://nvd.nist.gov/vuln/detail/CVE-2023-48236){: external}, [CVE-2023-48237](https://nvd.nist.gov/vuln/detail/CVE-2023-48237){: external}, [CVE-2023-5178](https://nvd.nist.gov/vuln/detail/CVE-2023-5178){: external}, [CVE-2023-5717](https://nvd.nist.gov/vuln/detail/CVE-2023-5717){: external}. |
| Kubernetes | N/A |N/A|N/A|
| Containerd | 1.7.10 |1.7.11| For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.11){: external}. |
{: caption="Changes since version 1.26.11_1565" caption-side="bottom"}


### Change log for master fix pack 1.26.11_1564, released 06 December 2023
{: #12611_1564_M}

The following table shows the changes that are in the master fix pack 1.26.11_1564. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| GPU device plug-in and installer | 99267c4 | 0e3950c | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.12 | v2.4.14 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.10-4 | v1.26.11-6 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 438 | 439 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | c33e6e7 | 58e69e0 | New version contains updates and security fixes. |
| Konnectivity agent and server | v0.1.5_39_iks | v0.1.5_47_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.1.5){: external}. |
| Kubernetes | v1.26.10 | v1.26.11 | Review the [community Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.11){: external}. Resolves [CVE-2023-39325](https://nvd.nist.gov/vuln/detail/CVE-2023-39325){: external} and [CVE-2023-44487](https://nvd.nist.gov/vuln/detail/CVE-2023-44487){: external}. For more information, see [Security Bulletin: IBM Cloud Kubernetes Service is affected by Kubernetes API server security vulnerabilities (CVE-2023-39325 and CVE-2023-44487)](https://www.ibm.com/support/pages/node/7091444){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.24 | 1.22.27 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.27){: external}. |
| Load balancer and Load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2731 | 2767 | New version contains updates and security fixes. |
{: caption="Changes since version 1.26.10_1560" caption-side="bottom"}


### Change log for worker node fix pack 1.26.11_1565, released 04 December 2023
{: #12611_1565_W}

The following table shows the changes that are in the worker node fix pack 1.26.11_1565. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-166-generic | 5.4.0-167-generic | Worker node kernel & package updates for [CVE-2023-31085](https://nvd.nist.gov/vuln/detail/CVE-2023-31085){: external}, [CVE-2023-40217](https://nvd.nist.gov/vuln/detail/CVE-2023-40217){: external}, [CVE-2023-44487](https://nvd.nist.gov/vuln/detail/CVE-2023-44487){: external}, [CVE-2023-45871](https://nvd.nist.gov/vuln/detail/CVE-2023-45871){: external}, [CVE-2023-47038](https://nvd.nist.gov/vuln/detail/CVE-2023-47038){: external}, [CVE-2023-5981](https://nvd.nist.gov/vuln/detail/CVE-2023-5981){: external}. |
| Kubernetes | 1.26.10 | 1.26.11 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.11){: external}. |
{: caption="Changes since version 1.26.10_1561" caption-side="bottom"}


### Change log for worker node fix pack 1.26.10_1561, released 29 November 2023
{: #12610_1561_W}

The following table shows the changes that are in the worker node fix pack 1.26.10_1561. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-166-generic | 5.4.0-166-generic | Worker node package updates for [CVE-2023-36054](https://nvd.nist.gov/vuln/detail/CVE-2023-36054){: external}, [CVE-2023-4016](https://nvd.nist.gov/vuln/detail/CVE-2023-4016){: external}, [CVE-2023-43804](https://nvd.nist.gov/vuln/detail/CVE-2023-43804){: external}, [CVE-2023-45803](https://nvd.nist.gov/vuln/detail/CVE-2023-45803){: external}. |
| Kubernetes | 1.26.9 | 1.26.10 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.10){: external}. |
| Containerd| 1.7.8 | 1.7.9 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.9){: external}. |
{: caption="Changes since version 1.26.9_1559" caption-side="bottom"}


### Change log for master fix pack 1.26.10_1560, released 15 November 2023
{: #12610_1560_M}

The following table shows the changes that are in the master fix pack 1.26.10_1560. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.4.4 | v1.4.5 | New version contains updates and security fixes. |
| etcd | v3.5.9 | v3.5.10 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.10){: external}. |
| Gateway-enabled cluster controller | 2366 | 2415 | New version contains updates and security fixes. |
| GPU device plug-in and installer | 4319682 | 99267c4a | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.9-8 | v1.26.10-4 | New version contains updates and security fixes. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 435 | 438 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | a1edf56 | c33e6e7 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | f0d3265 | e544e35 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.4 | v2.8.5 | New version contains updates and security fixes. |
| Konnectivity agent and server | v0.1.3_5_iks | v0.1.5_39_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.1.5){: external}. |
| Kubernetes | v1.26.9 | v1.26.10 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.10){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2681 | 2731 | New version contains updates and security fixes. |
| Portieris admission controller | v0.13.8 | v0.13.10 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.10){: external}. |
{: caption="Changes since version 1.26.9_1557" caption-side="bottom"}


### Change log for worker node fix pack 1.26.9_1559, released 08 November 2023
{: #1269_1559_W}

The following table shows the changes that are in the worker node fix pack 1.26.9_1559. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
|Ubuntu 20.04 packages | 5.4.0-165-generic | 5.4.0-166-generic | Worker node kernel & package updates for [CVE-2023-0597](https://nvd.nist.gov/vuln/detail/CVE-2023-0597){: external}, [CVE-2023-31083](https://nvd.nist.gov/vuln/detail/CVE-2023-31083){: external}, [CVE-2023-34058](https://nvd.nist.gov/vuln/detail/CVE-2023-34058){: external}, [CVE-2023-34059](https://nvd.nist.gov/vuln/detail/CVE-2023-34059){: external}, [CVE-2023-34319](https://nvd.nist.gov/vuln/detail/CVE-2023-34319){: external}, [CVE-2023-3446](https://nvd.nist.gov/vuln/detail/CVE-2023-3446){: external}, [CVE-2023-3772](https://nvd.nist.gov/vuln/detail/CVE-2023-3772){: external}, [CVE-2023-3817](https://nvd.nist.gov/vuln/detail/CVE-2023-3817){: external}, [CVE-2023-4132](https://nvd.nist.gov/vuln/detail/CVE-2023-4132){: external}, [CVE-2023-42752](https://nvd.nist.gov/vuln/detail/CVE-2023-42752){: external}, [CVE-2023-42753](https://nvd.nist.gov/vuln/detail/CVE-2023-42753){: external}, [CVE-2023-42755](https://nvd.nist.gov/vuln/detail/CVE-2023-42755){: external}, [CVE-2023-42756](https://nvd.nist.gov/vuln/detail/CVE-2023-42756){: external}, [CVE-2023-4622](https://nvd.nist.gov/vuln/detail/CVE-2023-4622){: external}, [CVE-2023-4623](https://nvd.nist.gov/vuln/detail/CVE-2023-4623){: external}, [CVE-2023-4733](https://nvd.nist.gov/vuln/detail/CVE-2023-4733){: external}, [CVE-2023-4735](https://nvd.nist.gov/vuln/detail/CVE-2023-4735){: external}, [CVE-2023-4750](https://nvd.nist.gov/vuln/detail/CVE-2023-4750){: external}, [CVE-2023-4751](https://nvd.nist.gov/vuln/detail/CVE-2023-4751){: external}, [CVE-2023-4752](https://nvd.nist.gov/vuln/detail/CVE-2023-4752){: external}, [CVE-2023-4781](https://nvd.nist.gov/vuln/detail/CVE-2023-4781){: external}, [CVE-2023-4881](https://nvd.nist.gov/vuln/detail/CVE-2023-4881){: external}, [CVE-2023-4921](https://nvd.nist.gov/vuln/detail/CVE-2023-4921){: external}, [CVE-2023-5344](https://nvd.nist.gov/vuln/detail/CVE-2023-5344){: external}, [CVE-2023-5441](https://nvd.nist.gov/vuln/detail/CVE-2023-5441){: external}, [CVE-2023-5535](https://nvd.nist.gov/vuln/detail/CVE-2023-5535){: external}. |
| Containerd | 1.7.7 | 1.7.8 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.8){: external}. |
{: caption="Changes since version 1.26.9_1558" caption-side="bottom"}


### Change log for master fix pack 1.26.9_1557, released 25 October 2023
{: #1269_1557_M}

The following table shows the changes that are in the master fix pack 1.26.9_1557. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.26.1 | v3.26.3 | See the [Calico release notes](https://docs.tigera.io/calico/latest/release-notes/#v3.26.3){: external}. |
| Cluster health image | v1.4.2 | v1.4.4 | New version contains updates and security fixes. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1390 | 1487 | New version contains security fixes. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.10 | v2.4.12 | New version contains updates and security fixes. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.8-3 | v1.26.9-8 | New version contains updates and security fixes. The logic for the `service.kubernetes.io/ibm-load-balancer-cloud-provider-vpc-idle-connection-timeout` annotation has changed. The default idle timeout is dependent on your account settings. Usually, this value is `50`. However some allowlisted accounts have larger timeout settings. If you don't set the annotation, your load balancers use the timeout setting in your account. You can explicitly specify the timeout by setting this annotation. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 4e2f346 | f0d3265 | New version contains updates and security fixes. |
| Key Management Service provider | v2.8.2 | v2.8.4 | New version contains updates and security fixes. |
| Kubernetes | v1.26.8 | v1.26.9 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.9){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.23 | 1.22.24 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.24){: external}. |
| Portieris admission controller | v0.13.6 | v0.13.8 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.8){: external}. |
{: caption="Changes since version 1.26.8_1554" caption-side="bottom"}


### Change log for worker node fix pack 1.26.9_1558, released 23 October 2023
{: #1269_1558_W}

The following table shows the changes that are in the worker node fix pack 1.26.9_1558. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-164-generic | 5.4.0-165-generic | Worker node kernel & package updates for [CVE-2022-3234](https://nvd.nist.gov/vuln/detail/CVE-2022-3234){: external}, [CVE-2022-3256](https://nvd.nist.gov/vuln/detail/CVE-2022-3256){: external}, [CVE-2022-3324](https://nvd.nist.gov/vuln/detail/CVE-2022-3324){: external}, [CVE-2022-3352](https://nvd.nist.gov/vuln/detail/CVE-2022-3352){: external}, [CVE-2022-3520](https://nvd.nist.gov/vuln/detail/CVE-2022-3520){: external}, [CVE-2022-3591](https://nvd.nist.gov/vuln/detail/CVE-2022-3591){: external}, [CVE-2022-3705](https://nvd.nist.gov/vuln/detail/CVE-2022-3705){: external}, [CVE-2022-4292](https://nvd.nist.gov/vuln/detail/CVE-2022-4292){: external}, [CVE-2022-4293](https://nvd.nist.gov/vuln/detail/CVE-2022-4293){: external}, [CVE-2023-34319](https://nvd.nist.gov/vuln/detail/CVE-2023-34319){: external}, [CVE-2023-38546](https://nvd.nist.gov/vuln/detail/CVE-2023-38546){: external}, [CVE-2023-42752](https://nvd.nist.gov/vuln/detail/CVE-2023-42752){: external}, [CVE-2023-42753](https://nvd.nist.gov/vuln/detail/CVE-2023-42753){: external}, [CVE-2023-42755](https://nvd.nist.gov/vuln/detail/CVE-2023-42755){: external}, [CVE-2023-42756](https://nvd.nist.gov/vuln/detail/CVE-2023-42756){: external}, [CVE-2023-4622](https://nvd.nist.gov/vuln/detail/CVE-2023-4622){: external}, [CVE-2023-4623](https://nvd.nist.gov/vuln/detail/CVE-2023-4623){: external}, [CVE-2023-4881](https://nvd.nist.gov/vuln/detail/CVE-2023-4881){: external}, [CVE-2023-4921](https://nvd.nist.gov/vuln/detail/CVE-2023-4921){: external}. |
| Kubernetes | 1.26.8 | 1.26.9 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.9){: external}. |
| Containerd | 1.7.6 | 1.7.7 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.7.7){: external}. |
{: caption="Changes since version 1.26.8_1556" caption-side="bottom"}


### Change log for worker node fix pack 1.26.8_1556, released 9 October 2023
{: #1268_1556_W}

The following table shows the changes that are in the worker node fix pack 1.26.8_1556. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-163-generic | 5.4.0-164-generic | Worker node kernel & package updates for [CVE-2021-4001](https://nvd.nist.gov/vuln/detail/CVE-2021-4001){: external}, [CVE-2023-1206](https://nvd.nist.gov/vuln/detail/CVE-2023-1206){: external}, [CVE-2023-20588](https://nvd.nist.gov/vuln/detail/CVE-2023-20588){: external}, [CVE-2023-3212](https://nvd.nist.gov/vuln/detail/CVE-2023-3212){: external}, [CVE-2023-3863](https://nvd.nist.gov/vuln/detail/CVE-2023-3863){: external}, [CVE-2023-40283](https://nvd.nist.gov/vuln/detail/CVE-2023-40283){: external}, [CVE-2023-4128](https://nvd.nist.gov/vuln/detail/CVE-2023-4128){: external}, [CVE-2023-4194](https://nvd.nist.gov/vuln/detail/CVE-2023-4194){: external}, [CVE-2023-43785](https://nvd.nist.gov/vuln/detail/CVE-2023-43785){: external}, [CVE-2023-43786](https://nvd.nist.gov/vuln/detail/CVE-2023-43786){: external}, [CVE-2023-43787](https://nvd.nist.gov/vuln/detail/CVE-2023-43787){: external}. |
| Kubernetes | N/A |N/A|N/A|
| Containerd | N/A |N/A|N/A|
{: caption="Changes since version 1.26.8_1555" caption-side="bottom"}


### Change log for worker node fix pack 1.26.8_1555, released 27 September 2023
{: #1268_1555_W}

The following table shows the changes that are in the worker node fix pack 1.26.8_1555. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-162-generic | 5.4.0-163-generic| Package updates for [CVE-2023-3341](https://nvd.nist.gov/vuln/detail/CVE-2023-3341){: external}, [CVE-2023-4156](https://nvd.nist.gov/vuln/detail/CVE-2023-4156){: external}, [CVE-2023-4128](https://nvd.nist.gov/vuln/detail/CVE-2023-4128){: external}, [CVE-2023-20588](https://nvd.nist.gov/vuln/detail/CVE-2023-20588){: external}, [CVE-2023-20900](https://nvd.nist.gov/vuln/detail/CVE-2023-20900){: external}, [CVE-2023-40283](https://nvd.nist.gov/vuln/detail/CVE-2023-40283){: external}. |
| RHEL 8 Packages | 4.18.0-477.21.1.el8_8 | 4.18.0-477.27.1.el8_8 | Worker node kernel & package updates for [CVE-2023-2002](https://nvd.nist.gov/vuln/detail/CVE-2023-2002){: external}, [CVE-2023-3090](https://nvd.nist.gov/vuln/detail/CVE-2023-3090){: external}, [CVE-2023-3390](https://nvd.nist.gov/vuln/detail/CVE-2023-3390){: external}, [CVE-2023-3776](https://nvd.nist.gov/vuln/detail/CVE-2023-3776){: external}, [CVE-2023-4004](https://nvd.nist.gov/vuln/detail/CVE-2023-4004){: external}, [CVE-2023-20593](https://nvd.nist.gov/vuln/detail/CVE-2023-20593){: external}, [CVE-2023-29491](https://nvd.nist.gov/vuln/detail/CVE-2023-29491){: external}, [CVE-2023-30630](https://nvd.nist.gov/vuln/detail/CVE-2023-30630){: external}, [CVE-2023-35001](https://nvd.nist.gov/vuln/detail/CVE-2023-35001){: external}, [CVE-2023-35788](https://nvd.nist.gov/vuln/detail/CVE-2023-35788){: external}. |
{: caption="Changes since version 1.26.7_1552" caption-side="bottom"}


### Change log for master fix pack 1.26.8_1554, released 20 September 2023
{: #1268_1554_M}

The following table shows the changes that are in the master fix pack 1.26.8_1554. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.25.1 | v3.26.1 | See the [Calico release notes](https://docs.tigera.io/calico/latest/release-notes/#v3.26.1){: external}. |
| Cluster health image | v1.3.24 | v1.4.2 | Updated `Go` to version `1.20.8` and updated dependencies. Updated to new base image. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.5 | v2.4.10 | Updated `Go dependencies`. Updated to newer UBI base image. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.7-4 | v1.26.8-3 | Updated to support the `Kubernetes 1.26.8` release. Updated `Go` to version `1.20.7` and updated `Go dependencies`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 434 | 435 | Updated `Go` to version `1.20.6` and updated dependencies. Updated to newer UBI base image. |
| Key Management Service provider | v2.7.3 | v2.8.2 | Updated `Go dependencies`. Changed to new base image. |
| Kubernetes | v1.26.7 | v1.26.8 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.8){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2631 | 2681 | Updated `Go` to version `1.19.12` and updated `Go dependencies`. |
{: caption="Changes since version 1.26.7_1550" caption-side="bottom"}


### Change log for worker node fix pack 1.26.7_1552, released 12 September 2023
{: #1267_1552_W}

The following table shows the changes that are in the worker node fix pack 1.26.7_1552. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-156-generic | 5.4.0-162-generic | Worker node kernel & package updates for [CVE-2020-21047](https://nvd.nist.gov/vuln/detail/CVE-2020-21047){: external}, [CVE-2021-33294](https://nvd.nist.gov/vuln/detail/CVE-2021-33294){: external}, [CVE-2022-40982](https://nvd.nist.gov/vuln/detail/CVE-2022-40982){: external}, [CVE-2023-20593](https://nvd.nist.gov/vuln/detail/CVE-2023-20593){: external}[CVE-2023-2269](https://nvd.nist.gov/vuln/detail/CVE-2023-2269){: external}, [CVE-2023-31084](https://nvd.nist.gov/vuln/detail/CVE-2023-31084){: external}, [CVE-2023-3268](https://nvd.nist.gov/vuln/detail/CVE-2023-3268){: external}, [CVE-2023-3609](https://nvd.nist.gov/vuln/detail/CVE-2023-3609){: external}, [CVE-2023-3611](https://nvd.nist.gov/vuln/detail/CVE-2023-3611){: external}, [CVE-2023-3776](https://nvd.nist.gov/vuln/detail/CVE-2023-3776){: external}. |
| Containerd | 1.7.4| 1.7.5 |N/A|
{: caption="Changes since version 1.26.7_1551" caption-side="bottom"}


### Change log for master fix pack 1.26.7_1550, released 30 August 2023
{: #1267_1550_M}

The following table shows the changes that are in the master fix pack 1.26.7_1550. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.3.23 | v1.3.24 | Updated `Go` to version `1.19.12` and updated dependencies. Updated base image version to 378. |
| Gateway-enabled cluster controller | 2322 | 2366 | Update `Go` dependencies to fix [CVE-2023-3978](https://nvd.nist.gov/vuln/detail/CVE-2023-3978){: external}. |
| GPU device plug-in and installer | 495931a | 8e87e60 | Updated `Go` to version `1.19.11` |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.7-1 | v1.26.7-4 | Updated `Go` dependencies to resolve a CVE. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 433 | 434 | Updated `Go` to version `1.20.6` and updated dependencies. Updated to newer UBI base image. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | d293d8b | a1edf56 | Updated `Go` to version `1.20.6`. |
| Key Management Service provider | v2.7.2 | v2.7.3 | Updated `Go` dependencies. |
| Portieris admission controller | v0.13.5 | v0.13.6 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.6){: external}. |
{: caption="Changes since version 1.26.7_1545" caption-side="bottom"}


### Change log for worker node fix pack 1.26.7_1551, released 28th August 2023
{: #1267_1551_W}

The following table shows the changes that are in the worker node fix pack 1.26.7_1551. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-155-generic | 5.4.0-156-generic | Worker node kernel & package updates for [CVE-2022-2598](https://nvd.nist.gov/vuln/detail/CVE-2022-2598){: external}, [CVE-2022-3016](https://nvd.nist.gov/vuln/detail/CVE-2022-3016){: external}, [CVE-2022-3037](https://nvd.nist.gov/vuln/detail/CVE-2022-3037){: external}, [CVE-2022-3099](https://nvd.nist.gov/vuln/detail/CVE-2022-3099){: external}, [CVE-2023-40225](https://nvd.nist.gov/vuln/detail/CVE-2023-40225){: external}. |
{: caption="Changes since version 1.26.7_1547" caption-side="bottom"}


### Change log for worker node fix pack 1.26.7_1547, released 15th August 2023
{: #1267_1547_W}

The following table shows the changes that are in the worker node fix pack 1.26.7_1547. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | N/A | N/A | Package updates for [CVE-2020-36691](https://nvd.nist.gov/vuln/detail/CVE-2020-36691){: external}, [CVE-2022-0168](https://nvd.nist.gov/vuln/detail/CVE-2022-0168){: external}, [CVE-2022-1184](https://nvd.nist.gov/vuln/detail/CVE-2022-1184){: external}, [CVE-2022-2208](https://nvd.nist.gov/vuln/detail/CVE-2022-2208){: external}, [CVE-2022-2210](https://nvd.nist.gov/vuln/detail/CVE-2022-2210){: external}, [CVE-2022-2257](https://nvd.nist.gov/vuln/detail/CVE-2022-2257){: external}, [CVE-2022-2264](https://nvd.nist.gov/vuln/detail/CVE-2022-2264){: external}, [CVE-2022-2284](https://nvd.nist.gov/vuln/detail/CVE-2022-2284){: external}, [CVE-2022-2285](https://nvd.nist.gov/vuln/detail/CVE-2022-2285){: external}, [CVE-2022-2286](https://nvd.nist.gov/vuln/detail/CVE-2022-2286){: external}, [CVE-2022-2287](https://nvd.nist.gov/vuln/detail/CVE-2022-2287){: external}, [CVE-2022-2289](https://nvd.nist.gov/vuln/detail/CVE-2022-2289){: external}, [CVE-2022-27672](https://nvd.nist.gov/vuln/detail/CVE-2022-27672){: external}, [CVE-2022-4269](https://nvd.nist.gov/vuln/detail/CVE-2022-4269){: external}, [CVE-2023-1611](https://nvd.nist.gov/vuln/detail/CVE-2023-1611){: external}, [CVE-2023-2124](https://nvd.nist.gov/vuln/detail/CVE-2023-2124){: external}, [CVE-2023-3090](https://nvd.nist.gov/vuln/detail/CVE-2023-3090){: external}, [CVE-2023-3111](https://nvd.nist.gov/vuln/detail/CVE-2023-3111){: external}, [CVE-2023-3141](https://nvd.nist.gov/vuln/detail/CVE-2023-3141){: external}, [CVE-2023-32629](https://nvd.nist.gov/vuln/detail/CVE-2023-32629){: external}, [CVE-2023-3390](https://nvd.nist.gov/vuln/detail/CVE-2023-3390){: external}, [CVE-2023-35001](https://nvd.nist.gov/vuln/detail/CVE-2023-35001){: external}. |
| Kubernetes | N/A | N/A | N/A |
| Containerd | N/A | N/A | N/A |
{: caption="Changes since version 1.26.7_1546" caption-side="bottom"}


### Change log for worker node fix pack 1.26.7_1546, released 1 August 2023
{: #1267_1546_W}

The following table shows the changes that are in the worker node fix pack 1.26.7_1546. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-212-generic | 4.15.0-214-generic | Worker node kernel & package updates for [CVE-2020-13987](https://nvd.nist.gov/vuln/detail/CVE-2020-13987){: external}, [CVE-2020-13988](https://nvd.nist.gov/vuln/detail/CVE-2020-13988){: external}, [CVE-2020-17437](https://nvd.nist.gov/vuln/detail/CVE-2020-17437){: external}, [CVE-2022-1184](https://nvd.nist.gov/vuln/detail/CVE-2022-1184){: external}, [CVE-2022-3303](https://nvd.nist.gov/vuln/detail/CVE-2022-3303){: external}, [CVE-2023-1611](https://nvd.nist.gov/vuln/detail/CVE-2023-1611){: external}, [CVE-2023-1670](https://nvd.nist.gov/vuln/detail/CVE-2023-1670){: external}, [CVE-2023-1859](https://nvd.nist.gov/vuln/detail/CVE-2023-1859){: external}, [CVE-2023-1990](https://nvd.nist.gov/vuln/detail/CVE-2023-1990){: external}, [CVE-2023-20867](https://nvd.nist.gov/vuln/detail/CVE-2023-20867){: external}, [CVE-2023-2124](https://nvd.nist.gov/vuln/detail/CVE-2023-2124){: external}, [CVE-2023-2828](https://nvd.nist.gov/vuln/detail/CVE-2023-2828){: external}, [CVE-2023-3090](https://nvd.nist.gov/vuln/detail/CVE-2023-3090){: external}, [CVE-2023-3111](https://nvd.nist.gov/vuln/detail/CVE-2023-3111){: external}, [CVE-2023-3141](https://nvd.nist.gov/vuln/detail/CVE-2023-3141){: external}, [CVE-2023-3268](https://nvd.nist.gov/vuln/detail/CVE-2023-3268){: external}, [CVE-2023-3390](https://nvd.nist.gov/vuln/detail/CVE-2023-3390){: external}, [CVE-2023-35001](https://nvd.nist.gov/vuln/detail/CVE-2023-35001){: external}. |
| Ubuntu 20.04 packages | 5.4.0-153-generic | 5.4.0-155-generic | Worker node kernel & package updates for [CVE-2020-13987](https://nvd.nist.gov/vuln/detail/CVE-2020-13987){: external}, [CVE-2020-13988](https://nvd.nist.gov/vuln/detail/CVE-2020-13988){: external}, [CVE-2020-17437](https://nvd.nist.gov/vuln/detail/CVE-2020-17437){: external}, [CVE-2023-20867](https://nvd.nist.gov/vuln/detail/CVE-2023-20867){: external}, [CVE-2023-28321](https://nvd.nist.gov/vuln/detail/CVE-2023-28321){: external}, [CVE-2023-28322](https://nvd.nist.gov/vuln/detail/CVE-2023-28322){: external}, [CVE-2023-3090](https://nvd.nist.gov/vuln/detail/CVE-2023-3090){: external}, [CVE-2023-32629](https://nvd.nist.gov/vuln/detail/CVE-2023-32629){: external}, [CVE-2023-3390](https://nvd.nist.gov/vuln/detail/CVE-2023-3390){: external}, [CVE-2023-35001](https://nvd.nist.gov/vuln/detail/CVE-2023-35001){: external}, [CVE-2023-38408](https://nvd.nist.gov/vuln/detail/CVE-2023-38408){: external}. |
| Kubernetes | 1.26.6 | 1.26.7 | For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.7){: external}. |
| Containerd | 1.6.21 | 1.6.22 | For more information, see the [change logs](https://github.com/containerd/containerd/releases/tag/v1.6.22){: external}. |
{: caption="Changes since version 1.26.6_1544" caption-side="bottom"}


### Change log for master fix pack 1.26.7_1545, released 27 July 2023
{: #1267_1545_M}

The following table shows the changes that are in the master fix pack 1.26.7_1545. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.3.21 | v1.3.23 | Updated `Go` to version `1.19.11` and updated `Go` dependencies. Updated UBI base image. |
| GPU device plug-in and installer | 202b284 | 495931a | Updated `Go` to version `1.20.6`. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.6-1 | v1.26.7-1 | Updated to support the Kubernetes `1.26.4` release. Updated `Go` dependencies and to `Go` version `1.20.6`. |
| Key Management Service provider | v2.6.7 | v2.7.2 | Updated `Go` to version `1.19.11` and updated `Go` dependencies. Updated UBI base image. |
| Konnectivity agent and server | v0.1.2_591_iks | v0.1.3_5_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.1.3){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.21 | 1.22.23 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.23){: external}. |
| Kubernetes | v1.26.6 | v1.26.7 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.7){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2584 | 2631 | Updated `Go` to version `1.19.10` and updated `Go` dependencies. Updated Alpine base image. |
{: caption="Changes since version 1.26.6_1541" caption-side="bottom"}


### Change log for worker node fix pack 1.26.6_1544, released 17 July 2023
{: #1266_1544_W}

The following table shows the changes that are in the worker node fix pack 1.26.6_1544. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Kubernetes | N/A | N/A | N/A |
| Ubuntu 18.04 packages | N/A | N/A | Worker node package updates for [CVE-2023-24626](https://nvd.nist.gov/vuln/detail/CVE-2023-24626){: external}, [CVE-2023-2953](https://nvd.nist.gov/vuln/detail/CVE-2023-2953){: external}. |
| Ubuntu 20.04 packages | N/A | N/A | N/A |
{: caption="Changes since version 1.26.6_1542" caption-side="bottom"}


### Change log for worker node fix pack 1.26.6_1542, released 03 July 2023
{: #1266_1542_W}

The following table shows the changes that are in the worker node fix pack 1.26.6_1542. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | N/A | N/A | Worker node package updates for [CVE-2023-2603](https://nvd.nist.gov/vuln/detail/CVE-2023-2603){: external},[CVE-2023-3138](https://nvd.nist.gov/vuln/detail/CVE-2023-3138){: external}
| Ubuntu 20.04 packages | 5.4.0-150-generic | 5.4.0-153-generic | Worker node kernel & package updates for [CVE-2023-0461](https://nvd.nist.gov/vuln/detail/CVE-2023-0461){: external},[CVE-2023-1380](https://nvd.nist.gov/vuln/detail/CVE-2023-1380){: external},[CVE-2023-1670](https://nvd.nist.gov/vuln/detail/CVE-2023-1670){: external},[CVE-2023-1859](https://nvd.nist.gov/vuln/detail/CVE-2023-1859){: external},[CVE-2023-2612](https://nvd.nist.gov/vuln/detail/CVE-2023-2612){: external},[CVE-2023-2828](https://nvd.nist.gov/vuln/detail/CVE-2023-2828){: external},[CVE-2023-30456](https://nvd.nist.gov/vuln/detail/CVE-2023-30456){: external},[CVE-2023-3138](https://nvd.nist.gov/vuln/detail/CVE-2023-3138){: external},[CVE-2023-31436](https://nvd.nist.gov/vuln/detail/CVE-2023-31436){: external},[CVE-2023-32233](https://nvd.nist.gov/vuln/detail/CVE-2023-32233){: external},[CVE-2023-3297](https://nvd.nist.gov/vuln/detail/CVE-2023-3297){: external}. |
| Kubernetes | 1.26.5 | 1.26.6 |See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/blob/master/CHANGELOG/CHANGELOG-1.26.md){: external}.|
{: caption="Changes since version 1.26.5_1540" caption-side="bottom"}


### Change log for master fix pack 1.26.6_1541, released 27 June 2023
{: #1266_1541_M}

The following table shows the changes that are in the master fix pack 1.26.6_1541. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.3.20 | v1.3.21 | Updated `Go` dependencies and to `Go` version `1.19.10`. |
| etcd | v3.5.8 | v3.5.9 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.9){: external}. |
| Gateway-enabled cluster controller | 2106 | 2322 | Updated image to resolve [CVE-2023-2650](https://nvd.nist.gov/vuln/detail/CVE-2023-2650){: external}. |
| GPU device plug-in and installer | 28d80a0 | 202b284 | Updated to `Go` version `1.19.9` |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.4-7 | v1.26.6-1 | Updated to support the `Kubernetes 1.26.6` release. Updated `Go` dependencies and to `Go` version `1.19.10`. Updated `calicoctl` and `vpcctl`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 431 | 433 | Updated `Go` to version `1.20.4`. Updated UBI base image. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | d842983 | d293d8b | Updated `Go` to version `1.20.5`. Updates to build and base images. |
| Key Management Service provider | v2.6.6 | v2.6.7 | Updated `Go` dependencies and to `Go` version `1.19.10`. |
| Kubernetes | v1.26.5 | v1.26.6 | [CVE-2023-2728](https://nvd.nist.gov/vuln/detail/CVE-2023-2728){: external}. For more information, see [{{site.data.keyword.containerlong_notm}} is affected by a Kubernetes API server security vulnerability (CVE-2023-2728)](https://www.ibm.com/support/pages/node/7011039){: external}. See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.6){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2486 | 2584 | Updated `Go` dependencies and to `Go` version `1.19.9`. Updated base image. |
{: caption="Changes since version 1.26.5_1537" caption-side="bottom"}


### Change log for worker node fix pack 1.26.5_1540, released 19 June 2023
{: #1265_1540_W}

The following table shows the changes that are in the worker node fix pack 1.26.5_1540. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | N/A | N/A | Worker node package updates for [CVE-2020-11080](https://nvd.nist.gov/vuln/detail/CVE-2020-11080){: external},[CVE-2023-24329](https://nvd.nist.gov/vuln/detail/CVE-2023-24329){: external},[CVE-2023-2603](https://nvd.nist.gov/vuln/detail/CVE-2023-2603){: external},[CVE-2023-2609](https://nvd.nist.gov/vuln/detail/CVE-2023-2609){: external},[CVE-2023-2610](https://nvd.nist.gov/vuln/detail/CVE-2023-2610){: external},[CVE-2023-32681](https://nvd.nist.gov/vuln/detail/CVE-2023-32681){: external}
| Ubuntu 20.04 packages | 5.4.0-149-generic | 5.4.0-150-generic | Worker node kernel & package updates for [CVE-2020-11080](https://nvd.nist.gov/vuln/detail/CVE-2020-11080){: external},[CVE-2021-45078](https://nvd.nist.gov/vuln/detail/CVE-2021-45078){: external},[CVE-2023-1380](https://nvd.nist.gov/vuln/detail/CVE-2023-1380){: external},[CVE-2023-1667](https://nvd.nist.gov/vuln/detail/CVE-2023-1667){: external},[CVE-2023-1670](https://nvd.nist.gov/vuln/detail/CVE-2023-1670){: external},[CVE-2023-1859](https://nvd.nist.gov/vuln/detail/CVE-2023-1859){: external},[CVE-2023-2283](https://nvd.nist.gov/vuln/detail/CVE-2023-2283){: external},[CVE-2023-24329](https://nvd.nist.gov/vuln/detail/CVE-2023-24329){: external},[CVE-2023-24593](https://nvd.nist.gov/vuln/detail/CVE-2023-24593){: external},[CVE-2023-2602](https://nvd.nist.gov/vuln/detail/CVE-2023-2602){: external},[CVE-2023-2603](https://nvd.nist.gov/vuln/detail/CVE-2023-2603){: external},[CVE-2023-2609](https://nvd.nist.gov/vuln/detail/CVE-2023-2609){: external},[CVE-2023-2610](https://nvd.nist.gov/vuln/detail/CVE-2023-2610){: external},[CVE-2023-2612](https://nvd.nist.gov/vuln/detail/CVE-2023-2612){: external},[CVE-2023-30456](https://nvd.nist.gov/vuln/detail/CVE-2023-30456){: external},[CVE-2023-3138](https://nvd.nist.gov/vuln/detail/CVE-2023-3138){: external},[CVE-2023-31436](https://nvd.nist.gov/vuln/detail/CVE-2023-31436){: external},[CVE-2023-31484](https://nvd.nist.gov/vuln/detail/CVE-2023-31484){: external},[CVE-2023-32233](https://nvd.nist.gov/vuln/detail/CVE-2023-32233){: external},[CVE-2023-32643](https://nvd.nist.gov/vuln/detail/CVE-2023-32643){: external},[CVE-2023-32681](https://nvd.nist.gov/vuln/detail/CVE-2023-32681){: external}. |
| Kubernetes | N/A |N/A|N/A|
{: caption="Changes since version 1.26.5_1539" caption-side="bottom"}


### Change log for worker node fix pack 1.26.5_1539, released 5 June 2023
{: #1265_1539_W}

The following table shows the changes that are in the worker node fix pack 1.26.5_1539. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-211-generic | 4.15.0-212-generic | Worker node kernel & package updates for [CVE-2019-17595](https://nvd.nist.gov/vuln/detail/CVE-2019-17595){: external}, [CVE-2021-39537](https://nvd.nist.gov/vuln/detail/CVE-2021-39537){: external}, [CVE-2022-29458](https://nvd.nist.gov/vuln/detail/CVE-2022-29458){: external}, [CVE-2022-4304](https://nvd.nist.gov/vuln/detail/CVE-2022-4304){: external}, [CVE-2023-1380](https://nvd.nist.gov/vuln/detail/CVE-2023-1380){: external}, [CVE-2023-25584](https://nvd.nist.gov/vuln/detail/CVE-2023-25584){: external}, [CVE-2023-25585](https://nvd.nist.gov/vuln/detail/CVE-2023-25585){: external}, [CVE-2023-25588](https://nvd.nist.gov/vuln/detail/CVE-2023-25588){: external}, [CVE-2023-2650](https://nvd.nist.gov/vuln/detail/CVE-2023-2650){: external}, [CVE-2023-29491](https://nvd.nist.gov/vuln/detail/CVE-2023-29491){: external}, [CVE-2023-30456](https://nvd.nist.gov/vuln/detail/CVE-2023-30456){: external}, [CVE-2023-31436](https://nvd.nist.gov/vuln/detail/CVE-2023-31436){: external}, [CVE-2023-31484](https://nvd.nist.gov/vuln/detail/CVE-2023-31484){: external}, [CVE-2023-32233](https://nvd.nist.gov/vuln/detail/CVE-2023-32233){: external}. |
| Ubuntu 20.04 packages | 5.4.0-148-generic | 5.4.0-149-generic | Worker node kernel & package updates for [CVE-2021-39537](https://nvd.nist.gov/vuln/detail/CVE-2021-39537){: external}, [CVE-2022-29458](https://nvd.nist.gov/vuln/detail/CVE-2022-29458){: external}, [CVE-2023-1075](https://nvd.nist.gov/vuln/detail/CVE-2023-1075){: external}, [CVE-2023-1118](https://nvd.nist.gov/vuln/detail/CVE-2023-1118){: external}, [CVE-2023-1380](https://nvd.nist.gov/vuln/detail/CVE-2023-1380){: external}, [CVE-2023-25584](https://nvd.nist.gov/vuln/detail/CVE-2023-25584){: external}, [CVE-2023-25585](https://nvd.nist.gov/vuln/detail/CVE-2023-25585){: external}, [CVE-2023-25588](https://nvd.nist.gov/vuln/detail/CVE-2023-25588){: external}, [CVE-2023-2612](https://nvd.nist.gov/vuln/detail/CVE-2023-2612){: external}, [CVE-2023-2650](https://nvd.nist.gov/vuln/detail/CVE-2023-2650){: external}, [CVE-2023-29491](https://nvd.nist.gov/vuln/detail/CVE-2023-29491){: external}, [CVE-2023-30456](https://nvd.nist.gov/vuln/detail/CVE-2023-30456){: external}, [CVE-2023-31436](https://nvd.nist.gov/vuln/detail/CVE-2023-31436){: external}, [CVE-2023-32233](https://nvd.nist.gov/vuln/detail/CVE-2023-32233){: external}. |
| Kubernetes | N/A |N/A|N/A|
{: caption="Changes since version 1.26.5_1538" caption-side="bottom"}


### Change log for master fix pack 1.26.5_1537, released 23 May 2023
{: #1265_1537_M}

The following table shows the changes that are in the master fix pack 1.26.5_1537. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.3.19 | v1.3.20 | Updated `Go` to version `1.19.9` and updated dependencies. Updated the base image. Resolved add-on health bugs. |
| etcd | v3.5.7 | v3.5.8 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.8){: external}. |
| GPU device plug-in | fc4cf22 | 28d80a0 | Updated `Go` to version `1.19.8` |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.4-1 | v1.26.4-7 | Updated support of the Kubernetes 1.26.4 release. Updated Go dependencies. Key rotation. |
| {{site.data.keyword.cloud_notm}} RBAC Operator | 778ef2b | 4e2f346 | Make armada-rbac-sync FIPS compliant |
| Key Management Service provider | v2.6.5 | v2.6.6 | Updated `Go` to version `1.19.9` and updated dependencies. |
| Kubernetes | v1.26.4 | v1.26.5 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.5){: external}. |
| Kubernetes DNS autoscaler | 1.8.6 | v1.8.8 | See the [Kubernetes DNS autoscaler release notes](https://github.com/kubernetes-sigs/cluster-proportional-autoscaler/releases/tag/v1.8.8){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.18 | 1.22.21 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.21){: external}. |
| Portieris admission controller | v0.13.4 | v0.13.5 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.5){: external}. |
{: caption="Changes since version 1.26.4_1535" caption-side="bottom"}


### Change log for worker node fix pack 1.26.5_1538, released 23 May 2023
{: #1265_1538_W}

The following table shows the changes that are in the worker node fix pack 1.26.5_1538. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-210-generic | 4.15.0-211-generic | Worker node kernel & package updates for [CVE-2021-3979](https://nvd.nist.gov/vuln/detail/CVE-2021-3979){: external}, [CVE-2023-1118](https://nvd.nist.gov/vuln/detail/CVE-2023-1118){: external}. |
| Ubuntu 20.04 packages | 5.4.0-139-generic | 5.4.0-148-generic | Worker node kernel & package updates for [CVE-2023-2004](https://nvd.nist.gov/vuln/detail/CVE-2023-2004){: external}. |
| Kubernetes | 1.26.4 |1.26.5| [CVE-2023-2431](https://nvd.nist.gov/vuln/detail/CVE-2023-2431){: external}. For more information, see [{{site.data.keyword.containerlong_notm}} is affected by a kubelet security vulnerability (CVE-2023-2431)](https://www.ibm.com/support/pages/node/7009655){: external}. For more information, see the [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.5){: external}. |
| Containerd | 1.7.0 | 1.7.1 | For more information, see the [change log](https://github.com/containerd/containerd/releases/tag/v1.7.1){: external} and [security bulletin for CVE-2023-28642 and CVE-2023-27561](https://www.ibm.com/support/pages/node/7001317){: external}. |
| Haproxy | N\A | N\A | N\A|
{: caption="Changes since version 1.26.4_1536" caption-side="bottom"}


### Change log for worker node fix pack 1.26.4_1536, released 9 May 2023
{: #1264_1536_W}

The following table shows the changes that are in the worker node fix pack 1.26.4_1536. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-209-generic | 4.15.0-210-generic | Worker node kernel & package updates for [CVE-2023-1786](https://nvd.nist.gov/vuln/detail/CVE-2023-1786){: external}, [CVE-2023-0464](https://nvd.nist.gov/vuln/detail/CVE-2023-0464){: external}, [CVE-2023-0466](https://nvd.nist.gov/vuln/detail/CVE-2023-0466){: external}, [CVE-2023-1829](https://nvd.nist.gov/vuln/detail/CVE-2023-1829){: external}, [CVE-2023-25652](https://nvd.nist.gov/vuln/detail/CVE-2023-25652){: external}, [CVE-2023-25815](https://nvd.nist.gov/vuln/detail/CVE-2023-25815){: external}, [CVE-2023-29007](https://nvd.nist.gov/vuln/detail/CVE-2023-29007){: external}. |
| Ubuntu 20.04 packages | n/a | n/a | Worker node kernel & package updates for [CVE-2023-1786](https://nvd.nist.gov/vuln/detail/CVE-2023-1786){: external}, [CVE-2023-0464](https://nvd.nist.gov/vuln/detail/CVE-2023-0464){: external}, [CVE-2023-0466](https://nvd.nist.gov/vuln/detail/CVE-2023-0466){: external}, [CVE-2023-25652](https://nvd.nist.gov/vuln/detail/CVE-2023-25652){: external}, [CVE-2023-25815](https://nvd.nist.gov/vuln/detail/CVE-2023-25815){: external}, [CVE-2023-29007](https://nvd.nist.gov/vuln/detail/CVE-2023-29007){: external}. |
| Kubernetes |N/A|N/A|N/A|
{: caption="Changes since version 1.26.4_1535" caption-side="bottom"}


### Change log for master fix pack 1.26.4_1535, released 27 April 2023
{: #1264_1535M}

The following table shows the changes that are in the master fix pack 1.26.4_1535. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.25.0 | v3.25.1 | See the [Calico release notes](https://docs.tigera.io/calico/latest/release-notes/#v3.25.1){: external}. |
| Cluster health image | v1.3.17 | v1.3.19 | Updated `Go` to version `1.19.8` and updated dependencies. |
| Gateway-enabled cluster controller | 2024 | 2106 | Support Ubuntu 20 and update image to resolve CVEs. |
| GPU device plug-in | a873e90 | fc4cf22 | Updated `Go` to version `1.19.7`. |
| GPU installer | a873e90 | 28d80a0 | Updated `Go` to version `1.19.8`. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1366 | 1390 | Eliminate IP syscall. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.4.0 | v2.4.5 | Updated universal base image (UBI) to resolve CVEs. Updated `Go` to version `1.19.8` and updated dependencies. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.3-1 | v1.26.4-1 | Updated to support the Kubernetes `1.26.4` release. Updated `Go` dependencies and to `Go` version `1.19.8`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 429 | 431 | Updated `Go` to version `1.19.8` and updated dependencies. Update UBI base image. |
| {{site.data.keyword.cloud_notm}} Metrics Server Config Watcher | N/A | d842983 | New component with multi-architecture support that replaces the existing metrics server configuration watcher. |
| Key Management Service provider | v2.6.4 | v2.6.5 | Updated `Go` to version `1.19.7` and updated dependencies. |
| Konnectivity agent and server | v0.1.1_569_iks | v0.1.2_591_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.1.2){: external}. Updated configuration to set `keepalive-time` to `40s`. |
| Kubernetes | v1.26.3 | v1.26.4 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.4){: external}. |
| Kubernetes Metrics Server configuration | N/A | N/A | Updated to use TLS version 1.3 ciphers. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2420 | 2486 | Updated `Go` to version `1.19.7` and updated dependencies. |
| Portieris admission controller | v0.13.3 | v0.13.4 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.4){: external}. |
{: caption="Changes since version 1.26.3_1531" caption-side="bottom"}


### Change log for worker node fix pack 1.26.4_1535, released 24 April 2023
{: #1264_1535}

The following table shows the changes that are in the worker node fix pack 1.26.4_1535. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-208-generic | 4.15.0-209-generic | Worker node package updates for  [CVE-2021-4192](https://nvd.nist.gov/vuln/detail/CVE-2021-4192){: external}, [CVE-2021-4193](https://nvd.nist.gov/vuln/detail/CVE-2021-4193){: external}, [CVE-2022-0213](https://nvd.nist.gov/vuln/detail/CVE-2022-0213){: external}, [CVE-2022-0261](https://nvd.nist.gov/vuln/detail/CVE-2022-0261){: external}, [CVE-2022-0318](https://nvd.nist.gov/vuln/detail/CVE-2022-0318){: external}, [CVE-2022-0319](https://nvd.nist.gov/vuln/detail/CVE-2022-0319){: external}, [CVE-2022-0351](https://nvd.nist.gov/vuln/detail/CVE-2022-0351){: external}, [CVE-2022-0359](https://nvd.nist.gov/vuln/detail/CVE-2022-0359){: external}, [CVE-2022-0361](https://nvd.nist.gov/vuln/detail/CVE-2022-0361){: external}, [CVE-2022-0368](https://nvd.nist.gov/vuln/detail/CVE-2022-0368){: external}, [CVE-2022-0408](https://nvd.nist.gov/vuln/detail/CVE-2022-0408){: external}, [CVE-2022-0443](https://nvd.nist.gov/vuln/detail/CVE-2022-0443){: external}, [CVE-2022-0554](https://nvd.nist.gov/vuln/detail/CVE-2022-0554){: external}, [CVE-2022-0572](https://nvd.nist.gov/vuln/detail/CVE-2022-0572){: external}, [CVE-2022-0685](https://nvd.nist.gov/vuln/detail/CVE-2022-0685){: external}, [CVE-2022-0714](https://nvd.nist.gov/vuln/detail/CVE-2022-0714){: external}, [CVE-2022-0729](https://nvd.nist.gov/vuln/detail/CVE-2022-0729){: external}, [CVE-2022-2207](https://nvd.nist.gov/vuln/detail/CVE-2022-2207){: external}, [CVE-2022-3903](https://nvd.nist.gov/vuln/detail/CVE-2022-3903){: external}, [CVE-2023-1281](https://nvd.nist.gov/vuln/detail/CVE-2023-1281){: external}, [CVE-2023-1326](https://nvd.nist.gov/vuln/detail/CVE-2023-1326){: external}, [CVE-2023-26545](https://nvd.nist.gov/vuln/detail/CVE-2023-26545){: external}, [CVE-2023-28450](https://nvd.nist.gov/vuln/detail/CVE-2023-28450){: external}, [CVE-2023-28484](https://nvd.nist.gov/vuln/detail/CVE-2023-28484){: external}, [CVE-2023-28486](https://nvd.nist.gov/vuln/detail/CVE-2023-28486){: external}, [CVE-2023-28487](https://nvd.nist.gov/vuln/detail/CVE-2023-28487){: external}, [CVE-2023-29469](https://nvd.nist.gov/vuln/detail/CVE-2023-29469){: external}. |
| Ubuntu 20.04 packages |N/A|N/A| Worker node package updates for [CVE-2021-4166](https://nvd.nist.gov/vuln/detail/CVE-2021-4166){: external}, [CVE-2021-4192](https://nvd.nist.gov/vuln/detail/CVE-2021-4192){: external}, [CVE-2021-4193](https://nvd.nist.gov/vuln/detail/CVE-2021-4193){: external}, [CVE-2022-0213](https://nvd.nist.gov/vuln/detail/CVE-2022-0213){: external}, [CVE-2022-0261](https://nvd.nist.gov/vuln/detail/CVE-2022-0261){: external}, [CVE-2022-0318](https://nvd.nist.gov/vuln/detail/CVE-2022-0318){: external}, [CVE-2022-0319](https://nvd.nist.gov/vuln/detail/CVE-2022-0319){: external}, [CVE-2022-0351](https://nvd.nist.gov/vuln/detail/CVE-2022-0351){: external}, [CVE-2022-0359](https://nvd.nist.gov/vuln/detail/CVE-2022-0359){: external}, [CVE-2022-0361](https://nvd.nist.gov/vuln/detail/CVE-2022-0361){: external}, [CVE-2022-0368](https://nvd.nist.gov/vuln/detail/CVE-2022-0368){: external}, [CVE-2022-0408](https://nvd.nist.gov/vuln/detail/CVE-2022-0408){: external}, [CVE-2022-0443](https://nvd.nist.gov/vuln/detail/CVE-2022-0443){: external}, [CVE-2022-0554](https://nvd.nist.gov/vuln/detail/CVE-2022-0554){: external}, [CVE-2022-0572](https://nvd.nist.gov/vuln/detail/CVE-2022-0572){: external}, [CVE-2022-0629](https://nvd.nist.gov/vuln/detail/CVE-2022-0629){: external}, [CVE-2022-0685](https://nvd.nist.gov/vuln/detail/CVE-2022-0685){: external}, [CVE-2022-0714](https://nvd.nist.gov/vuln/detail/CVE-2022-0714){: external}, [CVE-2022-0729](https://nvd.nist.gov/vuln/detail/CVE-2022-0729){: external}, [CVE-2022-2207](https://nvd.nist.gov/vuln/detail/CVE-2022-2207){: external}, [CVE-2022-3108](https://nvd.nist.gov/vuln/detail/CVE-2022-3108){: external}, [CVE-2022-3903](https://nvd.nist.gov/vuln/detail/CVE-2022-3903){: external}, [CVE-2023-1281](https://nvd.nist.gov/vuln/detail/CVE-2023-1281){: external}, [CVE-2023-1326](https://nvd.nist.gov/vuln/detail/CVE-2023-1326){: external}, [CVE-2023-26545](https://nvd.nist.gov/vuln/detail/CVE-2023-26545){: external}, [CVE-2023-28484](https://nvd.nist.gov/vuln/detail/CVE-2023-28484){: external}, [CVE-2023-28486](https://nvd.nist.gov/vuln/detail/CVE-2023-28486){: external}, [CVE-2023-28487](https://nvd.nist.gov/vuln/detail/CVE-2023-28487){: external}, [CVE-2023-29469](https://nvd.nist.gov/vuln/detail/CVE-2023-29469){: external}. |
| Kubernetes | 1.26.3 | 1.26.4 | See [change logs](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.4){: external}. |
| Containerd |N/A|N/A|N/A|
| Haproxy |N/A|N/A|N/A|
{: caption="Changes since version 1.26.3_1533" caption-side="bottom"}


### Change log for worker node fix pack 1.26.3_1533, released 11 April 2023
{: #1263_1533}

The following table shows the changes that are in the worker node fix pack 1.26.3_1533. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-206 | 4.15.0-208 | Worker node kernel & package updates for [CVE-2021-3669](https://nvd.nist.gov/vuln/detail/CVE-2021-3669){: external}, [CVE-2022-0413](https://nvd.nist.gov/vuln/detail/CVE-2022-0413){: external}, [CVE-2022-1629](https://nvd.nist.gov/vuln/detail/CVE-2022-1629){: external}, [CVE-2022-1674](https://nvd.nist.gov/vuln/detail/CVE-2022-1674){: external}, [CVE-2022-1720](https://nvd.nist.gov/vuln/detail/CVE-2022-1720){: external}, [CVE-2022-1733](https://nvd.nist.gov/vuln/detail/CVE-2022-1733){: external}, [CVE-2022-1735](https://nvd.nist.gov/vuln/detail/CVE-2022-1735){: external}, [CVE-2022-1785](https://nvd.nist.gov/vuln/detail/CVE-2022-1785){: external}, [CVE-2022-1796](https://nvd.nist.gov/vuln/detail/CVE-2022-1796){: external}, [CVE-2022-1851](https://nvd.nist.gov/vuln/detail/CVE-2022-1851){: external}, [CVE-2022-1898](https://nvd.nist.gov/vuln/detail/CVE-2022-1898){: external}, [CVE-2022-1942](https://nvd.nist.gov/vuln/detail/CVE-2022-1942){: external}, [CVE-2022-1968](https://nvd.nist.gov/vuln/detail/CVE-2022-1968){: external}, [CVE-2022-2124](https://nvd.nist.gov/vuln/detail/CVE-2022-2124){: external}, [CVE-2022-2125](https://nvd.nist.gov/vuln/detail/CVE-2022-2125){: external}, [CVE-2022-2126](https://nvd.nist.gov/vuln/detail/CVE-2022-2126){: external}, [CVE-2022-2129](https://nvd.nist.gov/vuln/detail/CVE-2022-2129){: external}, [CVE-2022-2175](https://nvd.nist.gov/vuln/detail/CVE-2022-2175){: external}, [CVE-2022-2183](https://nvd.nist.gov/vuln/detail/CVE-2022-2183){: external}, [CVE-2022-2206](https://nvd.nist.gov/vuln/detail/CVE-2022-2206){: external}, [CVE-2022-2304](https://nvd.nist.gov/vuln/detail/CVE-2022-2304){: external}, [CVE-2022-2345](https://nvd.nist.gov/vuln/detail/CVE-2022-2345){: external}, [CVE-2022-2571](https://nvd.nist.gov/vuln/detail/CVE-2022-2571){: external}, [CVE-2022-2581](https://nvd.nist.gov/vuln/detail/CVE-2022-2581){: external}, [CVE-2022-2845](https://nvd.nist.gov/vuln/detail/CVE-2022-2845){: external}, [CVE-2022-2849](https://nvd.nist.gov/vuln/detail/CVE-2022-2849){: external}, [CVE-2022-2923](https://nvd.nist.gov/vuln/detail/CVE-2022-2923){: external}, [CVE-2022-2946](https://nvd.nist.gov/vuln/detail/CVE-2022-2946){: external}, [CVE-2022-41218](https://nvd.nist.gov/vuln/detail/CVE-2022-41218){: external}, [CVE-2023-0045](https://nvd.nist.gov/vuln/detail/CVE-2023-0045){: external}, [CVE-2023-0266](https://nvd.nist.gov/vuln/detail/CVE-2023-0266){: external}, [CVE-2023-23559](https://nvd.nist.gov/vuln/detail/CVE-2023-23559){: external}. |
| Ubuntu 20.04 packages |N/A|N/A| Worker node package updates for [CVE-2022-0413](https://nvd.nist.gov/vuln/detail/CVE-2022-0413){: external}, [CVE-2022-1629](https://nvd.nist.gov/vuln/detail/CVE-2022-1629){: external}, [CVE-2022-1674](https://nvd.nist.gov/vuln/detail/CVE-2022-1674){: external}, [CVE-2022-1720](https://nvd.nist.gov/vuln/detail/CVE-2022-1720){: external}, [CVE-2022-1733](https://nvd.nist.gov/vuln/detail/CVE-2022-1733){: external}, [CVE-2022-1735](https://nvd.nist.gov/vuln/detail/CVE-2022-1735){: external}, [CVE-2022-1785](https://nvd.nist.gov/vuln/detail/CVE-2022-1785){: external}, [CVE-2022-1796](https://nvd.nist.gov/vuln/detail/CVE-2022-1796){: external}, [CVE-2022-1851](https://nvd.nist.gov/vuln/detail/CVE-2022-1851){: external}, [CVE-2022-1898](https://nvd.nist.gov/vuln/detail/CVE-2022-1898){: external}, [CVE-2022-1927](https://nvd.nist.gov/vuln/detail/CVE-2022-1927){: external}, [CVE-2022-1942](https://nvd.nist.gov/vuln/detail/CVE-2022-1942){: external}, [CVE-2022-1968](https://nvd.nist.gov/vuln/detail/CVE-2022-1968){: external}, [CVE-2022-2124](https://nvd.nist.gov/vuln/detail/CVE-2022-2124){: external}, [CVE-2022-2125](https://nvd.nist.gov/vuln/detail/CVE-2022-2125){: external}, [CVE-2022-2126](https://nvd.nist.gov/vuln/detail/CVE-2022-2126){: external}, [CVE-2022-2129](https://nvd.nist.gov/vuln/detail/CVE-2022-2129){: external}, [CVE-2022-2175](https://nvd.nist.gov/vuln/detail/CVE-2022-2175){: external}, [CVE-2022-2183](https://nvd.nist.gov/vuln/detail/CVE-2022-2183){: external}, [CVE-2022-2206](https://nvd.nist.gov/vuln/detail/CVE-2022-2206){: external}, [CVE-2022-2304](https://nvd.nist.gov/vuln/detail/CVE-2022-2304){: external}, [CVE-2022-2344](https://nvd.nist.gov/vuln/detail/CVE-2022-2344){: external}, [CVE-2022-2345](https://nvd.nist.gov/vuln/detail/CVE-2022-2345){: external}, [CVE-2022-2571](https://nvd.nist.gov/vuln/detail/CVE-2022-2571){: external}, [CVE-2022-2581](https://nvd.nist.gov/vuln/detail/CVE-2022-2581){: external}, [CVE-2022-2845](https://nvd.nist.gov/vuln/detail/CVE-2022-2845){: external}, [CVE-2022-2849](https://nvd.nist.gov/vuln/detail/CVE-2022-2849){: external}, [CVE-2022-2923](https://nvd.nist.gov/vuln/detail/CVE-2022-2923){: external}, [CVE-2022-2946](https://nvd.nist.gov/vuln/detail/CVE-2022-2946){: external}, [CVE-2022-2980](https://nvd.nist.gov/vuln/detail/CVE-2022-2980){: external}. Updated `sysctl` setting for `fs.inotify.max_user_instances` from default `128` to `1024`. |
| Kubernetes |N/A|N/A|N/A|
| Haproxy | 8398d1 | 8895ad | [CVE-2023-0361](https://nvd.nist.gov/vuln/detail/CVE-2023-0361){: external}. |
| Containerd |N/A|N/A|N/A|
{: caption="Changes since version 1.26.3_1531" caption-side="bottom"}


### Change log for worker node fix pack 1.26.3_1531, released 29 March 2023
{: #1263_1531}

The following table shows the changes that are in the worker node fix pack 1.26.3_1531. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-144 | 5.4.0-139 | Downgrading kernel to address [Upstream canonical bug](https://bugs.launchpad.net/ubuntu/+source/linux/+bug/2009325){: external}. |
{: caption="Changes since version 1.26.3_1529" caption-side="bottom"}


### Change log for master fix pack 1.26.3_1528, released 28 March 2023
{: #1263_1528}

The following table shows the changes that are in the master fix pack 1.26.3_1528. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Cluster health image | v1.3.16 | v1.3.17 | Updated `Go` to version `1.19.7` and updated dependencies. |
| GPU device plug-in and installer | 79a2232 | a873e90 | Updated `Go` to version `1.19.6`. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1308-amd64 | 1366-amd64 | Updated to resolve [CVE-2023-23916](https://nvd.nist.gov/vuln/detail/CVE-2023-23916){: external}. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.3.7 | v2.4.0 | Removed ExpandInUsePersistentVolumes feature gate. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.1-16 | v1.26.3-1 | Updated to support the `Kubernetes 1.26.3` release. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 427 | 429 | Updated universal base image (UBI) to resolve CVEs. Updated `Go` to version `1.19.6` and updated dependencies. |
| Key Management Service provider | v2.6.3 | v2.6.4 | Updated `Go` to version `1.19.7` and updated dependencies. |
| Kubernetes | v1.26.1 | v1.26.3 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.3){: external}. |
| Kubernetes Dashboard metrics scraper | v1.0.8 | v1.0.9 | See the [Kubernetes Dashboard metrics scraper release notes](https://github.com/kubernetes-sigs/dashboard-metrics-scraper/releases/tag/v1.0.9){: external}. |
| Load balancer and load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2383 | 2420 | Updated the image to resolve CVEs. |
{: caption="Changes since version 1.26.1_1524" caption-side="bottom"}


### Change log for worker node fix pack 1.26.3_1529, released 27 March 2023
{: #1263_1529}

The following table shows the changes that are in the worker node fix pack 1.26.3_1529. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages |N/A|N/A| Worker node package updates for [CVE-2021-36222](https://nvd.nist.gov/vuln/detail/CVE-2021-36222){: external}, [CVE-2021-37750](https://nvd.nist.gov/vuln/detail/CVE-2021-37750){: external}, [CVE-2022-47024](https://nvd.nist.gov/vuln/detail/CVE-2022-47024){: external}, [CVE-2023-0049](https://nvd.nist.gov/vuln/detail/CVE-2023-0049){: external}, [CVE-2023-0054](https://nvd.nist.gov/vuln/detail/CVE-2023-0054){: external}, [CVE-2023-0288](https://nvd.nist.gov/vuln/detail/CVE-2023-0288){: external}, [CVE-2023-0433](https://nvd.nist.gov/vuln/detail/CVE-2023-0433){: external}, [CVE-2023-1170](https://nvd.nist.gov/vuln/detail/CVE-2023-1170){: external}, [CVE-2023-1175](https://nvd.nist.gov/vuln/detail/CVE-2023-1175){: external}, [CVE-2023-24329](https://nvd.nist.gov/vuln/detail/CVE-2023-24329){: external}, [CVE-2023-27533](https://nvd.nist.gov/vuln/detail/CVE-2023-27533){: external}, [CVE-2023-27534](https://nvd.nist.gov/vuln/detail/CVE-2023-27534){: external}, [CVE-2023-27535](https://nvd.nist.gov/vuln/detail/CVE-2023-27535){: external}, [CVE-2023-27536](https://nvd.nist.gov/vuln/detail/CVE-2023-27536){: external}, [CVE-2023-27538](https://nvd.nist.gov/vuln/detail/CVE-2023-27538){: external}. |
| Ubuntu 20.04 packages |N/A|N/A| Worker node package updates for [CVE-2021-36222](https://nvd.nist.gov/vuln/detail/CVE-2021-36222){: external}, [CVE-2021-37750](https://nvd.nist.gov/vuln/detail/CVE-2021-37750){: external}, [CVE-2022-47024](https://nvd.nist.gov/vuln/detail/CVE-2022-47024){: external}, [CVE-2023-0049](https://nvd.nist.gov/vuln/detail/CVE-2023-0049){: external}, [CVE-2023-0054](https://nvd.nist.gov/vuln/detail/CVE-2023-0054){: external}, [CVE-2023-0288](https://nvd.nist.gov/vuln/detail/CVE-2023-0288){: external}, [CVE-2023-0433](https://nvd.nist.gov/vuln/detail/CVE-2023-0433){: external}, [CVE-2023-1170](https://nvd.nist.gov/vuln/detail/CVE-2023-1170){: external}, [CVE-2023-1175](https://nvd.nist.gov/vuln/detail/CVE-2023-1175){: external}, [CVE-2023-1264](https://nvd.nist.gov/vuln/detail/CVE-2023-1264){: external}, [CVE-2023-24329](https://nvd.nist.gov/vuln/detail/CVE-2023-24329){: external}, [CVE-2023-27533](https://nvd.nist.gov/vuln/detail/CVE-2023-27533){: external}, [CVE-2023-27534](https://nvd.nist.gov/vuln/detail/CVE-2023-27534){: external}, [CVE-2023-27535](https://nvd.nist.gov/vuln/detail/CVE-2023-27535){: external}, [CVE-2023-27536](https://nvd.nist.gov/vuln/detail/CVE-2023-27536){: external}, [CVE-2023-27538](https://nvd.nist.gov/vuln/detail/CVE-2023-27538){: external}. |
| Kubernetes | 1.26.1 | 1.26.3 | For more information, see the [change log](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.3){: external}. |
| Containerd | 1.7.0-rc.3 | 1.7.0 | For more information, see the [change log](https://github.com/containerd/containerd/releases/tag/v1.7.0){: external}. |
| Haproxy | af5031 | 8398d1 | [CVE-2023-23916](https://nvd.nist.gov/vuln/detail/CVE-2023-23916){: external}. |
{: caption="Changes since version 1.26.1_1525" caption-side="bottom"}


### Change log for worker node fix pack 1.26.1_1525, released 13 March 2023
{: #1261_1525}

The following table shows the changes that are in the worker node fix pack 1.26.1_1525. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 20.04 packages | 5.4.0-139 | 5.4.0-144 | Worker node kernel & package updates for [CVE-2022-29154](https://nvd.nist.gov/vuln/detail/CVE-2022-29154){: external}, [CVE-2022-3545](https://nvd.nist.gov/vuln/detail/CVE-2022-3545){: external}, [CVE-2022-3821](https://nvd.nist.gov/vuln/detail/CVE-2022-3821){: external}, [CVE-2022-40898](https://nvd.nist.gov/vuln/detail/CVE-2022-40898){: external}, [CVE-2022-41218](https://nvd.nist.gov/vuln/detail/CVE-2022-41218){: external}, [CVE-2022-4139](https://nvd.nist.gov/vuln/detail/CVE-2022-4139){: external}, [CVE-2022-4415](https://nvd.nist.gov/vuln/detail/CVE-2022-4415){: external}, [CVE-2022-47520](https://nvd.nist.gov/vuln/detail/CVE-2022-47520){: external}, [CVE-2022-48303](https://nvd.nist.gov/vuln/detail/CVE-2022-48303){: external}, [CVE-2023-0266](https://nvd.nist.gov/vuln/detail/CVE-2023-0266){: external}, [CVE-2023-0361](https://nvd.nist.gov/vuln/detail/CVE-2023-0361){: external}, [CVE-2023-0461](https://nvd.nist.gov/vuln/detail/CVE-2023-0461){: external}, [CVE-2023-0767](https://nvd.nist.gov/vuln/detail/CVE-2023-0767){: external}, [CVE-2023-23916](https://nvd.nist.gov/vuln/detail/CVE-2023-23916){: external}. |
| Ubuntu 18.04 packages | 4.15.0-204 | 4.15.0-206 | Worker node kernel & package updates for [CVE-2022-29154](https://nvd.nist.gov/vuln/detail/CVE-2022-29154){: external}, [CVE-2022-3545](https://nvd.nist.gov/vuln/detail/CVE-2022-3545){: external}, [CVE-2022-3628](https://nvd.nist.gov/vuln/detail/CVE-2022-3628){: external}, [CVE-2022-37454](https://nvd.nist.gov/vuln/detail/CVE-2022-37454){: external}, [CVE-2022-3821](https://nvd.nist.gov/vuln/detail/CVE-2022-3821){: external}, [CVE-2022-40898](https://nvd.nist.gov/vuln/detail/CVE-2022-40898){: external}, [CVE-2022-48303](https://nvd.nist.gov/vuln/detail/CVE-2022-48303){: external}, [CVE-2023-0461](https://nvd.nist.gov/vuln/detail/CVE-2023-0461){: external}, [CVE-2023-0767](https://nvd.nist.gov/vuln/detail/CVE-2023-0767){: external}, [CVE-2023-22490](https://nvd.nist.gov/vuln/detail/CVE-2023-22490){: external}, [CVE-2023-23916](https://nvd.nist.gov/vuln/detail/CVE-2023-23916){: external}. |
| Kubernetes |N/A|N/A|N/A|
| Containerd | 1.7.0-rc.1 | 1.7.0-rc.3 | For more information, see the [change log](https://github.com/containerd/containerd/releases/tag/v1.7.0-rc.3){: external}. |
{: caption="Changes since version 1.26.1_1522" caption-side="bottom"}


### Change log for master fix pack 1.26.1_1524, released 2 March 2023
{: #1261_1524}

The following table shows the changes that are in the master fix pack 1.26.1_1524. Master patch updates are applied automatically. 



| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico | v3.24.5 | v3.25.0 | See the [Calico release notes](https://docs.tigera.io/archive/v3.24/release-notes/#v3245){: external}. |
| Cluster health image | v1.3.15 | v1.3.16 | Updated `Go` dependencies and to `Go` version `1.19.6`. Updated universal base image (UBI) to resolve CVEs. |
| CoreDNS | 1.10.0 | 1.10.1 | See the [CoreDNS release notes](https://coredns.io/tags/notes/){: external}. |
| etcd | v3.5.6 | v3.5.7 | See the [etcd release notes](https://github.com/etcd-io/etcd/releases/v3.5.7){: external}. |
| {{site.data.keyword.IBM_notm}} Calico extension | 1305-amd64 | 1308-amd64 | Updated universal base image (UBI) to resolve [CVE-2022-47629](https://nvd.nist.gov/vuln/detail/CVE-2022-47629){: external}. |
| {{site.data.keyword.cloud_notm}} Block Storage driver and plug-in | v2.3.6 | v2.3.7 | Updated universal base image (UBI) to resolve CVEs. |
| {{site.data.keyword.cloud_notm}} Controller Manager | v1.26.1-2 | v1.26.1-16 | Updated `Go` dependencies. Updated `k8s.io/utils` digest to `a5ecb01`. |
| {{site.data.keyword.filestorage_full_notm}} plug-in and monitor | 425 | 427 | Updated universal base image (UBI) to resolve CVEs. |
| Gateway-enabled cluster controller | 1902 | 1987 | Updated `armada-utils` to version `v1.9.35` |
| Key Management Service provider | v2.6.2 | v2.6.3 | Updated `Go` dependencies and to `Go` version `1.19.6`. |
| Konnectivity agent | v0.1.0_503_iks | v0.1.1_569_iks | Updated to Konnectivity version v0.1.1. |
| Kubernetes NodeLocal DNS cache | 1.22.15 | 1.22.18 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.18){: external}. |
| Load balancer and Load balancer monitor for {{site.data.keyword.cloud_notm}} Provider | 2325 | 2383 | Updated to `armada-utils` version `1.9.35`. |
| Portieris admission controller | v0.12.6 | v0.13.3 | See the [Portieris admission controller release notes](https://github.com/{{site.data.keyword.IBM_notm}}/portieris/releases/tag/v0.13.3){: external}. |
{: caption="Changes since version 1.26.1_1519" caption-side="bottom"}


### Change log for worker node fix pack 1.26.1_1522, released 27 February 2023
{: #1261_1522}

The following table shows the changes that are in the worker node fix pack 1.26.1_1522. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
|containerd| v1.6.17| v1.6.18| See the [1.6.18 change log](https://github.com/containerd/containerd/releases/tag/v1.6.18){: external} and the [security bulletin for CVE-2023-25153 and CVE-2023-25173](https://www.ibm.com/support/pages/node/6960181){: external}. |
| Ubuntu 18.04 packages |N/A|N/A| Worker node package updates for [CVE-2023-22490](https://nvd.nist.gov/vuln/detail/CVE-2023-22490){: external}, [CVE-2023-23946](https://nvd.nist.gov/vuln/detail/CVE-2023-23946){: external}, [CVE-2023-25725](https://nvd.nist.gov/vuln/detail/CVE-2023-25725){: external}. |
| Ubuntu 20.04 packages |N/A|N/A| Worker node package updates for [CVE-2023-22490](https://nvd.nist.gov/vuln/detail/CVE-2023-22490){: external}, [CVE-2023-23946](https://nvd.nist.gov/vuln/detail/CVE-2023-23946){: external}, [CVE-2023-25725](https://nvd.nist.gov/vuln/detail/CVE-2023-25725){: external}. |
| Kubernetes |N/A|N/A|N/A|
| HAProxy | d38f89 | af5031 | [CVE-2022-40897](https://nvd.nist.gov/vuln/detail/CVE-2022-40897){: external}, [CVE-2022-4415](https://nvd.nist.gov/vuln/detail/CVE-2022-4415){: external}, [CVE-2020-10735](https://nvd.nist.gov/vuln/detail/CVE-2020-10735){: external}, [CVE-2021-28861](https://nvd.nist.gov/vuln/detail/CVE-2021-28861){: external}, [CVE-2022-45061](https://nvd.nist.gov/vuln/detail/CVE-2022-45061){: external}. |
| Default Worker Pool | Ubuntu 18 | Ubuntu 20| For {{site.data.keyword.containerlong_notm}}, default worker-pool is created with Ubuntu 20 Operating system |
{: caption="Changes since version 1.26.1_1521" caption-side="bottom"}


### Change log for worker node fix pack 1.26.1_1521, released 13 February 2023
{: #1261_1521}

The following table shows the changes that are in the worker node fix pack 1.26.1_1521. Worker node patch updates can be applied by updating, reloading (in classic infrastructure), or replacing (in VPC infrastructure) the worker node.
{: shortdesc}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Ubuntu 18.04 packages | 4.15.0-202 | 4.15.0-204 | Worker node kernel & package updates for [CVE-2022-28321](https://nvd.nist.gov/vuln/detail/CVE-2022-28321){: external}, [CVE-2022-3437](https://nvd.nist.gov/vuln/detail/CVE-2022-3437){: external}, [CVE-2022-4304](https://nvd.nist.gov/vuln/detail/CVE-2022-4304){: external}, [CVE-2022-4450](https://nvd.nist.gov/vuln/detail/CVE-2022-4450){: external}, [CVE-2022-45142](https://nvd.nist.gov/vuln/detail/CVE-2022-45142){: external}, [CVE-2022-47016](https://nvd.nist.gov/vuln/detail/CVE-2022-47016){: external}, [CVE-2023-0215](https://nvd.nist.gov/vuln/detail/CVE-2023-0215){: external}, [CVE-2023-0286](https://nvd.nist.gov/vuln/detail/CVE-2023-0286){: external}. |
| Ubuntu 20.04 packages | 5.4.0-137 | 5.4.0-139 | Worker node kernel & package updates for [CVE-2022-28321](https://nvd.nist.gov/vuln/detail/CVE-2022-28321){: external}, [CVE-2022-3437](https://nvd.nist.gov/vuln/detail/CVE-2022-3437){: external}, [CVE-2022-4304](https://nvd.nist.gov/vuln/detail/CVE-2022-4304){: external}, [CVE-2022-4450](https://nvd.nist.gov/vuln/detail/CVE-2022-4450){: external}, [CVE-2022-45142](https://nvd.nist.gov/vuln/detail/CVE-2022-45142){: external}, [CVE-2022-47016](https://nvd.nist.gov/vuln/detail/CVE-2022-47016){: external}, [CVE-2023-0215](https://nvd.nist.gov/vuln/detail/CVE-2023-0215){: external}, [CVE-2023-0286](https://nvd.nist.gov/vuln/detail/CVE-2023-0286){: external}. |
| Kubernetes |N/A|N/A|N/A|
| HAProxy | 8d6ea6 | 08c969 | [CVE-2022-47629](https://nvd.nist.gov/vuln/detail/CVE-2022-47629){: external}. |
{: caption="Changes since version 1.26.1_1520" caption-side="bottom"}


### Change log for master fix pack 1.26.1_1519 and worker node fix pack 1.26.1_1520, released 1 February 2023
{: #1261_1519_and_1261_1520}

| Component | Previous | Current | Description |
| --- | --- | --- | --- |
| Calico configuration | N/A | N/A | Calico configuration now sets a [BGP password](https://docs.tigera.io/calico/latest/reference/resources/bgppeer#bgppassword){: external} and container network sysctl tuning for `net.ipv4.tcp_keepalive_intvl` to `15`, `net.ipv4.tcp_keepalive_probes` to `6` and `net.ipv4.tcp_keepalive_time` to `40`.  |
| containerd | v1.6.16 | v1.7.0-beta.2 | See the [containerd release notes](https://github.com/containerd/containerd/releases/tag/v1.7.0-beta.2){: external}. In addition, the image pull progress timeout has been configured to 5 minutes. |
| IBM Cloud Controller Manager | v1.25.6-2 | v1.26.1-2 | Updated to support the Kubernetes `1.26.1` release. Updated `Go` dependencies and to `Go` version `1.19.5`. VPC load balancer creation now honors a user specified name. VPC load balancer update now handles an empty default pool name. |
| Key Management Service provider | v2.5.13 | v2.6.2 | Delayed KMS pod termination until the Kubernetes API server terminates. Updated `Go` dependencies and to `Go` version `1.19.4`. |
| Konnectivity agent and server | v0.0.34_491_iks | v0.1.0_503_iks | See the [Konnectivity release notes](https://github.com/kubernetes-sigs/apiserver-network-proxy/releases/tag/v0.1.0){: external}. |
| Kubernetes | v1.25.6 | v1.26.1 | See the [Kubernetes release notes](https://github.com/kubernetes/kubernetes/releases/tag/v1.26.1){: external}. |
| Kubernetes configuration | N/A | N/A | Updated the [kube-proxy configuration](/docs/containers?topic=containers-service-settings#kube-proxy){: external}. |
| Kubernetes add-on resizer | 1.8.15 | 1.8.16 | See the [Kubernetes add-on resizer release notes](https://github.com/kubernetes/autoscaler/releases/tag/addon-resizer-1.8.16){: external}. In addition, a liveness probe has been configured to improve availability. |
| Kubernetes DNS autoscaler configuration | N/A | N/A | Memory resource requests were increased from `5Mi` to `7Mi` to better align with normal resource utilization. In addition, a liveness probe has been configured to improve availability. |
| Kubernetes Metrics Server | v0.6.0 | v0.6.2 | See the [Kubernetes Metrics Server release notes](https://github.com/kubernetes-sigs/metrics-server/releases/tag/v0.6.2){: external}. |
| Kubernetes NodeLocal DNS cache | 1.22.13 | 1.22.15 | See the [Kubernetes NodeLocal DNS cache release notes](https://github.com/kubernetes/dns/releases/tag/1.22.15){: external}. |
| Pause container image | 3.8 | 3.9 | See the [pause container image release notes](https://github.com/kubernetes/kubernetes/blob/master/build/pause/CHANGELOG.md){: external}. |
{: caption="Changes since version 1.25." caption-side="bottom"}


