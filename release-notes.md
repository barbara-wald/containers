---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-30"


keywords: containers, {{site.data.keyword.containerlong_notm}}, kubernetes, release notes

subcollection: containers

content-type: release-note

---

{{site.data.keyword.attribute-definition-list}}


# Release notes
{: #containers-relnotes}

Use the release notes to learn about the latest changes to the documentation that are grouped by month.
{: shortdesc}

Looking for {{site.data.keyword.cloud_notm}} status, platform announcements, security bulletins, or maintenance notifications? See [{{site.data.keyword.cloud_notm}} status](https://cloud.ibm.com/status?selected=status).
{: tip}

## May 2024
{: #containers-may24}





### 30 May 2024
{: #containers-may3024}
{: release-note}

Ingress ALB updates are available for {{site.data.keyword.containerlong_notm}}.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 29 May 2024
{: #containers-may2924}
{: release-note}



New! {{site.data.keyword.containerlong_notm}} version 1.30.
:   You can now create or [update clusters to Kubernetes version 1.30](/docs/containers?topic=containers-cs_versions_130). With Kubernetes 1.30, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

{{site.data.keyword.containerlong_notm}} version version 1.30 Kubernetes certification
:   {{site.data.keyword.containerlong_notm}} version [1.30](/docs/containers?topic=containers-cs_versions_130) is now Kubernetes certified.

Important networking changes for {{site.data.keyword.containerlong_notm}} VPC clusters created at version 1.30.
:   For more information, see the [130 version information](/docs/openshift?topic=openshift-cs_versions_130) and [Understanding Secure by Default Cluster VPC Networking](/docs/containers?topic=containers-vpc-security-group-reference).

Important changes to the default cluster provisioning behavior for new VPC clusters beginning with version 1.30.
:   Beginning with version 1.30, there is a new option available at cluster creation time via the UI, CLI, API, and Terraform. This new option manages outbound traffic protection for the cluster. The default behavior is to have outbound traffic protection enabled, which means new version 1.30 VPC clusters won't have access the public internet by default. If your cluster needs access to the public internet, you must specifically include the option (from the UI, CLI, API, and Terraform) to disable outbound traffic protection. Note that you can also disable outbound traffic protection after your cluster is created. You can also selectively allow outbound traffic as needed after your cluster is created. If you provision clusters via automation, make sure to adjust your automation accordingly.
:   For more information, see the [1.30 version information](/docs/openshift?topic=openshift-cs_versions_130), [Understanding Secure by Default Cluster VPC Networking](/docs/containers?topic=containers-vpc-security-group-reference), and [Managing outbound traffic protection in VPC clusters](/docs/containers?topic=containers-sbd-allow-outbound).

Managing outbound traffic protection in new version 1.30 VPC clusters.
:   With the introduction of Secure by Default Cluster VPC networking in version 1.30 and later clusters, there are several scenarios where you might need to adjust the security group settings for your clusters to allow outbound traffic to certain resources. For more information, see [Managing outbound traffic protection in VPC clusters](/docs/containers?topic=containers-sbd-allow-outbound).

{{site.data.keyword.containerlong_notm}} version 1.27 is deprecated.
:   Support for 1.27 ends on {{site.data.keyword.kubernetes_127_unsupported_date}}. Update your cluster to at least [version 1.28](/docs/containers?topic=containers-cs_versions_128) as soon as possible.








{{site.data.keyword.containerlong_notm}} master fix packs.
:   Master fix pack are applied automatically over the course of several days. You can choose to use the [`ibmcloud ks cluster master update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update) command yourself without waiting for the update automation to apply the patch. Worker node fix packs can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)








### 23 May 2024
{: #containers-may2324}
{: release-note}




{{site.data.keyword.containerlong_notm}} worker node fix packs.
:   Worker node fix packs can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)







### 10 May 2024
{: #containers-may1024}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on patch update.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on patch update.
:   For more information, see the [change log](/docs/containers?topic=containers-versions-vpc-file-addon).





Istio add-on version `1.19` is no longer supported.
:   Update the add-on in your clusters to a supported version. For more information, see the [Updating the Istio add-on](/docs/containers?topic=containers-istio&interface=ui#istio_update) and the [change log](/docs/containers?topic=containers-istio-changelog).







### 08 May 2024
{: #containers-may0824}
{: release-note}



Istio add-on versions `1.21.2` and `1.20.6` are available.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).





ALB OAuth Proxy add-on patch updates.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-add-on-change-log).







### 07 May 2024
{: #containers-may0724}
{: release-note}





{{site.data.keyword.containerlong_notm}} worker node fix packs.
:   Worker node fix packs can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)






### 05 May 2024
{: #containers-may0524}
{: release-note}

{{site.data.keyword.containerlong_notm}} cluster autoscaler add-on patch updates.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

### 02 May 2024
{: #containers-may0224}
{: release-note}

{{site.data.keyword.containerlong_notm}} CLI version `1.0.618` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).



## April 2024
{: #containers-apr24}





### 29 April 2024
{: #containers-apr2924}
{: release-note}

Ingress ConfigMap update
:   For more information, see the [change log](https://cloud.ibm.com/docs/containers?topic=containers-ibm-k8s-controller-config-change-log).



### 24 April 2024
{: #containers-apr2424}
{: release-note}







{{site.data.keyword.containerlong_notm}} master and worker node fix packs.
:   Master fix pack are applied automatically over the course of several days. You can choose to use the [`ibmcloud ks cluster master update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update) command yourself without waiting for the update automation to apply the patch. Worker node fix packs can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)








Istio add-on versions `1.21.1`, `1.20.5`, and `1.19.9` are available.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).



{{site.data.keyword.cos_full_notm}} plug-in version `2.2.25`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.containerlong_notm}} CLI version `1.0.617` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).


### 18 April 2024
{: #containers-apr1824}
{: release-note}

{{site.data.keyword.containerlong_notm}} CLI version `1.0.613` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).

### 09 April 2024
{: #containers-apr0924}
{: release-note}



Worker node fix packs are available for {{site.data.keyword.containerlong_notm}}. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)








### 03 April 2024
{: #containers-apr0324}
{: release-note}



Istio add-on patch updates.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).

ALB OAuth Proxy add-on patch updates.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



{{site.data.keyword.containerlong_notm}} cluster autoscaler add-on patch updates.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

Version 1.0.9 of the cluster autoscaler add-on is deprecated with an end of support date of 30 April 2024.
:   Update to a supported version of the add-on before 30 April 2024.







## March 2024
{: #containers-mar24}

### 27 March 2024
{: #containers-mar2724}
{: release-note}



Master patch updates for {{site.data.keyword.containerlong_notm}} clusters. Master patches are applied automatically over the course of several days. You can choose to use the [`ibmcloud ks cluster master update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update) command yourself without waiting for the update automation to apply the patch. Review the change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_128)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)





### 25 March 2024
{: #containers-mar2524}
{: release-note}



Worker node fix packs are available for {{site.data.keyword.containerlong_notm}}. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)






New! NVIDIA L40 GPU support. You can now create VPC clusters with worker nodes which have NVIDIA L40 GPUs.
:   L40 GPU support is available in {{site.data.keyword.containerlong_notm}} clusters at version 1.28 or later with `gx3` worker nodes.
:   When you provision a version 1.28 or later VPC cluster with `gx3` worker nodes, or add a `gx3` worker pool to an existing 1.28 or later VPC cluster, the GPU drivers are automatically installed and you can get started right away. For more information, see [Deploying an app on a GPU machine](/docs/containers?topic=containers-deploy_app#gpu_app).




### 18 March 2024
{: #containers-mar1824}
{: release-note}


Ingress ALB updates are available for {{site.data.keyword.containerlong_notm}}.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).




### 15 March 2024
{: #containers-mar1524}
{: release-note}



Worker node fix packs are available for {{site.data.keyword.containerlong_notm}}. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure. Review the following change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_129)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)

Version 1.29 is the default version for {{site.data.keyword.containerlong_notm}}.
:   For a complete list of available versions, see the [version information](/docs/openshift?topic=openshift-openshift_versions).






### 08 March 2024
{: #containers-mar0824}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on patch updates.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on patch update.
:   For more information, see the [change log](/docs/containers?topic=containers-versions-vpc-file-addon).




### 06 March 2024
{: #containers-mar0624}
{: release-note}


Istio add-on versions `1.20.3` and `1.19.7` are available.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).


CLI version `1.0.601` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).

## February 2024
{: #containers-feb24}

### 28 February 2024
{: #containers-feb2824}
{: release-note}

{{site.data.keyword.containerlong_notm}} cluster autoscaler version 1.2.1 is available.
:   Version 1.2.1 of the autoscaler adds support for cluster version 1.29. For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).





Master patch updates for {{site.data.keyword.containerlong_notm}} clusters. Master patches are applied automatically over the course of several days. You can choose to use the [`ibmcloud ks cluster master update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update) command yourself without waiting for the update automation to apply the patch. Review the change logs for your cluster version.
:   [1.29](/docs/containers?topic=containers-changelog_128)
:   [1.28](/docs/containers?topic=containers-changelog_128)
:   [1.27](/docs/containers?topic=containers-changelog_127)
:   [1.26](/docs/containers?topic=containers-changelog_126)








### 27 February 2024
{: #containers-feb2724}
{: release-note}




Worker node fix packs are available for {{site.data.keyword.containerlong_notm}}. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.29.2_1529](/docs/containers?topic=containers-changelog_129)
    - [1.28.7_1547](/docs/containers?topic=containers-changelog_128)
    - [1.27.11_1567](/docs/containers?topic=containers-changelog_127)
    - [1.26.14_1576](/docs/containers?topic=containers-changelog_126)





CLI version `1.0.597` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).


### 26 February 2024
{: #containers-feb2624}
{: release-note}

New! NVIDIA L4 GPU support. You can now create VPC clusters with worker nodes which have NVIDIA L4 GPUs.
:   L4 GPU support is available in {{site.data.keyword.containerlong_notm}} clusters at version 1.28 or later with `gx3` worker nodes.
:   When you provision a version 1.28 or later VPC cluster with `gx3` worker nodes, or add a `gx3` worker pool to an existing 1.28 or later VPC cluster, the GPU drivers are automatically installed and you can get started right away. For more information, see [Deploying an app on a GPU machine](/docs/containers?topic=containers-deploy_app#gpu_app).



Ingress ALB patch updates `1.9.4_6376_iks`, `1.8.4_6375_iks`, and `1.6.4_6374_iks` for {{site.data.keyword.containerlong_notm}}.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



New worker node flavors are available with L4 GPUs.
:   The following worker node flavors with L4 GPUs are now available. For more information, see [VPC flavors](/docs/containers?topic=containers-vpc-flavors).
    - `gx3.16x80x1L4`: 1 GPU, 16 cores, 80 GB memory, 100GB storage, 32 Gbps network speed.
    - `gx3.32x160x2L4`: 2 GPU, 32 cores, 160 GB, memory, 100GB storage, 32 Gbps network speed
    - `gx3.64x320x4L4`: 4 GPU, 64 cores, 320 GB memory, 100GB storage, 32 Gbps network speed




### 22 February 2024
{: #containers-feb2224}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.24`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 21 February 2024
{: #containers-feb2124}
{: release-note}



Kubernetes version 1.29 certification
:   Version [1.29](/docs/containers?topic=containers-cs_versions_129) release is now certified.



{{site.data.keyword.containerlong_notm}} cluster autoscaler add-on patch updates `1.0.9_377` and `1.2.0_365`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).





### 19 February 2024
{: #containers-feb1924}
{: release-note}

Ingress ALB versions `1.9.4_6359_iks` and `1.8.4_6363_iks` are available for {{site.data.keyword.containerlong_notm}}.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).





### 16 February 2024
{: #containers-feb1624}
{: release-note}



{{site.data.keyword.containerlong_notm}} cluster autoscaler add-on patch update `1.1.0_362`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).




### 14 February 2024
{: #containers-feb1424}
{: release-note}

New! {{site.data.keyword.containerlong_notm}} version 1.29.
:   You can create or [update clusters to Kubernetes version 1.29](/docs/containers?topic=containers-cs_versions_129). With Kubernetes 1.29, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

Master fix pack `1.29.1_1524` and worker node fix pack `1.29.1_1525`.
:   For more information, see the [1.29 change log](/docs/containers?topic=containers-changelog_129).

Starting with {{site.data.keyword.containerlong_notm}} version 1.29, Calico components run in the `calico-system` namespace and the Tigera operator components run in the `tigera-operator` namespace.
:   For more information, see [1.29 version information and update actions](/docs/containers?topic=containers-cs_versions_129).


{{site.data.keyword.containerlong_notm}} version 1.26 is deprecated.
:   Update your cluster to at least [version 1.27](/docs/containers?topic=containers-cs_versions_127) as soon as possible.



### 13 February 2024
{: #containers-feb1324}
{: release-note}



Worker node fix packs are available for {{site.data.keyword.containerlong_notm}}. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.6_1544](/docs/containers?topic=containers-changelog_128)
    - [1.27.10_1563](/docs/containers?topic=containers-changelog_127)
    - [1.26.13_1571](/docs/containers?topic=containers-changelog_126)

Ingress ALB versions `1.9.4_6346_iks`, `1.8.4_6345_iks`, `1.6.4_6344_iks` are available for {{site.data.keyword.containerlong_notm}}.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).








### 08 February 2024
{: #containers-feb0824}
{: release-note}

CLI version `1.0.595` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).

{{site.data.keyword.block_storage_is_short}} add-on versions `5.2.15_501` and `5.1.21_506` are available.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.2.6_130` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-versions-vpc-file-addon).




### 07 February 2024
{: #containers-feb0724}
{: release-note}

Istio add-on versions `1.20.2`, `1.19.6`, and `1.18.7` are available.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).


### 05 February 2024
{: #containers-feb0524}
{: release-note}

  
Ingress ALB updates
:   Ingress ALB versions `1.9.4_6292_iks`, `1.8.4_6291_iks`, `1.6.4_6293_iks` are available. 1.9.4 is the default version for all ALBs that run the Kubernetes Ingress image. If you have Ingress auto update enabled, your ALBs automatically update to use this image. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 01 February 2024
{: #containers-feb0124}
{: release-note}



Master fix packs are available for {{site.data.keyword.containerlong_notm}}
:   Review the change logs for your cluster version. Master patch updates are applied automatically.
:   [1.28.6_1542](/docs/containers?topic=containers-changelog_128)
:   [1.27.10_1561](/docs/containers?topic=containers-changelog_127)
:   [1.26.13_1569](/docs/containers?topic=containers-changelog_126)

{{site.data.keyword.containerlong_notm}} version 1.25 is no longer supported.
:   Update your 1.25 clusters to at least version 1.26. For more information, see [1.26 version information and update actions](/docs/containers?topic=containers-cs_versions_126).






{{site.data.keyword.containerlong_notm}} cluster autoscaler add-on patch update `1.0.8_346`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).


## January 2024
{: #containers-jan24}

### 30 January 2024
{: #containers-jan3024}
{: release-note}



Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.6_1543](/docs/containers?topic=containers-changelog_128)
    - [1.27.10_1562](/docs/containers?topic=containers-changelog_127)
    - [1.26.13_1570](/docs/containers?topic=containers-changelog_126)





### 29 January 2024
{: #containers-jan2924}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.23`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).



### 22 January 2024
{: #containers-jan2224}
{: release-note}

  
Ingress ALB updates
:   Ingress ALB versions `1.9.4_6251_iks`, `1.8.4_6245_iks`, `1.6.4_6250_iks` are available. 1.9.4 is the default version for all ALBs that run the Kubernetes Ingress image. If you have Ingress auto update enabled, your ALBs automatically update to use this image. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).





### 19 January 2024
{: #containers-jan1924}
{: release-note}

CLI version `1.0.589` is available.
:   For more information, see [Updating the CLI](/docs/containers?topic=containers-cli-update) and the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).



### 17 January 2024
{: #containers-jan1724}
{: release-note}



Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.4_1541](/docs/containers?topic=containers-changelog_128)
    - [1.27.8_1560](/docs/containers?topic=containers-changelog_127)
    - [1.26.11_1568](/docs/containers?topic=containers-changelog_126)
    - [1.25.16_1573](/docs/containers?topic=containers-changelog_125)






### 16 January 2024
{: #containers-jan1624}
{: release-note}

Cluster autoscaler add-on patch updates `1.2.0_322` and `1.0.9_328`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).



ALB OAuth Proxy add-on version `2.0.0_2063`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).








### 10 January 2024
{: #containers-jan1024}
{: release-note}

Subscribe to the {{site.data.keyword.cloud_notm}} documentation release notes via RSS.
:   You can get notified via RSS about documentation updates for {{site.data.keyword.containerlong_notm}} such as worker node fix packs, new cluster versions, new cluster add-on versions, and more.  For more information, see [Subscribing to an RSS feed](/docs/containers?topic=containers-viewing-cloud-status#subscribing-rss-feed).


  
Ingress ALB updates
:   Ingress ALB versions `1.9.4_6161_iks`, `1.8.4_6173_iks`, `1.6.4_6177_iks` are available. 1.9.4 is the default version for all ALBs that run the Kubernetes Ingress image. If you have Ingress auto update enabled, your ALBs automatically update to use this image. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).

Istio cluster add-on versions `1.20.0`, `1.19.5`, and `1.18.6`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).

Istio add-on version 1.18 will no longer be supported on 21 February 2024
:   Follow the steps to update your [Istio components](/docs/containers?topic=containers-istio#istio_minor) to the latest patch version of Istio 1.18 that is supported by {{site.data.keyword.containerlong_notm}}.



{{site.data.keyword.filestorage_vpc_full_notm}} cluster add-on patch update `1.2.5_107`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).

{{site.data.keyword.block_storage_is_short}} cluster add-on patch updates `5.2.14_485` and `5.1.19_486`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).





### 2 January 2024
{: #containers-jan0224}
{: release-note}



Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.4_1540](/docs/containers?topic=containers-changelog_128)
    - [1.27.8_1559](/docs/containers?topic=containers-changelog_127)
    - [1.26.11_1567](/docs/containers?topic=containers-changelog_126)
    - [1.25.16_1572](/docs/containers?topic=containers-changelog_125)






## December 2023
{: #containers-dec23}

### 18 December 2023
{: #containers-dec1823}
{: release-note}



Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.4_1539](/docs/containers?topic=containers-changelog_128)
    - [1.27.8_1558](/docs/containers?topic=containers-changelog_127)
    - [1.26.11_1566](/docs/containers?topic=containers-changelog_126)
    - [1.25.16_1571](/docs/containers?topic=containers-changelog_125)





### 14 December 2023
{: #containers-dec1423}
{: release-note}

Information on worker node removal priority.
:   Details are available for [automated worker node removal](/docs/containers?topic=containers-update#worker-scaledown-logic) when scaling down a worker pool.


Kubernetes version 1.24 is unsupported.
:   Update your cluster to at least [version 1.25](/docs/containers?topic=containers-cs_versions_125) as soon as possible.












### 8 December 2023
{: #containers-dec0823}
{: release-note}

Security Bulletin: {{site.data.keyword.containerlong_notm}} is affected by Kubernetes API server security vulnerabilities
:   For more information, see the [Security Bulletin](https://www.ibm.com/support/pages/node/7091444){: external}. 


### 7 December 2023
{: #containers-dec0723}
{: release-note}

Istio add-on version `1.20.0`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).



### 6 December 2023
{: #containers-dec0623}
{: release-note}



Master fix packs are available. 
:   Review the change logs for your cluster version. Master patch updates are applied automatically.
:   [1.28.4_1537](/docs/containers?topic=containers-changelog_128)
:   [1.27.8_1556](/docs/containers?topic=containers-changelog_127)
:   [1.26.11_1564](/docs/containers?topic=containers-changelog_126)
:   [1.25.16_1569](/docs/containers?topic=containers-changelog_125)







  
### 5 December 2023
{: #containers-dec0523}
{: release-note}

Istio add-on version `1.19.4`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).
  




### 4 December 2023
{: #containers-dec0423}
{: release-note}


  
Ingress ALB updates
:   Ingress ALB versions `1.9.4_5886_iks`, `1.8.4_5885_iks`, `1.6.4_5884_iks` are available. 1.9.4 is now the default version for all ALBs that run the Kubernetes Ingress image. If you have Ingress auto update enabled, your ALBs automatically update to use this image. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).


Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.4_1538](/docs/containers?topic=containers-changelog_128)
    - [1.27.8_1557](/docs/containers?topic=containers-changelog_127)
    - [1.26.11_1565](/docs/containers?topic=containers-changelog_126)
    - [1.25.16_1570](/docs/containers?topic=containers-changelog_125)
    - [1.24.17_1592](/docs/containers?topic=containers-changelog_124)





## November 2023
{: #containers-nov23}

### 29 November 2023
{: #containers-nov2923}
{: release-note}




Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.3_1535](/docs/containers?topic=containers-changelog_128)
    - [1.27.7_1548](/docs/containers?topic=containers-changelog_127)
    - [1.26.10_1561](/docs/containers?topic=containers-changelog_126)
    - [1.25.15_1568](/docs/containers?topic=containers-changelog_125)
    - [1.24.17_1591](/docs/containers?topic=containers-changelog_124)





### 27 November 2023
{: #containers-nov2723}
{: release-note}

The Beta {{site.data.keyword.filestorage_vpc_short}} cluster add-on is now available to all accounts.
:   Previously the add-on was available in allowlisted accounts only. For more information, see [Enabling the {{site.data.keyword.filestorage_vpc_short}} add-on](/docs/containers?topic=containers-cluster-scaling-install-addon).

Cluster autoscaler add-on patch updates `1.2.0_290`, `1.0.9_290`, `1.0.8_292`, and `1.0.7_291`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.23_437` and `5.1.16_446`, and `5.2.11_447`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on patch `1.1.10_93` and `1.2.3_97`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).





### 21 November 2023
{: #containers-nov2123}
{: release-note}



Ingress ALB updates
:    Ingress ALB versions `1.9.4_5756_iks`, `1.8.4_5757_iks`, `1.6.4_5727_iks` are available. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 20 November 2023
{: #containers-nov2023}
{: release-note}

You can now specify a custom pod subnet size when creating a VPC cluster.
:   For more information, see the [CLI reference](/docs/containers?topic=containers-kubernetes-service-cli#cli_cluster-create-vpc-gen2) or [create a VPC cluster](/docs/containers?topic=containers-cluster-create-vpc-gen2&interface=cli#cluster_create_vpc) with a custom pod subnet size.

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.22`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 15 November 2023
{: #containers-nov1523}
{: release-note}

The cluster autoscaler add-on now supports version 1.28 clusters.
:   For more information, see [Enabling the cluster autoscaler add-on in your cluster](/docs/containers?topic=containers-cluster-scaling-install-addon).



Master fix packs are available. 
:   Review the change logs for your cluster version. Master patch updates are applied automatically.
:   [1.28.3_1534](/docs/containers?topic=containers-changelog_128)
:   [1.27.7_1547](/docs/containers?topic=containers-changelog_127)
:   [1.26.10_1560](/docs/containers?topic=containers-changelog_126)
:   [1.25.15_1567](/docs/containers?topic=containers-changelog_125)







### 13 November 2023
{: #containers-nov1323}
{: release-note}


{{site.data.keyword.cos_full_notm}} plug-in version `2.2.21`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.21_401` and `5.1.15_419`, and `5.2.10_428`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).

Cluster autoscaler add-on patch updates `1.0.9_195`, `1.0.8_233`, and `1.0.7_185`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on patch `1.1.9_87`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).



### 10 November 2023
{: #containers-nov1023}
{: release-note}

Updated sorting and formatting for the Classic and VPC cluster flavor pages.
:   For more information, see [VPC flavors](/docs/containers?topic=containers-vpc-flavors) and [Classic flavors](/docs/containers?topic=containers-classic-flavors).

### 9 November 2023
{: #containers-nov0923}
{: release-note}



Worker node fix packs are available.
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.

:   [1.28.2_1533](/docs/containers?topic=containers-changelog_128)
:   [1.27.6_1546](/docs/containers?topic=containers-changelog_127)
:   [1.26.9_1559](/docs/containers?topic=containers-changelog_126)
:   [1.25.14_1566](/docs/containers?topic=containers-changelog_125)
:   [1.24.17_1590](/docs/containers?topic=containers-changelog_124)





### 7 November 2023
{: #containers-nov0723}
{: release-note}

CLI version `1.0.579` is available.
:   For more information, see the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).



Ingress ALB updates
:    Ingress ALB versions `1.9.4_5698_iks`, `1.8.4_5644_iks`, `1.6.4_5642_iks` are available. Version `1.8.4_5644_iks` is now the default version. Version `1.5.1` is no longer supported. For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).




  
### 06 November 2023
{: #containers-nov0623}
{: release-note}

Kubernetes version 1.28 is now the default version for new {{site.data.keyword.containerlong_notm}} clusters.
:   For more information, see the [Kubernetes version information](/docs/containers?topic=containers-cs_versions), the [1.28 version information and update actions](/docs/containers?topic=containers-cs_versions_128), and the [1.28 change log](/docs/containers?topic=containers-changelog_128).





## October 2023
{: #containers-oct23}

### 31 October 2023
{: #containers-oct3123}
{: release-note}


VNI functionality for limiting access to {{site.data.keyword.filestorage_vpc_short}} by node, zone, worker pool and more.
:   You now have more granular control over how pods access your {{site.data.keyword.filestorage_vpc_short}}. For more information, see [Limiting file share access by worker node, zone, or worker pool](/docs/containers?topic=containers-storage-file-vpc-apps#storage-file-vpc-vni-setup).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.2`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).


### 30 October 2023
{: #containers-oct3023}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.20`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

Setting up alerts for {{site.data.keyword.blockstorageshort}} PVs with limited network connectivity.
:   For more information, see [Setting up monitoring for `limited` connectivity PVs](/docs/containers?topic=containers-block_storage#storage-block-vpc-limited-monitoring).

### 25 October 2023
{: #containers-oct2523}
{: release-note}



Master fix packs are available.
:   [1.28.2_1531](/docs/containers?topic=containers-changelog_128)
:   [1.27.6_1544](/docs/containers?topic=containers-changelog_127)
:   [1.26.9_1557](/docs/containers?topic=containers-changelog_126)
:   [1.25.14_1564](/docs/containers?topic=containers-changelog_125)


ALB OAuth Proxy add-on version `2.0.0_1901`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).






### 23 October 2023
{: #containers-oct2323}
{: release-note}



Worker node fix packs are available. 
:    Worker node updates can be applied by updating or reloading the worker node in classic infrastructure, or replacing the worker node in VPC infrastructure.
:    Review the following change logs for your cluster version.
    - [1.28.2_1532](/docs/containers?topic=containers-changelog_128)
    - [1.27.6_1545](/docs/containers?topic=containers-changelog_127)
    - [1.26.9_1558](/docs/containers?topic=containers-changelog_126)
    - [1.25.14_1565](/docs/containers?topic=containers-changelog_125)
    - [1.24.17_1589](/docs/containers?topic=containers-changelog_124)





Ingress ALB version `1.8.4_5586_ikss`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 18 October 2023
{: #containers-oct1823}
{: release-note}



Istio add-on version `1.18.5` and `1.17.8`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).
  
ALB OAuth Proxy add-on version `2.0.0_1889`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).






### 17 October 2023
{: #containers-oct1723}
{: release-note}

Ingress ALB versions `1.8.1_5543_iks`, `1.6.4_5544_iks`, and `1.5.1_5542_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 11 October 2023
{: #containers-oct1123}
{: release-note}

Ingress ALB versions `1.5.1_5436_iks`, `1.6.4_5435_iks`, and `1.8.1_5434_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.19`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).




### 10 October 2023
{: #containers-oct1023}
{: release-note}

CLI version `1.0.573` is available.
:   For more information, see the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).



Istio add-on version `1.19.3`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).



### 9 October 2023
{: #containers-oct923}
{: release-note} 



Worker node fix packs are available.
:   [1.28.2_1529](/docs/containers?topic=containers-changelog_128)
:   [1.27.5_1542](/docs/containers?topic=containers-changelog_127)
:   [1.26.8_1556](/docs/containers?topic=containers-changelog_126)
:   [1.25.13_1563](/docs/containers?topic=containers-changelog_125)
:   [1.24.16_1583](/docs/containers?topic=containers-changelog_124)







### 5 October 2023
{: #containers-oct523}
{: release-note} 

Ingress ALB versions `1.8.1_5384_iks`, `1.6.4_5406_iks`, and `1.5.1_5407_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 4 October 2023
{: #containers-oct423}
{: release-note}


Cluster autoscaler add-on version `1.0.9_134`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).


### 3 October 2023
{: #containers-oct323}
{: release-note}



Istio add-on versions `1.17.6` and `1.18.3`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).



## September 2023
{: #containers-sep23}


### 27 September 2023
{: #containers-sep2723}
{: release-note}


  
Worker node fix packs are available.
:   [1.28.2_1528](/docs/containers?topic=containers-changelog_128)
:   [1.27.5_1541](/docs/containers?topic=containers-changelog_127)
:   [1.26.8_1555](/docs/containers?topic=containers-changelog_126)
:   [1.25.12_1562](/docs/containers?topic=containers-changelog_125)
:   [1.24.17_1587](/docs/containers?topic=containers-changelog_124)





### 26 September 2023
{: #containers-sep2623}
{: release-note}



ALB OAuth Proxy add-on version `2.0.0_1843`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).
  



### 25 September 2023
{: #containers-sep2523}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version `5.2`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 22 September 2023
{: #containers-sep2223}
{: release-note}


Kubernetes version 1.28 certification
:   Version [1.28](/docs/containers?topic=containers-cs_versions_128) release is now certified.



### 20 September 2023
{: #containers-sep2023}
{: release-note} 



New! {{site.data.keyword.containerlong_notm}} version 1.28.
:   You can create or [update clusters to Kubernetes version 1.28](/docs/containers?topic=containers-cs_versions_128). With Kubernetes 1.28, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

Master fix pack `1.28.2_1527` and worker node fix pack `1.28.1_1523`.
:   For more information, see the [1.28 change log](/docs/containers?topic=containers-changelog_128).

Networking changes for VPC clusters 1.28 and later
:   In version 1.27 and earlier, VPC clusters pull container images from the {{site.data.keyword.registrylong_notm}} through a private cloud service endpoint for the Container Registry. For version 1.28 and later, this network path is updated so that images are pulled through a VPE gateway instead of a private service endpoint. For more information, see the [1.28 change log](/docs/containers?topic=containers-changelog_128).

Trusted profile updates for Kubernetes clusters version 1.28 and later.
:   You can now give trusted profiles service level access to your clusters, then use a federated ID, like App ID, to access the cluster at the level assigned in the trusted profile since trusted profile identities are now synced into the cluster RBAC. For more information, see [Creating trusted profiles](/docs/account?topic=account-create-trusted-profile&interface=ui) and [Logging in with a federated ID](/docs/account?topic=account-federated_id&interface=ui).

New! Updated GPU drivers with version 1.28 clusters.
:   With the release of IBM Cloud Kubernetes Version 1.28, GPU drivers moved to the 500 series version for all GPU worker node flavors. To use the 500 series GPU drivers, ensure that a GPU worker node flavor is being used and the cluster master version is upgraded to at least version 1.28. Versions earlier than 1.28 will still continue to use the 400 series GPU drivers. For more information, see [Deploying an app on a GPU machine](/docs/containers?topic=containers-deploy_app&interface=ui#gpu_app).

  
Master fix packs are available.
:   [1.27.5_1540](/docs/containers?topic=containers-changelog_127)
:   [1.26.8_1554](/docs/containers?topic=containers-changelog_126)
:   [1.25.13_1561](/docs/containers?topic=containers-changelog_125)
:   [1.24.17_1586](/docs/containers?topic=containers-changelog_124)







### 18 September 2023
{: #containers-sep1823}
{: release-note}

CLI version `1.0.566` is available.
:   For more information, see the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).


### 15 September 2023
{: #containers-sep1523}
{: release-note} 

Cluster autoscaler add-on versions `1.0.9_103`,`1.0.8_104`, and `1.0.7_102`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).


### 14 September 2023
{: #containers-sep1423}
{: release-note} 


{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.1.7_49`
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.19_358` and `5.1.13_345`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).


### 12 September 2023
{: #containers-sep1223}
{: release-note} 



Worker node fix packs are available.
:   [1.27.4_1538](/docs/containers?topic=containers-changelog_127)
:   [1.26.7_1552](/docs/containers?topic=containers-changelog_126)
:   [1.25.12_1558](/docs/containers?topic=containers-changelog_125)
:   [1.24.16_1583](/docs/containers?topic=containers-changelog_124)





### 7 September 2023
{: #containers-sep723}
{: release-note} 

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.18`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

## August 2023
{: #containers-aug23}



### 31 August 2023
{: #containers-aug3123}
{: release-note} 

Ingress ALB versions `1.8.1_5317_iks`, `1.6.4_5270_iks`, and `1.5.1_5318_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 30 August 2023
{: #containers-aug2023}
{: release-note}



Master fix packs are available.
:   [1.27.4_1536](/docs/containers?topic=containers-changelog_127)
:   [1.26.7_1550](/docs/containers?topic=containers-changelog_126)
:   [1.25.12_1556](/docs/containers?topic=containers-changelog_125)
:   [1.24.16_1581](/docs/containers?topic=containers-changelog_124)








### 29 August 2023
{: #containers-aug2923}
{: release-note}

New! Madrid multizone region
:   You can now [create VPC clusters](/docs/containers?topic=containers-cluster-create-vpc-gen2) in [Madrid](/docs/containers?topic=containers-regions-and-zones).

Worker node fix packs are available.
:   [`1.27.4_1537`](/docs/containers?topic=containers-changelog_127)
:   [`1.26.7_1551`](/docs/containers?topic=containers-changelog_126)
:   [`1.25.12_1557`](/docs/containers?topic=containers-changelog_125)
:   [`1.24.16_1582`](/docs/containers?topic=containers-changelog_124)

### 15 August 2023
{: #containers-aug1523}
{: release-note}



Worker node fix packs are available.
:   [`1.24.16_1580`](/docs/containers?topic=containers-changelog_124)
:   [`1.25.12_1555`](/docs/containers?topic=containers-changelog_125)
:   [`1.26.7_1547`](/docs/containers?topic=containers-changelog_126)
:   [`1.27.4_1535`](/docs/containers?topic=containers-changelog_127)



  


### 9 August 2023
{: #containers-aug0923}
{: release-note}

ALB OAuth Proxy add-on version `2.0.0_1715`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).




  
### 8 August 2023
{: #containers-aug0823}
{: release-note}

Istio add-on versions `1.16.7`, `1.17.5`, and `1.18.2`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).



### 7 August 2023
{: #containers-aug0723}
{: release-note}

Cluster autoscaler add-on versions `1.0.9_81`,`1.0.8_82`, and `1.0.7_83`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

### 3 August 2023
{: #containers-aug0323}
{: release-note}


CIS benchmarks for {{site.data.keyword.redhat_openshift_notm}} version 4.13.
:   CIS benchmark results are available for {{site.data.keyword.redhat_openshift_notm}} version [4.13](/docs/openshift?topic=openshift-cis-benchmark-413).


### 1 August 2023
{: #containers-aug0123}
{: release-note}



Worker node fix packs are available.
:   [`1.24.16_1579`](/docs/containers?topic=containers-changelog_124)
:   [`1.25.12_1554`](/docs/containers?topic=containers-changelog_125)
:   [`1.26.7_1546`](/docs/containers?topic=containers-changelog_126)
:   [`1.27.4_1534`](/docs/containers?topic=containers-changelog_127)





{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.17_266` and `5.1.12_285`.
:   For more information, see the [change log](/docs/containers?topic=containers-vpc_bs_changelog).



## July 2023
{: #containers-july23}



### 31 July 2023
{: #containers-july3123}
{: release-note}


Ubuntu 18 is no longer supported.
:   For more information, see [Migrating to a new Ubuntu version](/docs/containers?topic=containers-ubuntu-migrate).




### 28 July 2023
{: #containers-july2823}
{: release-note}





{{site.data.keyword.cos_full_notm}} plug-in version `2.2.17`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 27 July 2023
{: #containers-july2723}
{: release-note}



Master fix packs are available
:   [1.24.16_1578](/docs/containers?topic=containers-changelog_124)
:   [1.25.12_1553](/docs/containers?topic=containers-changelog_125)
:   [1.26.7_1545](/docs/containers?topic=containers-changelog_126)
:   [1.27.4_1533](/docs/containers?topic=containers-changelog_127)





{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.1.6`
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).




Istio add-on version `1.16.6`, `1.17.4`, and `1.18.1`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).





### 26 July 2023
{: #containers-july2623}
{: release-note} 

Ingress ALB versions `1.6.4_5219_iks`, `1.5.1_5217_iks`, and `1.4.0_5218_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).





### 25 July 2023
{: #containers-july2523}
{: release-note}


End of support for the free cluster tier 
:   As announced on [23 June 2023](#containers-jun2323), the free cluster option is no longer available. Existing free tier clusters will be allowed to finish their 30-day trial window. If you want to continue testing {{site.data.keyword.containerlong_notm}}, try creating a [Classic cluster](/docs/containers?topic=containers-cluster-create-classic). Then [copy your deployments to the new cluster](/docs/containers?topic=containers-update_app#copy_apps_cluster).




### 24 July 2023
{: #containers-july2423}
{: release-note}


Cluster autoscaler add-on version `1.0.9_70`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).
  
Static route add-on version `1.0.0_1122`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-static-route).



### 21 July 2023
{: #containers-july2123}
{: release-note}

Cluster autoscaler add-on update command.
:   You can now use the `ibmcloud ks cluster addon update` command to update your add-on. For more information, see [Updating the cluster autoscaler add-on](/docs/containers?topic=containers-cluster-scaling-install-addon#cluster-scaling-install-addon-update-addon).

### 19 July 2023
{: #containers-july1923}
{: release-note}

CLI version `1.0.540` is available.
:   For more information, see the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).


### 17 July 2023
{: #containers-july1723}
{: release-note}


Worker node fix packs `1.24.15_1576`, `1.25.11_1552`, `1.26.6_1544`, and `1.27.3_1532`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125),  [1.26](/docs/containers?topic=containers-changelog_126), and [1.27](/docs/containers?topic=containers-changelog_127).







### 12 July 2023
{: #containers-july1223}
{: release-note}

ALB OAuth Proxy add-on version `2.0.0_1669`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



### 11 July 2023
{: #containers-july1123}
{: release-note}

New! OpenShift Data Foundation add-on version `4.13.0`.
:   For more information, see the [change log](/docs/openshift?topic=openshift-odf_addon_changelog).



### 6 July 2023
{: #containers-july623}
{: release-note} 

Cluster autoscaler add-on version `1.0.8_56` and `1.0.7_57`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).



Istio add-on version `1.18.0`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).




Pod security admission updates
:   Review the [default pod security configuration](/docs/containers?topic=containers-pod-security-admission#psa-plugin-config-default) and the steps to [customize pod security admission in your cluster](/docs/containers?topic=containers-pod-security-admission#psa-plugin-config-custom).





### 5 July 2023
{: #containers-july523}
{: release-note} 

Ingress ALB versions `1.6.4_5161_iks`, `1.5.1_5160_iks`, and `1.4.0_5159_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 3 July 2023
{: #containers-july323}
{: release-note} 

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.16`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.1`
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon). 


Worker node fix packs `1.24.15_1574`, `1.25.11_1550`, `1.26.6_1542`, and `1.27.3_1530`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125),  [1.26](/docs/containers?topic=containers-changelog_126), and [1.27](/docs/containers?topic=containers-changelog_127).


## June 2023
{: #containers-jun23}



### 27 June 2023
{: #containers-jun2723}
{: release-note} 




Master fix packs `1.24.15_1573`, `1.25.11_1549`, `1.26.6_1541`, and `1.27.3_1529`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), [1.26](/docs/containers?topic=containers-changelog_126), and [1.27](/docs/containers?topic=containers-changelog_127).


### 26 June 2023
{: #containers-jun2623}
{: release-note} 

CLI version `1.0.528`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_cli_changelog).



### 23 June 2023
{: #containers-jun2323}
{: release-note} 

Free cluster tier deprecation
:   The free cluster option is deprecated and will be unsupported on 25 July 2023. Existing free tier clusters will be allowed to finish their 30-day trial window. If you want to continue testing {{site.data.keyword.containerlong_notm}}, try creating a [Classic cluster](/docs/containers?topic=containers-cluster-create-classic). Then [copy your deployments to the new cluster](/docs/containers?topic=containers-update_app#copy_apps_cluster).




### 22 June 2023
{: #containers-jun2223}
{: release-note} 



Cluster autoscaler add-on version `1.0.9_44`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).




Istio add-on version `1.17.3`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).





### 21 June 2023
{: #containers-jun2123}
{: release-note} 

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.16_127` and `5.1.11_126`.
:   This patch introduces two new variables to the `addon-vpc-block-csi-driver-configmap`. To get the latest snapshot configmap values users must add the new values to the existing configmap and apply the changes. For more information, see [Customizing snapshots](/docs/containers?topic=containers-vpc-volume-snapshot) and [the add-on change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 20 June 2023
{: #containers-jun2023}
{: release-note} 



Worker node fix pack updates
:   Worker node fix pack updates are available for versions [1.27](/docs/containers?topic=containers-changelog_127), [1.26](/docs/containers?topic=containers-changelog_126), [1.25](/docs/containers?topic=containers-changelog_125), and [1.24](/docs/containers?topic=containers-changelog_124).


### 19 June 2023
{: #containers-jun1923}
{: release-note} 

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.15`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).







### 8 June 2023
{: #containers-jun823}
{: release-note}

Istio add-on version `1.16.5`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).





### 6 June 2023
{: #containers-jun623}
{: release-note}

Ingress ALB versions `1.6.4_5067_iks`, `1.5.1_5074_iks`, and `1.4.0_5068_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 5 June 2023
{: #containers-jun523}
{: release-note}


Worker node fix packs `1.24.14_1571`, `1.25.10_1547`, `1.26.5_1539`, and `1.27.2_1527`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125),  [1.26](/docs/containers?topic=containers-changelog_126), and [1.27](/docs/containers?topic=containers-changelog_127).

## May 2023
{: #containers-may23}

### 31 May 2023
{: #containers-may3123}
{: release-note}



Master fix packs `1.24.14_1568`, `1.25.10_1545`, and `1.26.5_1537`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).

### 25 May 2023
{: #containers-may2523}
{: release-note}

CLI version `1.0.523`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_cli_changelog).


  
Kubernetes version 1.27 certification
:   Version [1.27](/docs/containers?topic=containers-cs_versions_127) release is now certified.



### 24 May 2023
{: #containers-may2423}
{: release-note}



New! {{site.data.keyword.containerlong_notm}} version 1.27.
:   You can create or [update clusters to Kubernetes version 1.27](/docs/containers?topic=containers-cs_versions_127). With Kubernetes 1.27, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

Master fix pack `1.27.2_1524` and worker node fix pack `1.27.2_1526`.
:   For more information, see the [1.27 change log](/docs/containers?topic=containers-changelog_127).


Worker node fix packs `1.24.14_1570`, `1.25.10_1546`, and `1.26.5_1538`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).



### 23 May 2023
{: #containers-may2323}
{: release-note}

Ingress ALB versions `1.6.4_4170_iks`, `1.5.1_4168_iks`, and `1.4.0_4169_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 16 May 2023
{: #containers-may1623}
{: release-note}

{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.0`.
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon).

### 15 May 2023
{: #containers-may1523}
{: release-note}

Cluster autoscaler add-on versions `1.0.6_1077`, `1.0.7_1076`, `1.0.8_1078`, and `1.1.0_1066`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

{{site.data.keyword.filestorage_vpc_full_notm}} add-on version `1.1-beta`
:   For more information, see [the change log](/docs/containers?topic=containers-versions-vpc-file-addon). 

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.12_1963` and `5.1.8_1970`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).


### 10 May 2023
{: #containers-may1023}
{: release-note}

Create Classic and VPC clusters with Terraform
:   For more information, see [Creating a single-zone classic cluster with Terraform](/docs/containers?topic=containers-cluster-create-classic&interface=terraform#cluster_classic_tf) and [Creating a VPC cluster with Terraform](/docs/containers?topic=containers-cluster-create-vpc-gen2&interface=terraform#cluster_vpcg2_tf).


### 9 May 2023
{: #containers-may0923}
{: release-note}


Worker node fix packs `1.24.13_1567`, `1.25.9_1544`, and `1.26.4_1536`.
:   For more information, see the change logs: [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).





### 4 May 2023
{: #containers-may0423}
{: release-note}

Ingress ALB version `1.6.4_4117_iks`, `1.5.1_4113_iks`, and `1.4.0_4114_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).




### 2 May 2023
{: #containers-may0223}
{: release-note}




{{site.data.keyword.cos_full_notm}} plug-in version `2.2.14`
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

## April 2023
{: #containers-apr23}


### 27 April 2023
{: #containers-apr2723}
{: release-note}


  
Ingress ALB version `1.6.4_4073_iks`, `1.5.1_4064_iks`, and `1.4.0_4062_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).
  
Master fix packs `1.23.17_1576`, `1.24.13_1566`, `1.25.9_1543`, and `1.26.4_1535`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).


### 26 April 2023
{: #containers-apr2623}
{: release-note}

Cluster autoscaler add-on version `1.1.0_1060`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

### 24 April 2023
{: #containers-apr2423}
{: release-note}  



Worker node fix packs `1.23.17_1576`, `1.24.13_1566`, `1.25.9_1543`, and `1.26.4_1535`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).



### 20 April 2023
{: #containers-apr2023}
{: release-note}  
  
Istio add-on version `1.16.4` and `1.17.2`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog).





### 13 April 2023
{: #containers-apr1323}
{: release-note}

ALB OAuth Proxy add-on version `2.0.0_1528`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).





### 12 April 2023
{: #containers-apr1223}
{: release-note}

Ingress ALB version `1.6.4_3976_iks`, `1.5.1_3977_iks`, and `1.4.0_3978_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 11 April 2023
{: #containers-apr1123}
{: release-note}

CLI version `1.0.510`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_cli_changelog).

Worker node fix packs `1.23.17_1574`, `1.24.12_1564`, `1.25.8_1541`, and `1.26.3_1533`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).

### 5 April 2023
{: #containers-apr0523}
{: release-note}

Cluster autoscaler add-on versions `1.0.6_1010`, `1.0.7_1021`, and `1.0.8_1016`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.10_1869` and `5.1.6_1872`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 4 April 2023
{: #containers-apr0423}
{: release-note}

Ingress ALB version `1.4.0_3953_iks`, `1.5.1_3951_iks`, and `1.6.4_3947_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 3 April 2023
{: #containers-apr0323}
{: release-note}

Pod Security admission 
:   You might need to check your Pod Security set up when you upgrade your cluster from version 1.24 to 1.25. For more information, see [Migrating from PSPs to Pod Security admission](/docs/containers?topic=containers-pod-security-admission-migration&interface=ui).

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.13`
:   **Important** Because there are changes to the storage classes installed with the plug-in, you must uninstall and reinstall the plug-in when you update to version `2.2.13` to get the latest storage class configurations. For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

## March 2023
{: #containers-mar23}

### 29 March 2023
{: #containers-mar2923}
{: release-note}



Worker node fix packs `1.23.17_1572`, `1.24.12_1562`, `1.25.8_1539`, and `1.26.3_1531`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).


{{site.data.keyword.block_storage_is_short}} add-on versions `5.0.9_1862` and `5.1.5_1857`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).

Cluster autoscaler add-on versions `1.0.7_988` and `1.0.8_987`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

### 28 March 2023
{: #containers-mar2823}
{: release-note}


  
Master fix packs `1.23.17_1569`, `1.24.12_1559`, `1.25.8_1536`, and `1.26.3_1528`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).

Worker node fix packs `1.23.17_1570`, `1.24.12_1560`, `1.25.8_1537`, and `1.26.3_1529`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).





### 24 March 2023
{: #containers-mar2423}
{: release-note}

Ingress ALB version `1.4.0_3896_iks`, `1.5.1_3897_iks`, and `1.6.4_3898_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 21 March 2023
{: #containers-mar2123}
{: release-note}

New troubleshooting steps for workers in `Critical` or `NotReady` state. 
:   For more information, see [Troubleshooting worker nodes in `Critical` or `NotReady` state](/docs/containers?topic=containers-ts-critical-notready).

### 20 March 2023
{: #containers-mar2023}
{: release-note}


{{site.data.keyword.cos_full_notm}} plug-in version `2.2.12`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 16 March 2023
{: #containers-mar1623}
{: release-note}


Cluster autoscaler add-on version `1.1.0_978`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).




### 14 March 2023
{: #containers-mar1423}
{: release-note}



Ingress ALB version `1.4.0_3862_iks`, `1.5.1_3863_iks`, and `1.6.4_3864_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).


Worker node fix packs `1.23.16_1568`, `1.24.10_1558`, `1.25.6_1535`, and `1.26.1_1525`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).





### 9 March 2023
{: #containers-mar0923}
{: release-note}


Cluster autoscaler add-on version `1.0.8_968`
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).



Istio add-on version `1.15.6` and `1.16.3`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1163).




### 7 March 2023
{: #containers-mar0723}
{: release-note}



Worker node fix packs `1.23.16_1567`, `1.24.10_1557`, `1.25.6_1534`, and `1.26.1_1524`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).



Cluster autoscaler add-on version `1.0.6_955` and `1.0.7_956`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).



Istio add-on version `1.17.1`.
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1171).



{{site.data.keyword.block_storage_is_short}} add-on versions `4.4.17_1829`, `5.0.7_1836`, and `5.1.2_1828`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).


### 3 March 2023
{: #containers-mar0323}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.10`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).


### 1 March 2023
{: #containers-mar0123}
{: release-note}

CLI version `1.0.498`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_cli_changelog).

ALB OAuth Proxy add-on version `2.0.0_1487`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).


## February 2023
{: #containers-feb23}



### 27 February 2023
{: #containers-feb2723}
{: release-note}



Worker node fix packs `1.23.16_1563`, `1.24.10_1554`, `1.25.6_1532`, and `1.26.1_1522`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).





### 23 February 2023
{: #containers-feb2323}
{: release-note}

Ingress ALB version `1.3.1_3807_iks`, `1.4.0_3808_iks`, and `1.5.1_3809_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).





### 22 February 2023
{: #containers-feb2223}
{: release-note}

ALB OAuth Proxy add-on version `2.0.0_1469`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



### 21 February 2023
{: #containers-feb2123}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.10`.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.block_storage_is_short}} add-on versions `4.4.17_1829`, `5.0.7_1836`, and `5.1.2_1828`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 20 February 2023
{: #containers-feb2023}
{: release-note}

Ingress ALB version `1.3.1_3777_iks`, `1.4.0_3783_iks`, and `1.5.1_3779_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).


  
### 17 February 2023
{: #containers-feb1723}
{: release-note}

Cluster autoscaler add-on version `1.0.7_944`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

### 14 February 2023
{: #containers-feb1423}
{: release-note}

Istio add-on `1.15.5` and `1.16.2`
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1162).

### 13 February 2023
{: #containers-feb1323}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.9` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).



Worker node fix packs `1.23.16_1562`, `1.24.10_1553`, `1.25.6_1531`, and `1.26.1_1521`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), [1.25](/docs/containers?topic=containers-changelog_125), and [1.26](/docs/containers?topic=containers-changelog_126).



### 10 February 2023
{: #containers-feb1023}
{: release-note}


New troubleshooting doc for how to recover after deleting a portable subnet in Classic clusters.
:   For more information, see [I deleted a portable subnet and now my Classic cluster my Load Balancers are failing. How do I recover?](/docs/containers?topic=containers-ts-network-subnet-recover).



Ingress ALB version `1.3.1_3754_iks` and `1.4.0_3755_iks`
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).




### 9 February 2023
{: #containers-feb0923}
{: release-note}


{{site.data.keyword.block_storage_is_short}} add-on version `5.1`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).


### 8 February 2023
{: #containers-feb0823}
{: release-note}

ALB OAuth Proxy add-on version `2.0.0_1420`.
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



### 2 February 2023
{: #containers-feb0223}
{: release-note}

Istio add-on `1.14` 
:   Version `1.14` of the managed Istio add-on is no longer supported. For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#v114).

### 1 February 2023
{: #containers-feb0123}
{: release-note}



New! Kubernetes 1.26
:   You can create or [update clusters to Kubernetes version 1.26](/docs/containers?topic=containers-cs_versions_126). With Kubernetes 1.26, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

Master fix pack
:   Kubernetes [1.26.1_1519](/docs/containers?topic=containers-changelog_126).

Worker node fix pack
:   Kubernetes [1.26.1_1520](/docs/containers?topic=containers-changelog_126)



Persistent VPC load balancers
:   You can now create a [persistent VPC load balancer](/docs/containers?topic=containers-vpc-lbaas#vpc_lb_persist) that remains available even after your cluster is deleted. 

Customized VPC load balancer health checks
:   For more control over your VPC load balancer health checks, you can use [optional annotations](/docs/containers?topic=containers-vpc-lbaas#vpc_lb_health_custom) to customize your health checks with advanced configurations for test intervals, timeouts, and retries.

## January 2023
{: #containers-jan23}

### 30 January 2023
{: #containers-jan3023}
{: release-note}



Master fix packs `1.23.16_1560`, `1.24.10_1551`, and `1.25.6_1529`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).





Worker node fix packs `1.23.16_1561`, `1.24.10_1552`, and `1.25.6_1530`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).



New! Optional secondary disks for worker nodes in VPC clusters.
:   When you create a VPC cluster, you can specify an optional secondary disk for your worker nodes. Secondary disks are used for the container runtime and are useful in scenarios where more container storage is needed, such as running pods with large images. For more information, see [Creating VPC clusters](/docs/containers?topic=containers-cluster-create-vpc-gen2&interface=ui).


CLI version `1.0.489`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_cli_changelog).



Ingress ALB version `1.5.1_3705_iks`, `1.4.0_3703_iks`, and `1.3.1_3704_iks`.
:   For more information, see the [change log](/docs/containers?topic=containers-cs_versions_ingress).



### 24 January 2023
{: #containers-jan2423}
{: release-note}

CLI version 1.0.487 change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.487.

{{site.data.keyword.block_storage_is_short}} add-on versions `4.4.16_1779` and `5.0.5_1784`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).

Cluster autoscaler add-on version `1.0.7_940`.
:   For more information, see [the change log](/docs/containers?topic=containers-ca_changelog).

Ingress ALB version `1.3.1_3685_iks`, `1.4.0_3684_iks`, and `1.5.1_3683_iks`
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).


### 23 January 2023
{: #containers-jan2323}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.8` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).


### 16 January 2023
{: #containers-jan1723}
{: release-note}



Worker node fix packs `1.23.15_1558`, `1.24.9_1550`, and `1.25.5_1528`.
:   For more information, see the change logs: [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).



### 10 January 2023
{: #containers-jan1023}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on versions `4.4.15_1764` and `5.0.4_1773`
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).

Istio add-on versions `1.14.6`, `1.15.4`, and `1.16.1`
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1161).

### 9 January 2023
{: #containers-jan0923}
{: release-note}

Cluster autoscaler add-on versions `1.0.5_898`, `1.0.6_899`, `1.0.7_900`, and `1.1.0_897`.
:   For more information, see [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 5 January 2023
{: #containers-jan0523}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.7` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).




### 3 January 2023
{: #containers-jan0323}
{: release-note}

Ingress ALB version `1.3.1_3538_iks`, and `1.4.0_3537_iks`
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).



### 2 January 2023
{: #containers-jan0223}
{: release-note}



Worker node fix packs `1.22.17_1584`, `1.23.15_1557`, `1.24.9_1549`, and `1.25.5_1527`
:   For more information, see the change logs: [1.22](/docs/containers?topic=containers-changelog_122), [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).



## December 2022
{: #containers-dec22}

### 19 December 2022
{: #containers-dec1922}
{: release-note}



Worker node fix packs `1.22.17_1583`, `1.23.15_1556`, `1.24.9_1548`, and `1.25.5_1526`
:   For more information, see the change logs: [1.22](/docs/containers?topic=containers-changelog_122), [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).



### 15 December 2022
{: #containers-dec1522}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.6` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).



Ingress ALB version `1.2.1_3299_iks`, `1.3.1_3298_iks`, and `1.4.0_3297_iks`
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).

ALB OAuth Proxy add-on version 2.0.0_1354
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



### 14 December 2022
{: #containers-dec1422}
{: release-note}



Master fix pack `1.22.17_1582`, `1.23.15_1555`, `1.24.9_1547`, and `1.25.5_1525`
:   For more information, see the change logs: [1.22](/docs/containers?topic=containers-changelog_122), [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).

 




Ubuntu 20 is now available for {{site.data.keyword.containerlong_notm}} clusters
:   You can now create {{site.data.keyword.containerlong_notm}} clusters using Ubuntu 20 worker nodes. To review the migration guide, see [Migrating to a new Ubuntu version](/docs/containers?topic=containers-ubuntu-migrate). To review operating system support by cluster version, see [{{site.data.keyword.containerlong_notm}} version information](/docs/containers?topic=containers-cs_versions).



CLI version 1.0.480 change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.480.
  
### 12 December 2022
{: #containers-dec1222}
{: release-note}





Ingress ALB version `1.4.0_3212_iks` change log updates
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).



### 9 December 2022
{: #containers-dec0922}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.5` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).



### 8 December 2022
{: #containers-dec0822}
{: release-note}

Ingress ALB version `1.3.1_3192_iks` change log updates
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).




### 5 December 2022
{: #containers-dec0522}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.4` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

Ingress ALB version `1.2.1_3186_iks` change log updates
:   For more information, see the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress).

 Worker node fix packs 1.22.16_1580, 1.23.14_1554, 1.24.8_1546, and 1.25.4_1524
:   For more information, see the change logs: [1.22.16_1580](/docs/containers?topic=containers-changelog_122), [1.23.14_1554](/docs/containers?topic=containers-changelog_123), [1.24.8_1546](/docs/containers?topic=containers-changelog_124), and [1.25.4_1524](/docs/containers?topic=containers-changelog_125).

### 1 December 2022
{: #containers-dec0122}
{: release-note}

CLI version 1.0.471 change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.471.


## November 2022
{: #containers-nov22}

### 30 November 2022
{: #containers-nov3022}
{: release-note}

Istio add-on version `1.16.0`
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1160).


Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for version `1.3.1_3108_iks`.





### 21 November 2022
{: #containers-nov2122}
{: release-note}



Worker node fix pack 1.22.16_1579, 1.23.14_1553, 1.24.8_1545, and 1.25.4_1523
:   For more information, see the change logs: [1.22.16_1579](/docs/containers?topic=containers-changelog_122), [1.23.14_1553](/docs/containers?topic=containers-changelog_123), [1.24.8_1545](/docs/containers?topic=containers-changelog_124), and [1.25.4_1523](/docs/containers?topic=containers-changelog_125).




### 17 November 2022
{: #containers-nov1722}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on versions `4.4.13_1712` and `5.0.2_1713`
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).




### 16 November 2022
{: #containers-nov1622}
{: release-note}



ALB OAuth Proxy add-on version 2.0.0_1315
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).
  
Master fix pack 1.22.16_1578, 1.23.14_1552, 1.24.8_1544, and 1.25.4_1522
:   For more information, see the change logs: [1.22](/docs/containers?topic=containers-changelog_122), [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).

 



### 15 November 2022
{: #containers-nov1522}
{: release-note}

New Ingress status messages
:   You can now use the **`ibmcloud ks ingress status-report get`** [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_get) to view your Ingress status. For more information, see [Checking the status of Ingress components](/docs/containers?topic=containers-ingress-status).


{{site.data.keyword.cos_full_notm}} plug-in version `2.2.3` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).


### 11 November 2022
{: #containers-nov1122}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version `4.3.8_1705`
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 10 November 2022
{: #containers-nov1022}
{: release-note}

Istio add-on version `1.15.3`
:   For more information, see the [change log](/docs/containers?topic=containers-istio-changelog#1153).


### 9 November 2022
{: #containers-nov0922}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version `4.4.12_1700` and `5.0.1_1695`
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).



### 8 November 2022
{: #containers-nov0822}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.2` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 7 November 2022
{: #containers-nov0722}
{: release-note}


Worker node fix pack 1.22.15_1577, 1.23.13_1551, 1.24.7_1543, and 1.25.3_1521
:   For more information, see the change logs: [1.22.15_1577](/docs/containers?topic=containers-changelog_122), [1.23.13_1551](/docs/containers?topic=containers-changelog_123), [1.24.7_1543](/docs/containers?topic=containers-changelog_124), and [1.25.3_1521](/docs/containers?topic=containers-changelog_125).



### 3 November 2022
{: #containers-nov0322}
{: release-note}

Changes to the Portworx update process beginning with version `2.12`.
:   Beginning with version `2.12` Portworx uses an operator-based deployment model instead of the Helm based model use in version `2.11` and earlier. If you want to update from Portworx `2.11` to version `2.12`, follow the migration steps in the [Portworx documentation](https://docs.portworx.com/portworx-enterprise/operations/operate-kubernetes/migrate-daemonset){: external}.

Cluster autoscaler add-on version `1.0.7_883`.
:   For more information, see [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

## October 2022
{: #containers-oct22}



### 31 October 2022
{: #containers-oct3122}
{: release-note}

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for version `1.3.0_2907_iks`.



### 27 October 2022
{: #containers-oct2722}
{: release-note}



ALB OAuth Proxy add-on version 2.0.0_1297
:   For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).

Master fix pack 1.22.15_1576, 1.23.13_1550, 1.24.7_1542, and 1.25.3_1520
:   For more information, see the change logs: [1.22](/docs/containers?topic=containers-changelog_122), [1.23](/docs/containers?topic=containers-changelog_123), [1.24](/docs/containers?topic=containers-changelog_124), and [1.25](/docs/containers?topic=containers-changelog_125).

 


### 26 October 2022
{: #containers-oct2622}
{: release-note}


Worker node fix pack 1.22.15_1575, 1.23.12_1549, 1.24.6_1541, and 1.25.2_1519
:   For more information, see the change logs: [1.22.15_1575](/docs/containers?topic=containers-changelog_122), [1.23.12_1549](/docs/containers?topic=containers-changelog_123), [1.24.6_1541](/docs/containers?topic=containers-changelog_124), and [1.25.2_1519](/docs/containers?topic=containers-changelog_125).



### 25 October 2022
{: #containers-oct2522}
{: release-note}

Istio add-on
:   Versions [`1.13.9`](/docs/containers?topic=containers-istio-changelog#1139), [`1.14.5`](/docs/containers?topic=containers-istio-changelog#1145), and [`1.15.2`](/docs/containers?topic=containers-istio-changelog#1152) are available.

### 24 October 2022
{: #containers-oct2422}
{: release-note}

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.3.0_2847_iks`, `1.2.1_2809_iks`, and `1.1.2_2808_iks`.

### 21 October 2022
{: #containers-oct2122}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.459.

### 12 October 2022
{: #containers-oct1222}
{: release-note}

Istio add-on
:   Version [`1.15.1`](/docs/containers?topic=containers-istio-changelog#1151) is available.


### 11 October 2022
{: #containers-oct1122}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version `5.0`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).




### 10 October 2022
{: #containers-oct1022}
{: release-note}


Worker node fix pack
:   Kubernetes [1.22.15_1574](/docs/containers?topic=containers-changelog_122), [1.23.12_1548](/docs/containers?topic=containers-changelog_123) and [1.24.6_1540](/docs/containers?topic=containers-changelog_124).


Cluster autoscaler add-on version `1.0.6_828`.
:   For more information, see [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).



### 7 October 2022
{: #containers-oct0722}
{: release-note}


Kubernetes version 1.25 certification
:   Version [1.25](/docs/containers?topic=containers-cs_versions_125) release is now certified.

### 6 October 2022
{: #containers-oct0622}
{: release-note}

New! Kubernetes 1.25
:   You can create or [update clusters to Kubernetes version 1.25](/docs/containers?topic=containers-cs_versions_125). With Kubernetes 1.25, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product. 

Master fix pack
:   Kubernetes [1.25.2_1517](/docs/containers?topic=containers-changelog_125).

Worker node fix pack
:   Kubernetes [1.25.2_1516](/docs/containers?topic=containers-changelog_125)





### 4 October 2022
{: #containers-oct0422}
{: release-note}

Istio add-on
:   Version [`1.14.4`](/docs/containers?topic=containers-istio-changelog#1144) and version [`1.13.8`](/docs/containers?topic=containers-istio-changelog#1138) are available.



### 3 October 2022
{: #containers-oct0322}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.454.


Ingress ConfigMap change log updates
:   Updated the [Ingress ConfigMap change log](/docs/containers?topic=containers-ibm-k8s-controller-config-change-log).

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.1_2646_iks` and `1.1.2_2645_iks`.

ALB OAuth Proxy add-on
:   Version 2.0.0_1265 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) is released. 



## September 2022
{: #containers-sep22}


### 30 September 2022
{: #containers-sep3022}
{: release-note}

New! Enabling Flow logs for VPC components
:    Flow logs gather information about the traffic entering or leaving your VPC cluster worker nodes.  For more information, see [Enabling Flow Logs for VPC cluster components](/docs/containers?topic=containers-vpc-flow-log).


### 26 September 2022
{: #containers-sep2622}
{: release-note}


Worker node fix pack
:   Kubernetes [1.21.14_1578](/docs/containers?topic=containers-changelog_121), [1.22.15_1573](/docs/containers?topic=containers-changelog_122), [1.23.12_1547](/docs/containers?topic=containers-changelog_123) and [1.24.6_1539](/docs/containers?topic=containers-changelog_124).




### 23 September 2022
{: #containers-sep2322}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version `4.4.11_1614`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).




### 22 September 2022
{: #containers-sep2222}
{: release-note}

Cluster autoscaler add-on versions `1.1.0_798`, `1.0.6_800`, and `1.0.5_779`.
:   For more information, see [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

{{site.data.keyword.block_storage_is_short}} add-on version `4.3.7_1613`.
:   For more information, see [the change log](/docs/containers?topic=containers-vpc_bs_changelog).


### 21 September 2022
{: #containers-sep2122}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.452.




Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.1_2558_iks` and `1.1.2_2586_iks`.




### 20 September 2022
{: #containers-sep2022}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.1` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).



### 15 September 2022
{: #containers-sep1522}
{: release-note}

Istio add-on
:   Version [`1.15.0`](/docs/containers?topic=containers-istio-changelog#1150) is available.



### 13 September 2022
{: #containers-sep1322}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version 4.4.10_1578 is available.
:   For more information, see [version 4.4.10_1578](/docs/containers?topic=containers-vpc_bs_changelog).

New! vGPU worker node flavors are now available for VPC Gen 2.
:   For more information about the available worker node flavors, see [VPC Gen 2 flavors](/docs/containers?topic=containers-vpc-flavors). Worker node flavors with vGPU support are the `gx2` flavor class, for example: `gx2.16x128.2v100`. {{site.data.keyword.vpc_short}} worker nodes with GPUs are available for allowlisted accounts only. To request that your account be allowlisted, see [Requesting access to allowlisted features](/docs/containers?topic=containers-get-help). Be sure to include the data centers, the VPC infrastructure profile, and the number of workers that you want use. For example `12 worker nodes in us-east-1 of VPC profile gx2-16x128xv100`.


### 12 September 2022
{: #containers-sep1222}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version 4.3.6_1579 is available.
:   For more information, see [version 4.3.6_1579](/docs/containers?topic=containers-vpc_bs_changelog)

{{site.data.keyword.cos_full_notm}} plug-in version `2.2.0` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.446.



ALB OAuth Proxy add-on
:   Version 2.0.0_1214 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) is released. 

### 8 September 2022
{: #containers-sep0822}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.444.

### 7 September 2022
{: #containers-sep722}
{: release-note}

Master fix pack update
:   Kubernetes [1.24.4_1536](/docs/containers?topic=containers-changelog_124), [1.23.10_1544](/docs/containers?topic=containers-changelog_123), [1.22.13_1570](/docs/containers?topic=containers-changelog_122), and [1.21.14_1579](/docs/containers?topic=containers-changelog_121).


## August 2022
{: #containers-aug22}

### 31 August 2022
{: #containers-aug3122}
{: release-note}

Cluster autoscaler add-on
:   Versions `1.0.5_775`, `1.0.6_774`, and `1.1.0_776` are available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 29 August 2022
{: #containers-aug2922}
{: release-note}

Worker node fix pack
:   Kubernetes [1.21.14_1578](/docs/containers?topic=containers-changelog_121), [1.22.13_1568](/docs/containers?topic=containers-changelog_122), [1.23.10_1543](/docs/containers?topic=containers-changelog_123) and [1.24.4_1535](/docs/containers?topic=containers-changelog_124).


### 26 August 2022
{: #containers-aug2622}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.439.

### 25 August 2022
{: #containers-aug2522}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version 4.4.9_1566 is available.
:   For more information, see [version 4.4.9_1566](/docs/containers?topic=containers-vpc_bs_changelog)



Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.1_2506_iks` and `1.1.2_2507_iks`.



### 24 August 2022
{: #containers-aug2422}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on version 4.3.5_1563 is available.

:   For more information, see [version 4.3.5_1563](/docs/containers?topic=containers-vpc_bs_changelog)

{{site.data.keyword.cos_full_notm}} plug-in version `2.1.21` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 17 August 2022
{: #containers-aug1722}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.1.20` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

Cluster autoscaler add-on
:   Versions `1.0.5_754` and `1.0.6_763` are available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 16 August 2022
{: #containers-aug1622}
{: release-note}

Worker node fix pack
:   Kubernetes [1.21.14_1576](/docs/containers?topic=containers-changelog_121), [1.22.12_1566](/docs/containers?topic=containers-changelog_122), [1.23.9_1541](/docs/containers?topic=containers-changelog_123) and [1.24.3_1533](/docs/containers?topic=containers-changelog_124).


Istio add-on
:   Version [`1.14.3`](/docs/containers?topic=containers-istio-changelog#1143) and [`1.13.7`](/docs/containers?topic=containers-istio-changelog#1137) is available.


### 11 August 2022
{: #containers-aug1122}
{: release-note}

Dynamically provision {{site.data.keyword.cos_full_notm}} buckets with quotas enabled
:   [Follow the tutorial](/docs/containers?topic=containers-storage-cos-tutorial-quota) to set up the {{site.data.keyword.cos_full_notm}} plug-in to automatically set quotas on buckets that are provisioned with PVCs. 



Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.1_2487_iks` and `1.1.2_2488_iks`.



### 5 August 2022
{: #containers-aug0522}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.433.

### 3 August 2022
{: #containers-august0322}
{: release-note}

New! {{site.data.keyword.filestorage_vpc_full_notm}} CSI Driver (Beta)
:    You can now enable the {{site.data.keyword.filestorage_vpc_full_notm}} add-on in your clusters. For more information, see [Enabling the {{site.data.keyword.filestorage_vpc_full_notm}} add-on](/docs/containers?topic=containers-storage-file-vpc-install). 




### 2 August 2022
{: #containers-aug0222}
{: release-note}

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.1_2426_iks` and `1.1.2_2411_iks`.



### 1 August 2022
{: #containers-aug0122}
{: release-note}

Worker node fix pack
:   Kubernetes [1.21.14_1575](/docs/containers?topic=containers-changelog_121), [1.22.12_1565](/docs/containers?topic=containers-changelog_122), [1.23.9_1540](/docs/containers?topic=containers-changelog_123) and [1.24.3_1532](/docs/containers?topic=containers-changelog_124).



## July 2022
{: #containers-july22}


### 27 July 2022
{: #containers-july2722}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in version `2.1.19` is available.
:   For more information, see the [change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 26 July 2022
{: #containers-july2622}
{: release-note}

Master fix pack update
:   Kubernetes [1.24.3_1531](/docs/containers?topic=containers-changelog_124), [1.23.9_1539](/docs/containers?topic=containers-changelog_123), [1.22.12_1564](/docs/containers?topic=containers-changelog_122), and [1.21.14_1574](/docs/containers?topic=containers-changelog_121).



### 22 July 2022
{: #containers-july2222}
{: release-note}




Cluster autoscaler add-on
:   Version `1.1.0_729` is available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 19 July 2022
{: #containers-july1922}
{: release-note}



Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.1.2_2368_iks` and `1.2.1_2415_iks`.



Cluster autoscaler add-on
:   Version `1.0.5_728` is available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 18 July 2022
{: #containers-july1822}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.3.4_1551](/docs/containers?topic=containers-vpc_bs_changelog) and [Version 4.4.8_1550](/docs/containers?topic=containers-vpc_bs_changelog) are available.

Worker node fix pack
:   Kubernetes [1.21.14_1572](/docs/containers?topic=containers-changelog_121), [1.22.11_1562](/docs/containers?topic=containers-changelog_122), [1.23.8_1537](/docs/containers?topic=containers-changelog_123) and [1.24.2_1529](/docs/containers?topic=containers-changelog_124).


### 15 July 2022
{: #containers-july1522}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.431.

Cluster autoscaler add-on
:   Versions `1.0.6_742` is available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 14 July 2022
{: #containers-july1422}

Cross-account encryption
:   You can now set up cross-account encryption. Note that this feature is available for allowlisted accounts only. For more information see, [Encrypting the Kubernetes secrets by using a KMS provider](/docs/containers?topic=containers-encryption).

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.18` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.block_storage_is_short}} add-on.
:   Version [5.0.1-beta_1411](/docs/containers?topic=containers-vpc_bs_changelog) is available.



### 13 July 2022
{: #containers-july1322}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.430.





### 7 July 2022
{: #containers-july0722}
{: release-note} 
 
ALB OAuth Proxy add-on
:   Version 2.0.0_1187 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) is released. 




### 5 July 2022
{: #containers-july0522}
{: release-note}

Worker node fix pack
:   Kubernetes [1.21.14_1565](/docs/containers?topic=containers-changelog_121), [1.22.11_1557](/docs/containers?topic=containers-changelog_122), [1.23.8_1535](/docs/containers?topic=containers-changelog_123) and [1.24.2_1527](/docs/containers?topic=containers-changelog_124).


Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for version `1.1.2_2305_iks`. Version `0.49.3` is no longer supported.

## June 2022
{: #containers-jun22}

### 30 June 2022
{: #containers-jun3022}
{: release-note}

Cluster autoscaler add-on
:   Versions `1.0.5_694` and `1.1.0_682` are available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 28 June 2022
{: #containers-jun2822}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.17` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

### 27 June 2022
{: #containers-jun2722}
{: release-note}

{{site.data.keyword.block_storage_is_short}}
:   You can now [set up the {{site.data.keyword.block_storage_is_short}} add-on with {{site.data.keyword.iamshort}} trusted profiles](/docs/containers?topic=containers-storage-block-vpc-trusted-profiles).

### 24 June 2022
{: #containers-jun2422}
{: release-note}

{{site.data.keyword.block_storage_is_short}}
:   You can now [create snapshots of your PVCs](/docs/containers?topic=containers-vpc-volume-snapshot) by using version `5.0.0-beta` of the {{site.data.keyword.block_storage_is_short}} add-on.

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.4.6_1446](/docs/containers?topic=containers-vpc_bs_changelog) is available.

### 22 June 2022
{: #containers-jun2222}
{: release-note}

New! Portworx Cloud Drive support
:   You can now dynamically provision storage for Portworx during installation by using Portworx Cloud Drives. For more information, see [About Portworx](/docs/containers?topic=containers-storage_portworx_about).




### 21 June 2022
{: #containers-jun2122}
{: release-note}

Istio add-on
:   Version [`1.13.5`](/docs/containers?topic=containers-istio-changelog#1135) and [`1.12.8`](/docs/containers?topic=containers-istio-changelog#1128) is available.




### 20 June 2022
{: #containers-jun2022}
{: release-note}

Worker node fix pack
:   Kubernetes [1.21.14_1564](/docs/containers?topic=containers-changelog_121), [1.22.11_1556](/docs/containers?topic=containers-changelog_122), [1.23.8_1534](/docs/containers?topic=containers-changelog_123) and [1.24.2_1526](/docs/containers?topic=containers-changelog_124).


### 17 June 2022
{: #containers-jun1722}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version version 4.3.2_1441](/docs/containers?topic=containers-vpc_bs_changelog) is available.




### 16 June 2022
{: #containers-jun1622}
{: release-note}

Certified Kubernetes
:   Version [1.24](/docs/containers?topic=containers-cs_versions_124) release is now certified.

Version 1.20 is unsupported as of 19 June 2022
:   Update your cluster to a supported as soon as possible. For more information, see the 1.20 [release information](/docs/containers?topic=containers-cs_versions_120) and [change log](/docs/containers?topic=containers-changelog_120). For more information about the supported releases, see the [version information](/docs/containers?topic=containers-cs_versions).

Istio add-on
:   Version [`1.14.1`](/docs/containers?topic=containers-istio-changelog#1141) is available.




### 15 June 2022
{: #containers-jun1522}
{: release-note}

{{site.data.keyword.mon_full_notm}} metrics and label updates
:   Metrics and labels are now stored and displayed in a Prometheus compatible naming convention. Some metrics and labels are deprecated. For more information, see [Discontinued Metrics and Labels](https://docs.sysdig.com/en/docs/release-notes/enhanced-metric-store/#discontinued-metrics-and-labels){: external} and [removed features](https://docs.sysdig.com/en/docs/release-notes/enhanced-metric-store/#removed-featurees){: external}.

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version version 5.0.1-beta_1411](/docs/containers?topic=containers-vpc_bs_changelog) is available for allowlisted accounts.




### 13 June 2022
{: #containers-jun1322}
{: release-note}


{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.4.5_1371](/docs/containers?topic=containers-vpc_bs_changelog) is available.



### 10 June 2022
{: #containers-jun1022}
{: release-note}

{{site.data.keyword.loganalysisshort}} and {{site.data.keyword.at_full_notm}} changes
:   {{site.data.keyword.containerlong_notm}} clusters running in Washington, D.C. (`us-east`) now send logs to {{site.data.keyword.loganalysisshort}} and {{site.data.keyword.at_full_notm}} instances in the same region, Washington, D.C. (`us-east`). For more information, see [{{site.data.keyword.at_full_notm}}](/docs/containers?topic=containers-at_events).

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for version `1.2.1_2337_iks`.

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 5.0.0-beta_1125](/docs/containers?topic=containers-vpc_bs_changelog) is available for allowlisted accounts.

### 9 June 2022
{: #containers-jun922}
{: release-note}

New! Kubernetes 1.24
:   You can create or [update clusters to Kubernetes version 1.24](/docs/containers?topic=containers-cs_versions_124). With Kubernetes 1.24, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product. 

Deprecated and unsupported Kubernetes versions
:   With the release of Kubernetes 1.24, clusters that run version 1.21 are deprecated, with a tentative unsupported date of 31 Aug 2022. Update your cluster to at least [version 1.22](/docs/containers?topic=containers-cs_versions_122) as soon as possible.

### 7 June 2022
{: #containers-jun722}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.419.

### 6 June 2022
{: #containers-jun622}
{: release-note}

Worker node fix pack
:   Kubernetes [1.20.15_1583](/docs/containers?topic=containers-changelog_120), [1.21.13_1562](/docs/containers?topic=containers-changelog_121), [1.22.10_1554](/docs/containers?topic=containers-changelog_122), [1.23.7_1532](/docs/containers?topic=containers-changelog_123).


### 3 June 2022
{: #containers-jun322}
{: release-note}

Master fix pack update
:   Kubernetes [1.23.7_1531](/docs/containers?topic=containers-changelog_123), [1.22.10_1553](/docs/containers?topic=containers-changelog_122), [1.21.13_1561](/docs/containers?topic=containers-changelog_121), and [1.20.15_1582](/docs/containers?topic=containers-changelog_120).




### 1 June 2022
{: #containers-jun122}
{: release-note}

Istio add-on
:   Version [`1.13.4`](/docs/containers?topic=containers-istio-changelog#1134) is available.

## May 2022
{: #containers-may22}


### 26 May 2022
{: #containers-may2622}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.415.


### 25 May 2022
{: #containers-may2522}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.16` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.3.0_1163](/docs/containers?topic=containers-vpc_bs_changelog) is available.

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2.6_1161](/docs/containers?topic=containers-vpc_bs_changelog) is available.

### 20 May 2022
{: #containers-may2022}
{: release-note}

Worker node fix pack
:   Kubernetes [1.20.15_1581](/docs/containers?topic=containers-changelog_120), [1.21.12_1560](/docs/containers?topic=containers-changelog_121), [1.22.9_1552](/docs/containers?topic=containers-changelog_122), [1.23.6_1530](/docs/containers?topic=containers-changelog_123).


### 19 May 2022
{: #containers-may1922}
{: release-note}

Istio add-on
:   Version [`1.12.7`](/docs/containers?topic=containers-istio-changelog#1127) is available.

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.0_2251_iks`, `1.1.2_2252_iks`, and `0.49.3_2253_iks`.


### 16 May 2022
{: #containers-may1622}
{: release-note}

Cluster autoscaler add-on
:   Versions `1.0.5_628` and `1.1.0_615` are available. See [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

ALB OAuth Proxy add-on
:   Version 1.0.0 is no longer supported. For more information, see the [change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).

### 12 May 2022
{: #containers-may1222}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2.5_1106](/docs/containers?topic=containers-vpc_bs_changelog) is available.

### 9 May 2022
{: #containers-may0922}
{: release-note}

Worker node fix pack
:   Kubernetes [1.20.15_1580](/docs/containers?topic=containers-changelog_120), [1.21.12_1559](/docs/containers?topic=containers-changelog_121), [1.22.9_1551](/docs/containers?topic=containers-changelog_122), [1.23.6_1529](/docs/containers?topic=containers-changelog_123).



### 6 May 2022
{: #containers-may0622}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.15` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

### 4 May 2022
{: #containers-may0422}
{: release-note}

  
ALB OAuth Proxy add-on
:   Version 2.0.0_1064 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) is released.
Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.2.0_2147_iks`, `1.1.2_2146_iks`, and `0.49.3_2145_iks`.




### 3 May 2022
{: #containers-may0322}
{: release-note}

Istio add-on
:   Version [`1.13.3`](/docs/containers?topic=containers-istio-changelog#1133) is available. 

## April 2022
{: #containers-apr22}


### 28 April 2022
{: #containers-apr2822}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.404.



Cluster security groups
:   You can now specify up to five security groups to attach to workers when you create a VPC cluster. For more information, see [Adding VPC security groups to clusters and worker pools during create time](/docs/containers?topic=containers-vpc-security-group).

### 26 April 2022
{: #containers-apr2622}
{: release-note}

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for version `1.2.0_2131_iks`. Version `1.1.1` is no longer available.


CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.403.

### 25 April 2022
{: #containers-apr2522}  
{: release-note}

Worker node fix pack
:   Kubernetes [1.23.6_1528](/docs/containers?topic=containers-changelog_123), [1.22.9_1550](/docs/containers?topic=containers-changelog_122), [1.21.12_1558](/docs/containers?topic=containers-changelog_121), [1.20.15_1579](/docs/containers?topic=containers-changelog_120).




  
### 21 April 2022
{: #containers-apr2122}  
{: release-note}
  
Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.1.2_2121_iks`, `1.1.1_2119_iks`, and `0.49.3_2120_iks`.
  




### 19 April 2022
{: #containers-apr1922}

Istio add-on
:   Version [`1.12.6`](/docs/containers?topic=containers-istio-changelog#1126) is available. 

### 13 April 2022
{: #containers-apr1322}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.14` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

### 12 April 2022
{: #containers-apr1222}



Create and manage dedicated hosts in VPC Gen 2.
:   You can now create clusters on dedicated hosts in VPC Gen 2. Note that support for dedicated hosts is available only for allowlisted accounts. For more information, see [Creating and managing dedicated hosts](/docs/containers?topic=containers-dedicated-hosts).

  
### 11 April 2022
{: #containers-apr1122}



New! {{site.data.keyword.secrets-manager_full}}
:   With the deprecation of {{site.data.keyword.cloudcerts_long}}, you can now manage certificates and secrets with {{site.data.keyword.secrets-manager_full}}. You can integrate your own {{site.data.keyword.secrets-manager_short}} instances with your Kubernetes clusters. {{site.data.keyword.secrets-manager_short}} instances can be used across multiple clusters, and a single cluster can have more than one instance. 



{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2.3_983](/docs/containers?topic=containers-vpc_bs_changelog) is available.

Worker node fix pack
:   Kubernetes [1.23.5_1526](/docs/containers?topic=containers-changelog_123), [1.22.8_1548](/docs/containers?topic=containers-changelog_122), [1.21.11_1556](/docs/containers?topic=containers-changelog_121), [1.20.15_1577](/docs/containers?topic=containers-changelog_120).





### 7 April 2022
{: #containers-apr0722}

{{site.data.keyword.containerlong_notm}} clusters in Mexico City (MEX01) are deprecated and become unsupported later this year. 
:   To prevent any interruption of service, [redeploy your cluster workloads](/docs/containers?topic=containers-update_app#copy_apps_cluster) to a [supported data center](/docs/containers?topic=containers-regions-and-zones#zones-mz) and remove your MEX01 clusters by 31 October 2022. Clusters remaining in these data centers after 31 October 2022 will be removed. You cannot create clusters in this location after 07 May 2022. For more information about data center closures and recommended data centers, see [Data center consolidations](/docs/get-support?topic=get-support-dc-closure).


Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.1.2_2084_iks`, `1.1.1_2085_iks`, and `0.49.3_2083_iks`.




CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.394.

### 6 April 2022
{: #containers-apr0622}}

Master fix pack update
:   Kubernetes [1.23.5_1525](/docs/containers?topic=containers-changelog_123), [1.22.8_1547](/docs/containers?topic=containers-changelog_122), [1.21.11_1555](/docs/containers?topic=containers-changelog_121), and [1.20.15_1576](/docs/containers?topic=containers-changelog_120).






## March 2022
{: #containers-mar22}

### 30 March 2022
{: #containers-mar3022}
{: release-note}

Cluster autoscaler add-on
:   Version [1.1.0_475](/docs/containers?topic=containers-ca_changelog) is available.

{{site.data.keyword.containershort}} 1.20 end of support date change
:   The end of support date of {{site.data.keyword.containershort}} 1.20 is now 15 June 2022. The [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions#cs_versions_available) page has been updated with the new date. 

Master fix pack update
:   Kubernetes [1.23.5_1523](/docs/containers?topic=containers-changelog_123#1235_1523), [1.22.8_1545](/docs/containers?topic=containers-changelog_122#1228_1545), [1.21.11_1553](/docs/containers?topic=containers-changelog_121#12111_1553), and [1.20.15_1574](/docs/containers?topic=containers-changelog_120#12015_1574).

### 28 March 2022
{: #containers-mar2822}
{: release-note}

Worker node fix pack update.
:   Kubernetes [1.23.5_1524](/docs/containers?topic=containers-changelog_123), [1.22.8_1546](/docs/containers?topic=containers-changelog_122), [1.21.11_1552](/docs/containers?topic=containers-changelog_121), [1.20.15_1575](/docs/containers?topic=containers-changelog_120), and [1.19.16_1579](/docs/containers?topic=containers-changelog_119).


### 24 March 2022
{: #containers-mar2422}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.13` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2.2_900](/docs/containers?topic=containers-vpc_bs_changelog) is available.

  
ALB OAuth Proxy add-on
:   Versions 1.0.0_1024 and 2.0.0_1023 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) are released.



### 22 March 2022
{: #containers-mar2222}
{: release-note}

Hong Kong (`HKG02`) and Seoul (`SEO01`) are deprecated and become unsupported later this year.
:   To prevent any interruption of service, [redeploy your cluster workloads](/docs/containers?topic=containers-update_app#copy_apps_cluster) to a [supported data center](/docs/containers?topic=containers-regions-and-zones#zones-mz) and remove your Hong Kong (`HKG02`) and Seoul (`SEO01`) clusters by 28 September 2022. Clusters remaining in these data centers after 28 September 2022 will be removed. Cluster creation in these locations will be stopped on 29 April 2022. For more information about data center closures and recommended data centers, see [Data center consolidations](/docs/get-support?topic=get-support-dc-closure).

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `1.1.2_2050_iks`, `1.1.1_1996_iks`, and `0.49.3_1994_iks`.

Istio add-on
:   Versions [`1.13.2`](/docs/containers?topic=containers-istio-changelog#1132), [`1.12.5`](/docs/containers?topic=containers-istio-changelog#1125), and [`1.11.8`](/docs/containers?topic=containers-istio-changelog#1118) are available. Note that this is the final update for version 1.11. 


### 21 March 2022
{: #containers-mar2122}
{: release-note}

CLI change log update
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.384.

### 17 March 2022
{: #containers-mar1722}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2.1_895](/docs/containers?topic=containers-vpc_bs_changelog) is available.


  
### 16 March 2022
{: #containers-mar1622}
{: release-note}

Cluster autoscaler add-on
:   Version [1.1.0_429](/docs/containers?topic=containers-ca_changelog) is available.

### 15 March 2022
{: #containers-mar1522}
{: release-note}

Version 1.19 unsupported 
:   Clusters that run version 1.19 are unsupported. Update your clusters to at least [version 1.20](/docs/containers?topic=containers-cs_versions_120) as soon as possible.


### 14 March 2022
{: #containers-mar1422}
{: release-note}


Worker node fix pack update.
:   Kubernetes [1.23.4_1522](/docs/containers?topic=containers-changelog_123), [1.22.7_1543](/docs/containers?topic=containers-changelog_122), [1.21.10_1552](/docs/containers?topic=containers-changelog_121), [1.20.15_1573](/docs/containers?topic=containers-changelog_120), and [1.19.16_1579](/docs/containers?topic=containers-changelog_119).




### 11 March 2022
{: #containers-mar1122}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.12` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).



### 9 March 2022
{: #containers-mar922}
{: release-note}

Istio add-on
:   [Version `1.13.1`](/docs/containers?topic=containers-istio-changelog#1131) is available.





### 8 March 2022
{: #containers-mar822}
{: release-note}

Master fix pack update.
:   Kubernetes [1.23.4_1520](/docs/containers?topic=containers-changelog_123#1234_1520), [1.22.7_1541](/docs/containers?topic=containers-changelog_122#1227_1541), [1.21.10_1550](/docs/containers?topic=containers-changelog_121#12110_1550), [1.20.15_1571](/docs/containers?topic=containers-changelog_120#12015_1571), and [1.19.16_1578](/docs/containers?topic=containers-changelog_119#11916_1578).




Istio add-on
:   [Version `1.12.4`](/docs/containers?topic=containers-istio-changelog#1124) and [Version `1.11.7`](/docs/containers?topic=containers-istio-changelog#1117) of the managed Istio add-on are available. 





### 3 March 2022
{: #containers-mar322}
{: release-note}


{{site.data.keyword.containershort}} default version update.
:   [1.22](/docs/containers?topic=containers-cs_versions#cs_versions_available) is now the default version.

Maintenance Windows for {{site.data.keyword.containershort}} ALBs
:   You can now further control and manage your ALB updates by [creating a customized ConfigMap](/docs/containers?topic=containers-ingress-alb-manage#alb-scheduled-updates) that specifies the time you want the updates to occur and the percentage of ALBs you want to update.



## February 2022
{: #containers-feb22}

### 28 February 2022
{: #containers-feb2822}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.2](/docs/containers?topic=containers-vpc_bs_changelog) is available.

Cluster autoscaler
:   Version [1.0.5_415](/docs/containers?topic=containers-ca_changelog) is available.
:   New pages for [Preparing your cluster for autoscaling](/docs/containers?topic=containers-cluster-scaling-install-addon), [Installing the cluster autoscaler add-on](/docs/containers?topic=containers-cluster-scaling-install-addon), and [Enabling autoscaling](/docs/containers?topic=containers-cluster-scaling-install-addon-enable).
:   New troubleshooting pages for [resizing worker pools](/docs/containers?topic=containers-ts-ca-resize) and updating [unbalanced worker pools](/docs/containers?topic=containers-ts-ca-unbalanced) in autoscaled clusters. 


  
ALB OAuth Proxy add-on
:   Versions 1.0.0_1001 and 2.0.0_999 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) are released.


Worker node fix pack
:   Kubernetes [1.23.4_1521](/docs/containers?topic=containers-changelog_123#1234_1521), [1.22.7_1542](/docs/containers?topic=containers-changelog_122#1227_1542), [1.21.10_1551](/docs/containers?topic=containers-changelog_121#12110_1551), [1.20.15_1572](/docs/containers?topic=containers-changelog_120#12015_1572), and [1.19.16_1579](/docs/containers?topic=containers-changelog_119#11916_1579).


### 24 February 2022
{: #containers-feb2422}
{: release-note}


Container service CLI 
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.374.



Kubernetes Ingress image
:   Versions 1.1.1_1996_iks, 1.0.3_1995_iks, and 0.49.3_1994_iks of the [Kubernetes Ingress image](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) are released.






### 23 February 2022
{: #containers-feb2322}
{: release-note}

Cluster autoscaler
:   Version [1.0.4_410](/docs/containers?topic=containers-ca_changelog) is available.



Istio add-on
:   [Version `1.12.3`](/docs/containers?topic=containers-istio-changelog#1116) of the managed Istio add-on is available. 




### 18 February 2022
{: #containers-feb1822}
{: release-note}

Container service CLI 
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.372.


### 17 February 2022
{: #containers-feb1722}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.10` of the {{site.data.keyword.cos_full_notm}} plug-in [is available](/docs/containers?topic=containers-cos_plugin_changelog).




  
### 15 February 2022
{: #containers-feb1522}
{: release-note}

Istio add-on
:   [Version `1.11.6`](/docs/containers?topic=containers-istio-changelog#1116) of the managed Istio add-on is available. 



### 14 February 2022
{: #containers-feb1422}
{: release-note}

Worker node fix pack
:   Kubernetes [1.23.3_1519](/docs/containers?topic=containers-changelog_123#1233_1519), [1.22.6_1539](/docs/containers?topic=containers-changelog_122#1226_1539), [1.21.9_1549](/docs/containers?topic=containers-changelog_121#1219_1549), [1.20.15_1570](/docs/containers?topic=containers-changelog_120#12015_1570), and [1.19.16_1577](/docs/containers?topic=containers-changelog_119#11916_1577).


{{site.data.keyword.cos_full_notm}} doc restructuring. 
:   For more information, see [Setting up {{site.data.keyword.cos_full_notm}}](/docs/containers?topic=containers-storage-cos-understand), [Installing the {{site.data.keyword.cos_full_notm}} plug-in](/docs/containers?topic=containers-storage_cos_install), [Setting up authorized IP addresses for {{site.data.keyword.cos_full_notm}}](/docs/containers?topic=containers-storage_cos_vpc_ip), [Adding {{site.data.keyword.cos_full_notm}} storage to apps](/docs/containers?topic=containers-storage_cos_apps), and [Storage class reference](/docs/containers?topic=containers-storage_cos_reference).


{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.1.3_846](/docs/containers?topic=containers-vpc_bs_changelog) is released.


### 10 February 2022
{: #containers-feb1022}
{: release-note}


Certified Kubernetes
:   Version [1.23](/docs/containers?topic=containers-cs_versions_123) release is now certified.


  
ALB OAuth Proxy add-on
:   Version 2.0.0_981 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) is released.




### 9 February 2022
{: #containers-feb922}
{: release-note}




New! Kubernetes 1.23
:   You can create or [update clusters to Kubernetes version 1.23](/docs/containers?topic=containers-cs_versions_123). With Kubernetes 1.23, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product.

Deprecated and unsupported Kubernetes versions
:   With the release of Kubernetes 1.23, clusters that run version 1.20 remain deprecated, with a tentative unsupported date of May 2022. Update your cluster to at least [version 1.21](/docs/containers?topic=containers-cs_versions_121) as soon as possible.




  


### 3 February 2022
{: #containers-feb322}
{: release-note}

Istio add-on
:   [Version `1.12.2`](/docs/containers?topic=containers-istio-changelog#1122) of the managed Istio add-on is available. 





## January 2022
{: #containers-jan22}

### 31 January 2022
{: #containers-jan3122}

Version change log
:   Fix pack update.
:   Kubernetes [1.22.6_1538](/docs/containers?topic=containers-changelog_122#1226_1538), [1.21.9_1548](/docs/containers?topic=containers-changelog_121#1219_1548), [1.20.15_1569](/docs/containers?topic=containers-changelog_120#12015_1569), [1.19.16_1576](/docs/containers?topic=containers-changelog_119#11916_1576).



**New!** Worker node flavor reference
:   View a list of all available worker node flavors by zone. For more information, see [VPC Gen 2 flavors](/docs/containers?topic=containers-classic-flavors) or [Classic flavors](/docs/containers?topic=containers-vpc-flavors).



### 27 January 2022
{: #containers-jan2722}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.1.2_834](/docs/containers?topic=containers-vpc_bs_changelog) is released.

**New!** Gathering Ingress logs
:   When troubleshooting Ingress, follow the steps in [gathering Ingress logs](/docs/containers?topic=containers-ingress-must-gather) to retrieve useful debugging information.





### 26 January 2022
{: #containers-jan2622}
{: release-note}

ALB OAuth Proxy add-on
:   Versions 1.0.0_924 and 2.0.0_923 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) are released.



### 25 January 2022
{: #containers-jan2522}
{: release-note}


Kubernetes Ingress image
:   Versions 1.1.1_1949_iks, 1.0.3_1933_iks, and 0.49.3_1941_iks of the [Kubernetes Ingress image](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) are released.
  
Kubernetes Ingress annotations
:   Clusters created on or after 31 January 2022 by default no longer support server-snippet annotations in Ingress resources for the managed Kubernetes Ingress Controller (ALB). All new clusters are deployed with the `allow-server-snippets` configuration set to `false`, which prevents the ALB from correctly processing Ingress resources with the offending annotations. You must edit the ConfigMap manually to change this setting in order for the add-on to work.



### 24 January 2022
{: #containers-jan2422}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.9` of the {{site.data.keyword.cos_full_notm}} plug-in is released. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).


### 20 January 2022
{: #containers-jan2022}
{: release-note}

Cluster autoscaler add-on.
:   [Version 1.0.4_403](/docs/containers?topic=containers-ca_changelog) is released.

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.1.1_827](/docs/containers?topic=containers-vpc_bs_changelog) is released.

OpenShift Data Foundation
:   New and updated parameters for OpenShift Data Foundation.
:   Automatic disk discovery is now available for Classic clusters version 4.8 and later. Enable this feature by setting the `autoDiscoverDevices` parameter to `true` parameter. For more information, see [ODF using local disks](/docs/openshift?topic=openshift-deploy-odf-classic).
:   The `monDevicePaths` and `monSize` parameters are no longer required for add-on version 4.8 and later.



### 18 January 2022
{: #containers-jan1822}
{: release-note}

Review the release notes for January 2022.
{: shortdesc}

**New!** {{site.data.keyword.containerlong_notm}} CLI Map
:   The [{{site.data.keyword.containerlong_notm}} CLI Map](/docs/containers?topic=containers-icks_map) lists all `ibmcloud ks` commands as they are structured in the CLI. Use this page as a visual reference for how ibmcloud ks commands are organized, or to quickly find a specific command. 

{{site.data.keyword.containershort}} 1.19, 1.20, 1.21, and 1.22 unsupported date change
:   The [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions#cs_versions_available) page has been updated with the new unsupported dates. 

Worker node fix pack update.
:   Kubernetes [1.22.4_1536](/docs/containers?topic=containers-changelog_122#1224_1536), [1.21.7_1546](/docs/containers?topic=containers-changelog_121#1217_1546), [1.20.13_1567](/docs/containers?topic=containers-changelog_120#12013_1567), and [1.19.16_1574](/docs/containers?topic=containers-changelog_119#11916_1574).



### 17 January 2022
{: #containers-jan1722}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.8` of the {{site.data.keyword.cos_full_notm}} plug-in is released. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).



### 13 January 2022
{: #containers-jan1321}
{: release-note}

Istio add-on
:   [Version `1.12.1`](/docs/containers?topic=containers-istio-changelog#1121) and [Version `1.10.6`](/docs/containers?topic=containers-istio-changelog#1106) of the Istio managed add-on are released.






### 06 January 2022
{: #containers-jan0622}
{: release-note}


{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.1.0_807](/docs/containers?topic=containers-vpc_bs_changelog) is released.


{{site.data.keyword.containershort}} 1.20 end of support date change
:   The end of support date of {{site.data.keyword.containershort}} 1.20 is now March 2022. The [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions#cs_versions_available) page has been updated with the new date. 


### 4 January 2022
{: #containers-jan422}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for worker node versions [`1.22.4_1534`](/docs/containers?topic=containers-changelog_122#1224_1534), [`1.21.7_1544`](/docs/containers?topic=containers-changelog_121#1217_1544), [`1.20.13_1566`](/docs/containers?topic=containers-changelog_120#12013_1566), and [`1.19.16_1573`](/docs/containers?topic=containers-changelog_119#11916_1573).

## December 2021
{: #containers-dec21}

Review the release notes for December 2021.
{: shortdesc}

### 20 December 2021
{: #containers-dec2021}
{: release-note}





  
Deprecated and unsupported Kubernetes versions
:   Clusters that run version 1.19 are deprecated, with a tentative unsupported date of 31 Jan 2022. Update your clusters to at least [version 1.20](/docs/containers?topic=containers-cs_versions_120) as soon as possible.


### 14 December 2021
{: #containers-dec1421}
{: release-note}


Istio add-on
:   [Version `1.11.5`](/docs/containers?topic=containers-istio-changelog#1115) of the Istio managed add-on is released.



### 7 December 2021
{: #containers-dec721}
{: release-note}



Istio add-on
:   [Version `1.12`](/docs/containers?topic=containers-istio-changelog#1102) of the Istio managed add-on is released.

Master fix pack update
:   Change log documentation is available for version [`1.22.4_1531`](/docs/containers?topic=containers-changelog_122#1224_1531), [`1.21.7_1541`](/docs/containers?topic=containers-changelog_121#1217_1541), [`1.20.13_1563`](/docs/containers?topic=containers-changelog_120#12013_1563), and [`1.19.16_1570`](/docs/containers?topic=containers-changelog_119#11916_1570).



### 6 December 2021
{: #containers-dec621}
{: release-note}



Worker node fix pack update
:   Change log documentation is available for version [`1.22.4_1532`](/docs/containers?topic=containers-changelog_122#1224_1532), [`1.21.7_1542`](/docs/containers?topic=containers-changelog_121#1217_1542), [`1.20.13_1564`](/docs/containers?topic=containers-changelog_120#12013_1564), and [`1.19.16_1571`](/docs/containers?topic=containers-changelog_119#11916_1571).



### 2 December 2021
{: #containers-dec221}
{: release-note}



{{site.data.keyword.containershort}} default version update.
:   [1.21](/docs/containers?topic=containers-cs_versions#cs_versions_available) is now the default version.




## November 2021
{: #containers-nov21}

Review the release notes for November 2021.
{: shortdesc}


### 29 November 2021
{: #containers-nov2921}
{: release-note}

Container service CLI 
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.347.



### 22 November 2021
{: #containers-nov2221}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for version [`1.22.3_1530`](/docs/containers?topic=containers-changelog_122#1223_1530), [`1.21.6_1540`](/docs/containers?topic=containers-changelog_121#1216_1540), [`1.20.12_1562`](/docs/containers?topic=containers-changelog_120#12012_1562), and [`1.19.16_1569`](/docs/containers?topic=containers-changelog_119#11916_1569).

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.0.3_793](/docs/containers?topic=containers-vpc_bs_changelog) is released.

Cluster autoscaler add-on.
:   [Version 1.0.4_387](/docs/containers?topic=containers-ca_changelog) is released.


### 19 November 2021
{: #containers-nov1921}
{: release-note}



ALB OAuth Proxy add-on
:   Versions 1.0.0_756 and 2.0.0_755 of the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog) are released.

Kubernetes Ingress image
:   Versions `1.0.3_1730_iks` and `0.49.3_1830_iks` of the [Kubernetes Ingress image](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) are released.



### 18 November 2021
{: #containers-nov1821}
{: release-note}

{{site.data.keyword.cloudaccesstraillong_notm}} and {{site.data.keyword.at_full_notm}}
:   Previously, clusters running in Toronto (`ca-tor`) sent logs to Washington D.C., and clusters running in Osaka (`jp-osa`) or Sydney (`au-syd`) sent logs to Tokyo. Beginning 18 November 2021, all instances of Log Analysis and Activity Tracker that are used for clusters running in Osaka (`jp-osa`), Toronto (`ca-tor`), and Sydney (`au-syd`) send logs to their respective regions. To continue receiving logs for clusters in these regions, you must create instances of {{site.data.keyword.cloudaccesstraillong_notm}} and {{site.data.keyword.at_full_notm}} in the same region as your cluster. If you already have instances in these regions, look for logs in those instances.

{{site.data.keyword.cos_full_notm}}
:   Version 2.1.7 of the [{{site.data.keyword.cos_full_notm}} plug-in](/docs/containers?topic=containers-cos_plugin_changelog) is released.

  
### 17 November 2021
{: #containers-nov1721}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for version [`1.22.3_1529`](/docs/containers?topic=containers-changelog_122#1223_1529), [`1.21.6_1539`](/docs/containers?topic=containers-changelog_121#1216_1539), [`1.20.12_1561`](/docs/containers?topic=containers-changelog_120#12012_1561), and [`1.19.16_1568`](/docs/containers?topic=containers-changelog_119#11916_1568).


### 15 November 2021
{: #containers-nov1521}
{: release-note}

CLI change log
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.344. 

### 12 November 2021
{: #containers-nov1221}
{: release-note}

Master fix pack updates
:   Change log documentation is available for version  [`1.22.2_1526`](/docs/containers?topic=containers-changelog_122#1222_1526), [`1.21.5_1536`](/docs/containers?topic=containers-changelog_121#1215_1536), [`1.20.11_1558`](/docs/containers?topic=containers-changelog_120#12011_1558), and [`1.19.15_1565`](/docs/containers?topic=containers-changelog_119#11915_1565).

### 10 November 2021
{: #containers-nov1021}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for version [`1.22.2_1528`](/docs/containers?topic=containers-changelog_122#1222_1528), [`1.21.5_1538`](/docs/containers?topic=containers-changelog_121#1215_1538), [`1.20.11_1560`](/docs/containers?topic=containers-changelog_120#12011_1560), and [`1.19.15_1567`](/docs/containers?topic=containers-changelog_119#11915_1567).

### 8 November 2021
{: #containers-nov821}
{: release-note}

Update commands to use `docker build`
:   Updates commands that use `cr build` to use `docker build` instead. 


### 4 November 2021
{: #containers-nov421}
{: release-note}

IAM trusted profiles for pod authorization
:   Updates for pod authorization with IAM trusted profiles. Authorizing pods with IAM trusted profiles is available for clusters that run version 1.21 or later. Note that for new clusters, authorizing pods with IAM trusted profiles is enabled automatically. You can enable IAM trusted profiles on existing clusters by running [`ibmcloud ks cluster master refresh`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_refresh). For more information, see [Authorizing pods in your cluster to IBM Cloud services with IAM trusted profiles](/docs/containers?topic=containers-pod-iam-identity).


### 2 November 2021
{: #containers-nov221}
{: release-note}

Istio add-on change log
:   [Version `1.11.4`](/docs/containers?topic=containers-istio-changelog#1114) of the Istio managed add-on is released.



## October 2021
{: #containers-oct21}

Review the release notes for October 2021.
{: shortdesc}

### 28 October 2021
{: #containers-oct2821}
{: release-note}

Istio add-on change log
:   [Version `1.10.5`](/docs/containers?topic=containers-istio-changelog#1105) of the Istio managed add-on is released.

### 26 October 2021
{: #containers-oct2621}
{: release-note}

CLI change log
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.334. 

### 25 October 2021
{: #containers-oct2521}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for version [`1.22.2_1527`](/docs/containers?topic=containers-changelog_122#1222_1527), [`1.21.5_1537`](/docs/containers?topic=containers-changelog_121#1215_1537), [`1.20.11_1559`](/docs/containers?topic=containers-changelog_120#12011_1559), and [`1.19.15_1566`](/docs/containers?topic=containers-changelog_119#11915_1566).

### 22 October 2021
{: #containers-oct2221}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in.
:   [Version 2.1.6](/docs/containers?topic=containers-cos_plugin_changelog) is released.

### 19 October 2021
{: #containers-oct1921}
{: release-note}

Ingress ALB change log updates
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress) for versions `0.49.3_1745_iks` and `1.0.3_1730_iks`.

### 18 October 2021
{: #containers-oct1821}
{: release-note}

New troubleshooting topic
:   See [Why does my cluster master status say it is approaching its resource limit?](/docs/containers?topic=containers-master_resource_limit). 



### 13 October 2021
{: #containers-oct1321}
{: release-note}

CLI change log
:   The [CLI change log](/docs/containers?topic=containers-cs_cli_changelog) is updated for version 1.0.331. 

### 11 October 2021
{: #containers-oct1121}
{: release-note}



Unsupported Kubernetes version 1.18
:   Kubernetes version 1.18 is unsupported. To continue receiving important security updates and support, you must [update your cluster to a supported version](/docs/containers?topic=containers-cs_versions#prep-up) immediately. 



Worker node fix pack update
:   Change log documentation is available for version [`1.22.2_1524`](/docs/containers?topic=containers-changelog_122#1222_1524), [`1.21.5_1533`](/docs/containers?topic=containers-changelog_121#1215_1533), [`1.20.11_1555`](/docs/containers?topic=containers-changelog_120#12011_1555), and [`1.19.15_1562`](/docs/containers?topic=containers-changelog_119#11915_1562).

### 7 October 2021
{: #containers-oct721}
{: release-note}

Istio add-on change log
:   [Version `1.11.3`](/docs/containers?topic=containers-istio-changelog#1113) of the Istio managed add-on is released.

Cluster autoscaler add-on.
:   [Version 1.0.4](/docs/containers?topic=containers-ca_changelog) is released.



### 6 October 2021
{: #containers-oct621}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on.
:   [Version 4.0.1_780](/docs/containers?topic=containers-vpc_bs_changelog) is released.


### 5 October 2021
{: #containers-oct521}
{: release-note}

Updated supported, deprecated, and unsupported versions for strongSwan Helm chart.
:   [Upgrading or disabling the strongSwan Helm chart](/docs/containers?topic=containers-vpn#vpn_upgrade)



{{site.data.keyword.cos_full_notm}} plug-in.
:   [Version 2.1.5](/docs/containers?topic=containers-cos_plugin_changelog) is released.


## September 2021
{: #containers-sep21}

Review the release notes for September 2021.
{: shortdesc}

### 29 September 2021
{: #containers-sep2921}
{: release-note}



New! Kubernetes 1.22
:   You can create or [update clusters to Kubernetes version 1.22](/docs/containers?topic=containers-cs_versions_122). With Kubernetes 1.22, you get the latest stable enhancements from the Kubernetes community as well as enhancements to the {{site.data.keyword.cloud_notm}} product. For more information, [see the blog announcement](https://www.ibm.com/blog/announcement/kubernetes-version-121-now-available-in-ibm-cloud-kubernetes-service/){: external}.

Deprecated and unsupported Kubernetes versions
:   With the release of Kubernetes 1.22, clusters that run version 1.18 remain deprecated, with a tentative unsupported date of 10 Oct 2021. Update your cluster to at least [version 1.20](/docs/containers?topic=containers-cs_versions_120) as soon as possible.

Master fix pack and worker node fix pack update
:   Change log documentation is available for Kubernetes version [`1.22.2_1522` and `1.22.2_1523`](/docs/containers?topic=containers-changelog_122#1222_1522_and_1222_1523).





### 27 September 2021
{: #containers-sep2721}
{: release-note}

Master fix pack update
:   Change log documentation is available for version [`1.21.5_1531`](/docs/containers?topic=containers-changelog_121#1215_1531), [`1.20.11_1553`](/docs/containers?topic=containers-changelog_120#12011_1553), [`1.19.15_1560`](/docs/containers?topic=containers-changelog_119#11915_1560), [`1.18.20_1565`](/docs/containers?topic=containers-118_changelog#11820_1565).


Worker node fix pack update
:   Change log documentation is available for version [`1.18.20_1566`](/docs/containers?topic=containers-118_changelog#11820_1566), [`1.19.15_1561`](/docs/containers?topic=containers-changelog_119#11915_1561), [`12011_1554`](/docs/containers?topic=containers-changelog_120#12011_1554), and [`1.21.5_1532`](/docs/containers?topic=containers-changelog_121#1215_1532).

### 23 September 2021
{: #containers-sep2321}
{: release-note}

Review the release notes for 23 September 2021.
{: shortdesc}

Istio add-on change log
:   [Version `1.11.2`](/docs/containers?topic=containers-istio-changelog#1112) of the Istio managed add-on is released.

### 22 September 2021
{: #containers-sep2221}
{: release-note}

Review the release notes for 22 September 2021.
{: shortdesc}

Ingress ALB version change log
:   [Version `1.0.0_1699_iks`](/docs/containers?topic=containers-cs_versions_ingress#1_0_0) is now available. Updates for versions [`0.48.1_1698_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_48_0) and [`0.43.0_1697_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_47_0) are available in the change log. 




### 16 September 2021
{: #containers-sep1621}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on  
:   Version [`4.0.0_769`](/docs/containers?topic=containers-vpc_bs_changelog) is available.




### 14 September 2021
{: #containers-sep1421}
{: release-note}

Review the release notes for 14 September 2021.
{: shortdesc}

Ingress ALB version change log
:   [Version `1.0.0_1645_iks`](/docs/containers?topic=containers-cs_versions_ingress#1_0_0) is now available. Updates for versions [`0.48.1_1613_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_48_0) and [`0.47.0_1614_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_47_0) are available in the change log. 

Istio add-on change log
:   [Version `1.10.4`](/docs/containers?topic=containers-istio-changelog#1104) and [version `1.9.8`](/docs/containers?topic=containers-istio-changelog#198) of the Istio managed add-on is released.


### 13 September 2021
{: #containers-sep1321}
{: release-note}

Worker node fix pack update
:   Change log documentation is available for version [`1.18.20_1564`](/docs/containers?topic=containers-118_changelog#11820_1564), [`1.19.14_1559`](/docs/containers?topic=containers-changelog_119#11914_1559), [`1.20.10_1552`](/docs/containers?topic=containers-changelog_120#12010_1552), and [`1.21.4_1530`](/docs/containers?topic=containers-changelog_121#12104_1530).

### 9 September 2021
{: #containers-sep921}
{: release-note}

Ingress ALB change log
:   Updated the [change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions `0.48.1_1613_iks`, `0.47.0_1614_iks`, and `0.43.0_1612_iks`.



### 1 September 2021
{: #containers-sep121}
{: release-note}

Review the release notes for 1 September 2021.
{: shortdesc}

{{site.data.keyword.block_storage_is_short}} add-on
:   Version [`4.0`](/docs/containers?topic=containers-vpc_bs_changelog) is available.

{{site.data.keyword.cos_full_notm}} plug-in 
:   Version [`2.1.4`](/docs/containers?topic=containers-cos_plugin_changelog) is available.


## August 2021
{: #containers-aug21}

Review the release notes for August 2021.
{: shortdesc}

### 31 August 2021
{: #containers-aug3121}
{: release-note}

Review the release notes for 31 August 2021.
{: shortdesc}

Istio add-on change log
:   [Version 1.11.1](/docs/containers?topic=containers-istio-changelog#1111) of the Istio managed add-on is released.

New! Sao Paulo multizone region
:   You can now create VPC clusters in the Sao Paulo, Brazil [location](/docs/containers?topic=containers-regions-and-zones).

 VPC disk encryption on worker nodes
:   Now, you can manage the encryption for the disk on your VPC worker nodes. For more information, see [VPC worker nodes](/docs/containers?topic=containers-encryption-vpc-worker-disks).

### 30 August 2021
{: #containers-aug3021}
{: release-note}

Review the release notes for 30 August 2021.
{: shortdesc}



Worker node fix pack update
:   Change log documentation is available for version [`1.17.17_1568`](/docs/containers?topic=containers-117_changelog#11717_1568), [`1.18.20_1563`](/docs/containers?topic=containers-118_changelog#11820_1563), [`1.19.14_1558`](/docs/containers?topic=containers-changelog_119#11914_1558), [`1.20.10_1551`](/docs/containers?topic=containers-changelog_120#12010_1551), and [`1.21.4_1529`](/docs/containers?topic=containers-changelog_121#12104_1529).



### 25 August 2021
{: #containers-aug2621}
{: release-note}

New! Create a cluster with a template
:   No longer do you have to manually specify the networking and worker node details to create a cluster, or enable security integrations such as logging and monitoring after creation. Instead, you can try out the **technical preview** to create a multizone cluster with nine worker nodes and encryption, logging, and monitoring already enabled.

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.3` is [released](/docs/containers?topic=containers-cos_plugin_changelog).
Master fix pack update change log documentation

:   Master fix pack update change log documentation is available for version [1.21.4_ 1528](/docs/containers?topic=containers-changelog_121#1214_1528), [1.20.10_1550](/docs/containers?topic=containers-changelog_120#12010_1550), [1.19.14_1557](/docs/containers?topic=containers-changelog_119#11914_1557), and [1.18.20_1562](/docs/containers?topic=containers-118_changelog#11820_1562).

### 23 August 2021
{: #containers-aug2321}
{: release-note}

Registry token update
:   Registry tokens are no longer accepted for authentication in {{site.data.keyword.registrylong_notm}}. Update your clusters to use {{site.data.keyword.cloud_notm}} IAM authentication. For more information, see [Accessing {{site.data.keyword.registrylong_notm}}](/docs/Registry?topic=Registry-registry_access). For more information about Registry token deprecation, see [IBM Cloud Container Registry Deprecates Registry Tokens for Authentication](https://www.ibm.com/blog/announcement/ibm-cloud-container-registry-deprecates-registry-tokens-for-authentication/){: external}.

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions `0.48.1_1541_iks`, `0.47.0_1540_iks`, and `0.43.0_1539_iks`. Version `0.45.0_1482_iks` is removed.


  
ALB OAuth Proxy
:   Updated the version change log for the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog).



### 16 August 2021
{: #containers-aug1621}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available. For more information, see Version change log.


  
### 12 August 2021
{: #containers-aug1221}
{: release-note}

Istio add-on change log
:   [Version 1.9.7](/docs/containers?topic=containers-istio-changelog#196) of the Istio managed add-on is released.



### 10 August 2021
{: #containers-aug1021}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions `0.48.1_1465_iks`, `0.47.0_1480_iks`, and `0.45.0_1482_iks`.



ALB OAuth Proxy
:   Updated the version change log for the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog).

 

### 9 August 2021
{: #containers-aug0921}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.312](/docs/containers?topic=containers-cs_cli_changelog).

### 2 August 2021
{: #containers-aug0221}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions `0.47.0_1434_iks` and `0.45.0_1435_iks`. Version `0.35.0` is now unsupported. 

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.21.3_1526](/docs/containers?topic=containers-changelog_121#1213_1526), [1.20.9_1548](/docs/containers?topic=containers-changelog_120#1209_1548), [1.19.13_1555](/docs/containers?topic=containers-changelog_119#11913_1555), and [1.18.20_1560](/docs/containers?topic=containers-118_changelog#11820_1560).

## July 2021
{: #containers-jul21} 

### 27 July 2021
{: #containers-july2721}
{: release-note}

New! IAM trusted profile support
:   Link your cluster to a trusted profile in IAM so that the pods in your cluster can authenticate with IAM to use other {{site.data.keyword.cloud_notm}} services.

Master versions
:   Master fix pack update change log documentation is available for version [1.21.3_1525](/docs/containers?topic=containers-changelog_121#1213_1525), [1.20.9_1547](/docs/containers?topic=containers-changelog_120#1209_1547), [1.19.13_1554](/docs/containers?topic=containers-changelog_119#11913_1554), and [1.18.20_1559](/docs/containers?topic=containers-118_changelog#11820_1559).

### 22 July 2021
{: #containers-july2221}
{: release-note}

Istio add-on change log
:   [Version 1.9.6](/docs/containers?topic=containers-istio-changelog#196) of the Istio managed add-on is released.



### 19 July 2021
{: #containers-july1921}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.21.2_1524](/docs/containers?topic=containers-changelog_121#1212_1524), [1.20.8_1546](/docs/containers?topic=containers-changelog_120#1208_1546), [1.19.12_1553](/docs/containers?topic=containers-changelog_119#11912_1553), [1.18.29_1558](/docs/containers?topic=containers-118_changelog#11829_1558), and [1.17.17_1568](/docs/containers?topic=containers-117_changelog#11717_1568).

### 15 July 2021
{: #containers-july1521}
{: release-note}

Istio add-on change log
:   [Version 1.10.2](/docs/containers?topic=containers-istio-changelog#v110) of the Istio managed add-on is released. 



### 12 July 2021
{: #containers-july1221}
{: release-note}



Snapshots
:   Before updating to Kubernetes version `1.20` or `1.21`, snapshot CRDs must be changed to version `v1beta1`. For more information, see the [Kubernetes version information and update actions](/docs/containers?topic=containers-cs_versions_121#121_before).



### 6 July 2021
{: #containers-july0621}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions `0.47.0_1376_iks`, `0.45.0_1375_iks`, and `0.35.0_1374_iks`.

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.21.2_1523](/docs/containers?topic=containers-changelog_121#1212_1523), [1.20.8_1545](/docs/containers?topic=containers-changelog_120#1208_1545), [1.19.12_1552](/docs/containers?topic=containers-changelog_119#11912_1552), [1.18.20_1557](/docs/containers?topic=containers-118_changelog#11820_1557), and [1.17.17_1567](/docs/containers?topic=containers-117_changelog#11717_1567_worker).

### 2 July 2021
{: #containers-july0221}
{: release-note}

Unsupported Kubernetes version 1.17
:   To continue receiving important security updates and support, you must [update the cluster to a supported version](/docs/containers?topic=containers-cs_versions#prep-up) immediately.

## June 2021
{: #containers-jun21}

From 07 to 31 July 2021, the DNS provider is changed from Cloudflare to Akamai for all `containers.appdomain.cloud`, `containers.mybluemix.net`, and `containers.cloud.ibm.com` domains for all clusters in {{site.data.keyword.containerlong_notm}}. Review the following actions that you must make to your Ingress setup.
{: important}

- If you currently allow inbound traffic to your classic cluster from the Cloudflare source IP addresses, you must also allow inbound traffic from the [Akamai source IP addresses](https://github.com/IBM-Cloud/kube-samples/tree/master/akamai/gtm-liveness-test){: external} before 07 July. After the migration completes on 31 July, you can remove the Cloudflare IP address rules.

- The Akamai health check does not support verification of the body of the health check response. Update any custom health check rules that you configured for Cloudflare that use verification of the body of the health check responses.

- Cluster subdomains that were health checked in Cloudflare are now registered in the Akamai DNS as CNAME records. These CNAME records point to an Akamai Global Traffic Management domain that health checks the subdomains. When a client runs a DNS query for a health checked subdomain, a CNAME record is returned to the client, as opposed to Cloudflare, in which an A record was returned. If your client expects an A record for a subdomain that was health checked in Cloudflare, update your logic to accept a CNAME record.

- During the migration, an Akamai Global Traffic Management (GTM) health check was automatically created for any subdomains that had a Cloudflare health check. If you previously created a Cloudflare health check for a subdomain, and you create an Akamai health check for the subdomain after the migration, the two Akamai health checks might conflict. Note that Akamai GTM configurations don't support nested subdomains. In these cases, you can use the `ibmcloud ks nlb-dns monitor disable` command to disable the Akamai health check that the migration automatically configured for your subdomain.

### 28 June 2021
{: #containers-june2821}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available for version [1.21.2_1522](/docs/containers?topic=containers-changelog_121#1212_1522), [1.20.8_1544](/docs/containers?topic=containers-changelog_120#1208_1544), [1.19.12_1551](/docs/containers?topic=containers-changelog_119#11912_1551), [1.18.20_1556](/docs/containers?topic=containers-118_changelog#11820_1556), and [1.17.17_1567](/docs/containers?topic=containers-117_changelog#11717_1567).

### 24 June 2021
{: #containers-june2421}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.295](/docs/containers?topic=containers-cs_cli_changelog#10).

### 23 June 2021
{: #containers-june2321}
{: release-note}

Cluster autoscaler add-on
:   [Version `1.0.3`](/docs/containers?topic=containers-ca_changelog) of the cluster autoscaler add-on is available.

### 22 June 2021
{: #containers-june2221}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.1.2` of the {{site.data.keyword.cos_full_notm}} plug-in is released. Update your clusters to use the latest version. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.21.1_1521](/docs/containers?topic=containers-changelog_121#1211_1521), [1.20.7_1543](/docs/containers?topic=containers-changelog_120#1207_1543), [1.19.11_1550](/docs/containers?topic=containers-changelog_119#11911_1550), [1.18.19_1555](/docs/containers?topic=containers-118_changelog#11819_1555) and [1.17.17_1566](/docs/containers?topic=containers-117_changelog#11717_1566).

### 21 June 2021
{: #containers-june2121}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the release of version 0.47.0 of the Kubernetes Ingress image.

New! The `addon options` command is now available
:   For more information, see [`addon options`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_options).



### 17 June 2021
{: #containers-june1721}
{: release-note}



ALB OAuth Proxy
:   Updated the version change log for the [ALB OAuth Proxy](/docs/containers?topic=containers-alb-oauth-proxy-changelog) add-on.



### 15 June 2021
{: #containers-june1521}
{: release-note}

New! Private VPC NLB
:   You can now create [private Network Load Balancers for VPC](/docs/containers?topic=containers-vpc-lbaas#setup_vpc_nlb_priv) to expose apps in clusters that run version 1.19 and later.

### 10 June 2021
{: #containers-june1021}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for versions 0.45.0, 0.35.0, and 0.34.1 of the Kubernetes Ingress image.



### 9 June 2021
{: #containers-june0921}
{: release-note}



New! Kubernetes 1.21
:   You can create or (/docs/containers?topic=containers-cs_versions_121)update your cluster to Kubernetes version 1.21. With Kubernetes 1.21, you get the latest stable enhancements from the community, such as stable `CronJob`, `EndpointSlice`, and `PodDisruptionBudget` resources. You also get enhancements to the {{site.data.keyword.cloud_notm}} product, such as a refreshed user interface experience. For more information, see the [blog announcement](https://www.ibm.com/blog/announcement/kubernetes-version-121-now-available-in-ibm-cloud-kubernetes-service/){: external}.

Deprecated Kubernetes 1.18
:   With the release of Kubernetes 1.21, clusters that run version 1.18 are deprecated, with a tentative unsupported date of 10 October 2021. Update your cluster to at least [version 1.19](/docs/containers?topic=containers-cs_versions_119) as soon as possible.



Expanded Troubleshooting
:   You can now find troubleshooting steps for {{site.data.keyword.cloud_notm}} persistent storage in the following pages.  
    - [{{site.data.keyword.filestorage_short}}](/docs/containers?topic=containers-debug_storage_file)
    - [{{site.data.keyword.blockstorageshort}}](/docs/containers?topic=containers-debug_storage_block)
    - [{{site.data.keyword.cos_short}}](/docs/containers?topic=containers-debug_storage_cos)
    - [Portworx](/docs/containers?topic=containers-debug_storage_px)

### 07 June 2021
{: #containers-june0721}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.7_1542](/docs/containers?topic=containers-changelog_120#1207_1542), [1.19.11_1549](/docs/containers?topic=containers-changelog_119#11911_1549), [1.18.19_1554](/docs/containers?topic=containers-118_changelog#11819_1554), and [1.17.17_1565](/docs/containers?topic=containers-117_changelog#11717_1565).

### 3 June 2021
{: #containers-june0321}
{: release-note}

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.0.8` of the {{site.data.keyword.cos_full_notm}} plug-in is released. Update your clusters to use the latest version. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 2 June 2021
{: #containers-june0221}
{: release-note}



End of support for custom IBM Ingress image
:   The custom {{site.data.keyword.containerlong_notm}} Ingress image is unsupported. In clusters that were created before 01 December 2020, migrate any ALBs that continue to run the custom IBM Ingress image to the Kubernetes Ingress image. Not ready to switch your ALBs to the Kubernetes Ingress image yet? The custom {{site.data.keyword.containerlong_notm}} Ingress image is available as an [open source project](https://github.com/IBM-Cloud/iks-ingress-controller/){: external}. However, this project is not officially supported by {{site.data.keyword.cloud_notm}}, and you are responsible for deploying, managing, and maintaining the Ingress controllers in your cluster.



## May 2021
{: #containers-may21}




  
### 27 May 2021
{: #containers-may2721}
{: release-note}

Istio add-on change log
:   [Version 1.9.5](/docs/containers?topic=containers-istio-changelog#v19) and version [1.8.6](/docs/containers?topic=containers-istio-changelog#v18) of the Istio managed add-on are released.



### 26 May 2021
{: #containers-may2621}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.275](/docs/containers?topic=containers-cs_cli_changelog#10).

Version 0.45.0 of the Kubernetes Ingress image
:   Due to a [regression in the community Kubernetes Ingress NGINX code](https://github.com/kubernetes/ingress-nginx/issues/6931){: external}, trailing slashes (`/`) are removed from subdomains during TLS redirects.

### 24 May 2021
{: #containers-may2421}
{: release-note}



Master versions
:   Master fix pack update change log documentation is available for version [1.20.7_1540](/docs/containers?topic=containers-changelog_120#1207_1540), [1.19.11_1547](/docs/containers?topic=containers-changelog_119#11911_1547), [1.18.19_1552](/docs/containers?topic=containers-118_changelog#11819_1552), and [1.17.17_1563](/docs/containers?topic=containers-117_changelog#11717_1563).

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.7_1541](/docs/containers?topic=containers-changelog_120#1207_1541), [1.19.11_1548](/docs/containers?topic=containers-changelog_119#11911_1548), [1.18.19_1553](/docs/containers?topic=containers-118_changelog#11819_1553), and [1.17.17_1564](/docs/containers?topic=containers-117_changelog#11717_1564).

### 17 May 2021
{: #containers-may1721}
{: release-note}

Deprecated: Kubernetes web terminal.
:   The Kubernetes web terminal add-on is deprecated and becomes unsupported 1 July 2021. Instead, use the [{{site.data.keyword.cloud-shell_notm}}](/docs/cloud-shell?topic=cloud-shell-shell-ui).



Istio add-on
:   [Version 1.9.4 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#v19) is released.

Deprecated Ubuntu 16 end of support date
:   The Ubuntu 16 worker node flavors were deprecated 1 December 2020, with an initial unsupported date of April 2021. To give customers more time to migrate to a newer Ubuntu version, the end of support date is extended to 31 December 2021. Before 31 December 2021, [update the worker pools in your cluster to run Ubuntu 18](/docs/containers?topic=containers-update#machine_type). For more information, see the [{{site.data.keyword.cloud_notm}} blog](https://www.ibm.com/blog/announcement/new-bare-metal-servers-available-for-kubernetes-and-openshift-clusters/){: external}.

### 11 May 2021
{: #containers-may1121}
{: release-note}

VPC cluster healthchecks
:   If you set up [VPC security groups](/docs/containers?topic=containers-vpc-security-group) or [VPC access control lists (ACLs)](/docs/containers?topic=containers-vpc-acls) to secure your cluster network, you can now create the rules to allow the necessary traffic from the control plane IP addresses and Akamai IPv4 IP addresses to health check your ALBs. Previously, a quota on the number of rules per security group or ACL prevented the ability to create all necessary rules for health checks.

### 10 May 2021
{: #containers-may1021}
{: release-note}

New! Portworx Backup is now available
:   For more information, see [Backing up and restoring apps and data with Portworx Backup](/docs/containers?topic=containers-storage_portworx_backup).



Calico KDD update in 1.19
:   Added a step to check for Calico `NetworkPolicy` resources that are scoped to non-existent namespaces before [updating your cluster to Kubernetes version 1.19](/docs/containers?topic=containers-cs_versions_119#119_before).



Cluster autoscaler add-on
:   [Patch update `1.0.2_267`](/docs/containers?topic=containers-ca_changelog) of the cluster autoscaler add-on is available.

{{site.data.keyword.cos_full_notm}} plug-in
:   [Version `2.0.9`](/docs/containers?topic=containers-cos_plugin_changelog) of the {{site.data.keyword.cos_full_notm}} plug-in is available.

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.6_1539](/docs/containers?topic=containers-changelog_120#1206_1539), [1.19.10_1546](/docs/containers?topic=containers-changelog_119#11910_1546), [1.18.18_1551](/docs/containers?topic=containers-118_changelog#11818_1551), and [1.17.17_1562](/docs/containers?topic=containers-117_changelog#11717_1562).

### 4 May 2021
{: #containers-may0421}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available for version [1.20.5_1538](/docs/containers?topic=containers-changelog_120#1206_1538) and [1.19.10_1545](/docs/containers?topic=containers-changelog_119#11910_1545).

## April 2021
{: #containers-apr21}



### 29 April 2021
{: #containers-april2921}
{: release-note}

Custom IOPs for Istio
:   Added a page for creating a custom Istio ingress and egress gateways for the managed Istio add-on by [using `IstioOperator`](/docs/containers?topic=containers-istio-custom-gateway).

Istio add-on change log
:   [Version 1.9.3](/docs/containers?topic=containers-istio-changelog#v19) and version [1.8.5](/docs/containers?topic=containers-istio-changelog#v18) of the Istio managed add-on are released.



### 28 April 2021
{: #containers-april2821}
{: release-note}

Default version
:   The default version for new clusters is now 1.20.

### 27 April 2021
{: #containers-april2721}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available for version [1.20.6_1536](/docs/containers?topic=containers-changelog_120#1206_1536), [1.19.10_1543](/docs/containers?topic=containers-changelog_119#11910_1543), [1.18.18_1549](/docs/containers?topic=containers-118_changelog#11818_1549), and [1.17.17_1560](/docs/containers?topic=containers-117_changelog#11717_1560).

### 26 April 2021
{: #containers-april2621}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.258](/docs/containers?topic=containers-cs_cli_changelog#10).



VPC NLB
:   Adds steps for [registering a VPC network load balancer with a DNS record and TLS certificate](/docs/containers?topic=containers-vpc-lbaas#vpc_nlb_dns).

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.6_1537](/docs/containers?topic=containers-changelog_120#1206_1537), [1.19.10_1544](/docs/containers?topic=containers-changelog_119#11910_1544), [1.18.18_1550](/docs/containers?topic=containers-118_changelog#11818_1550), and [1.17.17_1561](/docs/containers?topic=containers-117_changelog#11717_1561).


  
### 23 April 2021
{: #containers-april2321}
{: release-note}

Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the release of version 0.45.0 of the Kubernetes Ingress image. Version 0.33.0 is now unsupported.



### 20 April 2021
{: #containers-april2021}
{: release-note}

New! Toronto multizone region for VPC
:   You can now create clusters on VPC infrastructure in the Toronto, Canada (`ca-tor`) [location](/docs/containers?topic=containers-regions-and-zones).

### 19 April 2021
{: #containers-april1921}
{: release-note}

add-on change logs
:   Updated version change logs for the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog).

Cluster autoscaler add-on
:   [Patch update `1.0.2_256`](/docs/containers?topic=containers-ca_changelog) of the cluster autoscaler add-on is available.

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.0.8` of the {{site.data.keyword.cos_full_notm}} plug-in is released. Update your clusters to use the latest version. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).


  
Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for updates to the Kubernetes Ingress and {{site.data.keyword.containerlong_notm}} Ingress images.



### 16 April 2021
{: #containers-april1621}
{: release-note}

New fields and events for {{site.data.keyword.at_short}}
:   To align with event auditing standards across {{site.data.keyword.cloud_notm}}, the previously deprecated cluster fields and events are now replaced by new fields and events. For an updated list of events, see [{{site.data.keyword.at_full_notm}} events](/docs/containers?topic=containers-at_events).

### 15 April 2021
{: #containers-april1521}
{: release-note}



Accessing VPC clusters
:   Updated the steps for [accessing VPC clusters through the private cloud service endpoint](/docs/containers?topic=containers-access_cluster#vpc_private_se) by configuring the VPC VPN gateway to access the `166.8.0.0/14` subnet.



### 12 April 2021
{: #containers-april1221}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.5_1535](/docs/containers?topic=containers-changelog_120#1205_1535), [1.19.9_1542](/docs/containers?topic=containers-changelog_119#1199_1542), [1.18.17_1548](/docs/containers?topic=containers-118_changelog#11817_1548), and [1.17.17_1559](/docs/containers?topic=containers-117_changelog#11717_1559).



Ingress change logs
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for updates to the Kubernetes Ingress and {{site.data.keyword.containerlong_notm}} Ingress images.



### 5 April 2021
{: #containers-april0521}
{: release-note}

Deprecated data centers for classic clusters
:   Houston (`hou02`) and Oslo (`osl01`) are deprecated and become unsupported later this year. To prevent any interruption of service, [redeploy all your cluster workloads](/docs/containers?topic=containers-update_app#copy_apps_cluster) to a [supported data center](/docs/containers?topic=containers-regions-and-zones#zones-mz) and remove your `osl01` or `hou02` clusters by **1 August 2021**. Before the unsupported date, you are blocked from adding new worker nodes and clusters starting on **1 July 2021**. For more information, see [Data center closures in 2021](/docs/get-support?topic=get-support-dc-closure).

### 2 April 2021
{: #containers-april0221}
{: release-note}



Istio add-on
:   [Version 1.9.2 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#v19) is released.



### 1 April 2021
{: #containers-april0121}
{: release-note}

Cluster autoscaler add-on
:   [Patch update `1.0.2_249`](/docs/containers?topic=containers-ca_changelog) of the cluster autoscaler add-on is available.

{{site.data.keyword.block_storage_is_short}} add-on
:   [Patch update `3.0.0_521`](/docs/containers?topic=containers-vpc_bs_changelog) of the {{site.data.keyword.block_storage_is_short}} add-on is available.

{{site.data.keyword.block_storage_is_short}} driver
:   Added steps to install the `vpc-block-csi-driver` on unmanaged clusters. For more information, see [Setting up {{site.data.keyword.block_storage_is_short}} for unmanaged clusters](/docs/containers?topic=containers-vpc-block-storage-driver-unmanaged).

New! image security add-on
:   In clusters that run version 1.18 or later, you can (/docs/containers?topic=containers-images#portieris-image-sec)install the container image security enforcement add-onto set up the (https://github.com/IBM/portieris){: external} Portieris project in your cluster.


## March 2021
{: #containers-mar21}



### 30 March 2021
{: #containers-march3021}
{: release-note}

add-on change logs
:   Added version change logs for the [ALB OAuth Proxy add-on](/docs/containers?topic=containers-alb-oauth-proxy-changelog).

Master versions
:   Master fix pack update change log documentation is available for version [1.20.5_1533](/docs/containers?topic=containers-changelog_120#1205_1533), [1.19.9_1540](/docs/containers?topic=containers-changelog_119#1199_1540), [1.18.17_1546](/docs/containers?topic=containers-118_changelog#11817_1546), and [1.17.17_1557](/docs/containers?topic=containers-117_changelog#11717_1557).

### 29 March 2021
{: #containers-march2921}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.5_1534](/docs/containers?topic=containers-changelog_120#1205_1534), [1.19.9_1541](/docs/containers?topic=containers-changelog_119#1199_1541), [1.18.17_1547](/docs/containers?topic=containers-118_changelog#11817_1547), and [1.17.17_1558](/docs/containers?topic=containers-117_changelog#11717_1558).

### 25 March 2021
{: #containers-march2521}
{: release-note}

 

{{site.data.keyword.cloudcerts_short}} instances
:   The default {{site.data.keyword.cloudcerts_short}} instance for your cluster is now named in the format `kube-crtmgr-<cluster_ID>`.


  
### 23 March 2021
{: #containers-march2321}
{: release-note}

Istio add-on
:   [Version 1.8.4 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#184) is released.



### 22 March 2021
{: #containers-march2221}
{: release-note}



Ingress ALB change log
:   Updated the [Ingress ALB change log](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for updates to the Kubernetes Ingress and {{site.data.keyword.containerlong_notm}} Ingress images.





### 17 March 2021
{: #containers-mar1721}
{: release-note}

Deprecated events to be replaced for {{site.data.keyword.at_short}}
:   To align with event auditing standards across {{site.data.keyword.cloud_notm}}, the following cluster events are deprecated and are replaced in 30 days on 16 April 2021 by new events.
    - `containers-kubernetes.account.create` 
    - `containers-kubernetes.account.delete` 
    - `containers-kubernetes.account.get` 
    - `containers-kubernetes.account.update` 
    - `containers-kubernetes.cluster.config` 
    - `containers-kubernetes.cluster.create` 
    - `containers-kubernetes.cluster.delete` 
    - `containers-kubernetes.cluster.update` 
    - `containers-kubernetes.credentials.ready-to-use` 
    - `containers-kubernetes.logging-config.create` 
    - `containers-kubernetes.logging-config.delete` 
    - `containers-kubernetes.logging-config.refresh` 
    - `containers-kubernetes.logging-filter.create` 
    - `containers-kubernetes.logging-filter.delete` 
    - `containers-kubernetes.logging-filter.update` 
    - `containers-kubernetes.logging-autoupdate.changed` 
    - `containers-kubernetes.masterlog-retrieve` 
    - `containers-kubernetes.masterlog-status` 
    - `containers-kubnertes.cluster.rbac.update` 
    - `containers-kubernetes.service.create` 
    - `containers-kubernetes.service.delete` 
    - `containers-kubernetes.subnet.add` 
    - `containers-kubernetes.subnet.create` 
    - `containers-kubernetes.subnet.update` 
    - `containers-kubernetes.vlan.create` 
    - `containers-kubernetes.vlan.delete` 
    - `containers-kubernetes.worker.create` 
    - `containers-kubernetes.worker.delete` 
    - `containers-kubernetes.worker.update` 
    - `containers-kubernetes.workerpool.create` 
    - `containers-kubernetes.workerpool.delete` 
    - `containers-kubernetes.workerpool.update` 
    - `containers-kubernetes.zone.delete` 
    - `containers-kubernetes.zone.update`
    
Deprecated fields across events
:   The following fields are deprecated and replaced by or updated with new values across events. 
    - The `correlationID` is replaced by `correlationId` to align with field casing standards. 
    - The `resourceGroupID` field is no longer used. Instead, the resource group ID can be found in the `target.resourceGroupId` field. 
    - The `reason.reasonCode` field is now formatted as an integer (`int`) instead of string (`string`). 
    - The `requestData` field is now formatted as a JSON object instead of a JSON string. 
    - The `responseData` field is now formatted as a JSON object instead of string. 
    - The `target.typeURI` values are updated for consistency. All values now have a prefix of `containers-kubernetes/` instead of `container/`. For example, `container/cluster` is now `containers-kubernetes/cluster` and `container/worker` is now `containers-kubernetes/worker`.

### 16 March 2021
{: #containers-march1621}
{: release-note}

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 2458](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

### 12 March 2021
{: #containers-march1221}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.4_1532](/docs/containers?topic=containers-changelog_120#1204_1532), [1.19.8_1539](/docs/containers?topic=containers-changelog_119#1198_1539), [1.18.16_1545](/docs/containers?topic=containers-118_changelog#11816_1545), and [1.17.17_1556](/docs/containers?topic=containers-117_changelog#11717_1556).



### 10 March 2021
{: #containers-march1021}
{: release-note}

Istio add-on
:   [Version 1.7.8 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#178) is released.



### 9 March 2021
{: #containers-march0921}
{: release-note}

Cluster autoscaler add-on
:   Version 1.0.2 of the cluster autoscaler add-on is released. For more information, see the [cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).



### 5 March 2021
{: #containers-march0521}
{: release-note}

Trusted images
:   You can now [set up trusted content for container images](/docs/containers?topic=containers-images#trusted_images) that are signed and stored in {{site.data.keyword.registrylong_notm}}.

### 1 March 2021
{: #containers-march0121}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.233](/docs/containers?topic=containers-cs_cli_changelog#10).



Istio add-on
:   [Version 1.8.3 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#183) is released.



Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.20.4_1531](/docs/containers?topic=containers-changelog_120#1204_1531), [1.19.8_1538](/docs/containers?topic=containers-changelog_119#1198_1538), [1.18.16_1544](/docs/containers?topic=containers-118_changelog#11816_1544), and [1.17.17_1555](/docs/containers?topic=containers-117_changelog#11717_1555_worker).

## February 2021
{: #containers-feb21}

### 27 February 2021
{: #containers-feb2721}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available for version [1.20.4_1531](/docs/containers?topic=containers-changelog_120#1204_1531_master), [1.19.8_1538](/docs/containers?topic=containers-changelog_119#1198_1538_master), and [1.18.16_1544](/docs/containers?topic=containers-118_changelog#11816_1544_master).

### 26 February 2021
{: #containers-feb2621}
{: release-note}

{{site.data.keyword.block_storage_is_short}} add-on
:   Version `3.0.0` of the {{site.data.keyword.block_storage_is_short}} add-on is released. Update your clusters to use the latest version. For more information, see the [{{site.data.keyword.block_storage_is_short}} add-on change log](/docs/containers?topic=containers-vpc_bs_changelog).



End of service of VPC Gen 1
:   Removed steps for using VPC Gen 1 compute. You can now [create new VPC clusters on Generation 2 compute only](/docs/containers?topic=containers-cluster-create-vpc-gen2&interface=ui). Move any remaining workloads from VPC Gen 1 clusters to VPC Gen 2 clusters before 01 March 2021, when any remaining VPC Gen 1 worker nodes are automatically deleted.



### 25 February 2021
{: #containers-feb2521}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.231](/docs/containers?topic=containers-cs_cli_changelog#10).


  
### 24 February 2021
{: #containers-feb2421}
{: release-note}

Default version
:   Kubernetes 1.19 is now the default cluster version.



### 23 February 2021
{: #containers-feb2321}
{: release-note}

VPE
:   Worker node communication to the Kubernetes master is now established over the [VPC virtual private endpoint (VPE)](/docs/containers?topic=containers-vpc-subnets#vpc_basics_vpe).

### 22 February 2021
{: #containers-feb2221}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available for version [1.20.4_1530](/docs/containers?topic=containers-changelog_120#1204_1530), [1.19.8_1537](/docs/containers?topic=containers-changelog_119#1198_1537), [1.18.16_1543](/docs/containers?topic=containers-118_changelog#11816_1543), and [1.17.17_1555](/docs/containers?topic=containers-117_changelog#11717_1555).

### 20 February 2021
{: #containers-feb2021}
{: release-note}

Certified Kubernetes
:   Version [1.20](/docs/containers?topic=containers-cs_versions_120) release is now certified.

### 17 February 2021
{: #containers-feb1721}
{: release-note}



New! Kubernetes 1.20
:   You can create or [update](/docs/containers?topic=containers-cs_versions_120) your cluster to Kubernetes version 1.20. With Kubernetes 1.20, you get the latest stable enhancements from the community, as well as beta access to features such as [API server priority](/docs/containers?topic=containers-kubeapi-priority). For more information, see the [blog announcement](https://www.ibm.com/blog/announcement/kubernetes-version-120-now-available-in-ibm-cloud-kubernetes-service){: external}.

Deprecated Kubernetes 1.17
:   With the release of Kubernetes 1.20, clusters that run version 1.17 are deprecated, with a tentative unsupported date of 2 July 2021. Update your cluster to at least [version 1.18](/docs/containers?topic=containers-cs_versions#k8s_version_archive) as soon as possible.



### 15 February 2021
{: #containers-feb1521}
{: release-note}

New! Osaka multizone region
:   You can now create classic or VPC clusters in the Osaka, Japan (`jp-osa`) [location](/docs/containers?topic=containers-regions-and-zones).

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.19.7_1535](/docs/containers?topic=containers-changelog_119#1197_1535), [1.18.15_1541](/docs/containers?topic=containers-118_changelog#11815_1541), and [1.17.17_1553](/docs/containers?topic=containers-117_changelog#11717_1553).

### 12 February 2021
{: #containers-feb1221}
{: release-note}

Gateway firewalls and Calico policies
:   For classic clusters in Frankfurt, updated the required IP addresses and ports that you must open in a [private gateway device firewall](/docs/containers?topic=containers-firewall#firewall_private) or [Calico private network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies/private-network-isolation/eu-de){: external}.

### 10 February 2021
{: #containers-feb1021}
{: release-note}

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 2452](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

Gateway firewalls and Calico policies
:   For classic clusters in Dallas, Washington D.C., and Frankfurt, updated the required IP addresses and ports that you must open in a [public gateway firewall device](/docs/containers?topic=containers-firewall#firewall_outbound), [private gateway device firewall](/docs/containers?topic=containers-firewall#firewall_private), or [Calico network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies){: external}.

### 8 February 2021
{: #containers-feb0821}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.223](/docs/containers?topic=containers-cs_cli_changelog#10).



Istio add-on
:   [Version 1.7.7 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#177) is released.



### 4 February 2021
{: #containers-feb0421}
{: release-note}

Worker node modifications
:   Summarized the modifications that you can make to the [default worker node settings](/docs/containers?topic=containers-kernel#worker-default).



### 3 February 2021
{: #containers-feb0321}
{: release-note}

Worker node versions
:   A worker node fix pack for internal documentation updates is available for version [1.19.7_1534](/docs/containers?topic=containers-changelog_119#1197_1534), and [1.18.15_1540](/docs/containers?topic=containers-118_changelog#11815_1540).



### 1 February 2021
{: #containers-feb0121}
{: release-note}

Unsupported: Kubernetes version 1.16
:   Clusters that run Kubernetes version 1.16 are unsupported as of 31 January 2021. To continue receiving important security updates and support, you must [update the cluster to a supported version](/docs/containers?topic=containers-cs_versions#prep-up) immediately.

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.19.7_1533](/docs/containers?topic=containers-changelog_119#1197_1533), [1.18.15_1539](/docs/containers?topic=containers-118_changelog#11815_1539), and [1.17.17_1552](/docs/containers?topic=containers-117_changelog#11717_1552).

## January 2021
{: #containers-jan21}

### 27 January 2021
{: #containers-jan2721}
{: release-note}

Block Storage for VPC add-on
:   Block Storage for VPC add-on patch update `2.0.3_471` is released. For more information, see the [Block Storage for VPC add-on change log](/docs/containers?topic=containers-vpc_bs_changelog).



Reminder: VPC Gen 1 deprecation
:   You can continue to use VPC Gen 1 resources only until 26 February 2021, when all service for VPC Gen 1 ends. On 01 March 2021, any remaining VPC Gen 1 worker nodes are automatically deleted. To ensure continued support, [create new VPC clusters on Generation 2 compute only](/docs/containers?topic=containers-cluster-create-vpc-gen2&interface=ui), and move your workloads from existing VPC Gen 1 clusters to VPC Gen 2 clusters.



### 25 January 2021
{: #containers-jan2521}
{: release-note}



Istio add-on
:   [Version 1.8.2 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#182) is released.

New! Private service endpoint allowlists
:   You can now control access to your private cloud service endpoint by [creating a subnet allowlist](/docs/containers?topic=containers-access_cluster#private-se-allowlist). Only authorized requests to your cluster master that originate from subnets in the allowlist are permitted through the cluster's private cloud service endpoint.

Private Kubernetes Ingress
:   Added steps for privately exposing apps with ALBs that run the Kubernetes Ingress image.

### 19 January 2021
{: #containers-jan1921}
{: release-note}

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 2424](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

Master versions
:   Master fix pack update change log documentation is available for version [1.19.7_1532](/docs/containers?topic=containers-changelog_119#1197_1532_master), [1.18.15_1538](/docs/containers?topic=containers-118_changelog#11815_1538_master), [1.17.17_1551](/docs/containers?topic=containers-117_changelog#11717_1551_master), and [1.16.15_1557](/docs/containers?topic=containers-116_changelog#11615_1557_master).

### 18 January 2021
{: #containers-jan1821}
{: release-note}

Knative add-on is unsupported
:   The Knative add-on is automatically removed from your cluster. Instead, use the [Knative open source project](https://knative.dev/docs/install/){: external} or [{{site.data.keyword.codeenginefull}}](/docs/codeengine?topic=codeengine-getting-started), which includes Knative's open-source capabilities.

Worker node versions
:   Worker node fix pack update change log documentation is available for version [1.19.7_1532](/docs/containers?topic=containers-changelog_119#1197_1532), [1.18.15_1538](/docs/containers?topic=containers-118_changelog#11815_1538), [1.17.17_1551](/docs/containers?topic=containers-117_changelog#11717_1551), and [1.16.15_1557](/docs/containers?topic=containers-116_changelog#11615_1557).

### 14 January 2021
{: #containers-jan1421}
{: release-note}

Cluster autoscaler
:   Cluster autoscaler add-on patch update `1.0.1_210` is released. For more information, see the [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 12 January 2021
{: #containers-jan1221}
{: release-note}

Ingress resources
:   Added example Ingress resource definitions that are compatible with Kubernetes version 1.19. 

Kubernetes benchmarks
:   Added how to [run the CIS Kubernetes benchmark tests on your own worker nodes](/docs/containers?topic=containers-cis-benchmark#cis-worker-test). 

Removal of data center support
:   Updated the documentation to reflect that Melbourne (`mel01`) is no longer available as an option to create {{site.data.keyword.cloud_notm}} resources in.


  
### 7 January 2021
{: #containers-jan0721}
{: release-note}

Ingress ALB change log
:   Updated the latest [Kubernetes Ingress image build to `0.35.0_869_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_35_0).



### 6 January 2021
{: #containers-jan0621}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available.
:   [1.19.6_1531](/docs/containers?topic=containers-changelog_119#1196_1531), [1.18.14_1537](/docs/containers?topic=containers-118_changelog#11814_1537), [1.17.16_1550](/docs/containers?topic=containers-117_changelog#11716_1550), and [1.16.15_1556](/docs/containers?topic=containers-116_changelog#11615_1556).

## December 2020
{: #containers-dec20}

### 21 December 2020
{: #containers-dec2120}
{: release-note}

Gateway firewalls and Calico policies
:   For classic clusters in Tokyo, updated the {{site.data.keyword.containerlong_notm}} IP addresses that you must open in a [public gateway firewall device](/docs/containers?topic=containers-firewall#firewall_outbound) or [Calico network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies/public-network-isolation){: external}.

Worker node versions
:   Worker node fix pack update change log documentation is available.
:   [1.19.5_1530](/docs/containers?topic=containers-changelog_119#1195_1530), [1.18.13_1536](/docs/containers?topic=containers-118_changelog#11813_1536), [1.17.15_1549](/docs/containers?topic=containers-117_changelog#11715_1549), and [1.16.15_1555](/docs/containers?topic=containers-116_changelog#11615_1555).

### 18 December 2020
{: #containers-dec1820}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.208](/docs/containers?topic=containers-cs_cli_changelog#10).

{{site.data.keyword.cos_full_notm}} plug-in
:   Version `2.0.6` of the {{site.data.keyword.cos_full_notm}} plug-in is released. For more information, see the [{{site.data.keyword.cos_full_notm}} plug-in change log](/docs/containers?topic=containers-cos_plugin_changelog).

### 17 December 2020
{: #containers-dec1720}
{: release-note}

Audit documentation
:   Reorganized information about the configuration and forwarding of Kubernetes API server [audit logs](/docs/containers?topic=containers-health-audit).

Back up and restore
:   Version `1.0.5` of the `ibmcloud-backup-restore` Helm chart is released. For more information, see the [Back up and restore Helm chart change log](/docs/containers?topic=containers-backup_restore_changelog).



Ingress ALB change log
:   Updated the latest [Kubernetes Ingress image build to `0.35.0_826_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_35_0).
:   Updated the [`ingress-auth` build to 954](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

  
### 16 December 2020
{: #containers-dec1620}
{: release-note}

Istio add-on
:   Versions [1.8.1](/docs/containers?topic=containers-istio-changelog#181) and [1.7.6](/docs/containers?topic=containers-istio-changelog#176) of the Istio managed add-on are released. Version 1.6 is unsupported.

### 15 December 2020
{: #containers-dec1520}
{: release-note}

Cluster autoscaler
:   Cluster autoscaler add-on patch update `1.0.1_205` is released. For more information, see the [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).

### 14 December 2020
{: #containers-dec1420}
{: release-note}



Ingress ALB change log
:   Updated the latest [Kubernetes Ingress image build to `0.35.0_767_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_35_0).
:   Updated the [`nginx-ingress` build to 2410 and the `ingress-auth` build to 947](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

Master versions
:   Master fix pack update change log documentation is available.
:   [1.19.5_1529](/docs/containers?topic=containers-changelog_119#1195_1529), [1.18.13_1535](/docs/containers?topic=containers-118_changelog#11813_1535), [1.17.15_1548](/docs/containers?topic=containers-117_changelog#11715_1548), and [1.16.15_1554](/docs/containers?topic=containers-116_changelog#11615_1554_master).

### 11 December 2020
{: #containers-dec1120}
{: release-note}

Storage add-ons
:   Cluster autoscaler add-on patch update `1.0.1_195` is released. For more information, see the [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog). {{site.data.keyword.block_storage_is_short}} add-on patch update `2.0.3_464` is released. For more information, see the [{{site.data.keyword.block_storage_is_short}} add-on change log](/docs/containers?topic=containers-vpc_bs_changelog).

strongSwan versions
:   Added information about which [strongSwan Helm chart versions](/docs/containers?topic=containers-116_changelog#11615_1554) are supported.



Worker node versions
:   Worker node fix pack update change log documentation is available for Kubernetes version [1.19.4_1529](/docs/containers?topic=containers-changelog_119#1194_1529), [1.18.12_1535](/docs/containers?topic=containers-118_changelog#11812_1535), [1.17.14_1548](/docs/containers?topic=containers-117_changelog#11714_1548), and [1.16.15_1554](/docs/containers?topic=containers-116_changelog#11615_1554).



### 9 December 2020
{: #containers-dec0920}
{: release-note}

Accessing clusters
:   Updated the steps for [accessing clusters through the private cloud service endpoint](/docs/containers?topic=containers-access_cluster#access_private_se) to use the `--endpoint private` option in the **`ibmcloud ks cluster config`** command.

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.206](/docs/containers?topic=containers-cs_cli_changelog#10).

Proxy protocol for Ingress
:   In VPC clusters, you can now [enable the PROXY protocol](/docs/containers?topic=containers-comm-ingress-annotations#preserve_source_ip_vpc) for all load balancers that expose Ingress ALBs in your cluster. The PROXY protocol enables load balancers to pass client connection information that is contained in headers on the client request, including the client IP address, the proxy server IP address, and both port numbers, to ALBs.

Helm version 2 unsupported
:   Removed all steps for using Helm v2, which is unsupported. [Migrate to Helm v3 today](https://helm.sh/docs/topics/v2_v3_migration/){: external} for several advantages over Helm v2, such as the removal of the Helm server, Tiller.



Istio add-on
:   [Version 1.8 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#v18) is released.



### 7 December 2020
{: #containers-dec0720}
{: release-note}

{{site.data.keyword.keymanagementserviceshort}} enhancements
:   For clusters that run `1.18.8_1525` or later, your cluster now [integrates more features from {{site.data.keyword.keymanagementserviceshort}}](/docs/containers?topic=containers-encryption-setup) when you enable {{site.data.keyword.keymanagementserviceshort}} as the KMS provider for the cluster. When you enable this integration, a **Reader** [service-to-service authorization policy](/docs/account?topic=account-serviceauth) between {{site.data.keyword.containerlong_notm}} and {{site.data.keyword.keymanagementserviceshort}} is automatically created for your cluster, if the policy does not already exist. If you have a cluster that runs an earlier version, [update your cluster](/docs/containers?topic=containers-update) and then [re-enable KMS encryption](/docs/containers?topic=containers-encryption) to register your cluster with {{site.data.keyword.keymanagementserviceshort}} again.

Worker node versions
:   Worker node fix pack update change log documentation is available.
:   Kubernetes version [1.19.4_1528](/docs/containers?topic=containers-changelog_119#1194_1528), [1.18.12_1534](/docs/containers?topic=containers-118_changelog#11812_1534), [1.17.14_1546](/docs/containers?topic=containers-117_changelog#11714_1546), and [1.16.15_1553](/docs/containers?topic=containers-116_changelog#11615_1553)..

### 3 December 2020
{: #containers-dec0320}
{: release-note}

Cluster autoscaler add-on
:   Patch update `1.0.1_146` is released. For more information, see the [Cluster autoscaler add-on change log](/docs/containers?topic=containers-ca_changelog).



Istio add-on
:   Versions [1.6.14](/docs/containers?topic=containers-istio-changelog#1614) and [1.7.5](/docs/containers?topic=containers-istio-changelog#175) of the Istio managed add-on are released.



### 1 December 2020
{: #containers-dec0120}
{: release-note}

Default Kubernetes Ingress image
:   In all new {{site.data.keyword.containerlong_notm}} clusters, default application load balancers (ALBs) now run the Kubernetes Ingress image. In existing clusters, ALBs continue to run the previously supported {{site.data.keyword.containerlong_notm}} Ingress image, which is now deprecated. For more information and migration actions, see Setting up Kubernetes Ingress.

## November 2020
{: #containers-nov20}



### 24 November 2020
{: #containers-nov2420}
{: release-note}

New! Reservations to reduce classic worker node costs
:   Create a reservation with contracts for 1 or 3 year terms for classic worker nodes to lock in a reduced cost for the life of the contract. Typical savings range between 30-50% compared to worker node costs. Reservations can be created in the {{site.data.keyword.cloud_notm}} console for classic infrastructure only. For more information, see [Reserving instances to reduce classic worker node costs](/docs/containers?topic=containers-reservations).

### 23 November 2020
{: #containers-nov2320}
{: release-note}

Worker node versions
:   Worker node fix pack update change log documentation is available.
:   Kubernetes version [1.19.4_1527](/docs/containers?topic=containers-changelog_119#1194_1527_worker), [1.18.12_1533](/docs/containers?topic=containers-118_changelog#11812_1533_worker), [1.17.14_1545](/docs/containers?topic=containers-117_changelog#11714_1545_worker), and [1.16.15_1552](/docs/containers?topic=containers-116_changelog#11615_1552_worker).

### 20 November 2020
{: #containers-nov2020}
{: release-note}

New! Portieris for image security enforcement
:   With the [open source Portieris project](https://github.com/IBM/portieris){: external}, you can set up a Kubernetes admission controller to enforce image security policies by namespace or cluster. Use [Portieris](/docs/Registry?topic=Registry-security_enforce_portieris) instead of the deprecated Container Image Security Enforcement Helm chart.

### 19 November 2020
{: #containers-nov1920}
{: release-note}

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 653 and the `ingress-auth` build to 425](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

### 18 November 2020
{: #containers-nov1820}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.197](/docs/containers?topic=containers-cs_cli_changelog#10).



Knative add-on deprecation
:   As of 18 November 2020 the Knative managed add-on is deprecated. On 18 December 2020 the add-on becomes unsupported and can no longer be installed, and on 18 January 2021 the add-on is automatically uninstalled from all clusters. If you use the Knative add-on, consider migrating to the [Knative open source project](https://knative.dev/docs/install/){: external} or to [{{site.data.keyword.codeenginefull}}](/docs/codeengine?topic=codeengine-getting-started), which includes the open source capabilities of Knative.



New! {{site.data.keyword.block_storage_is_short}} change log
:   Added a [change log](/docs/containers?topic=containers-vpc_bs_changelog) for the {{site.data.keyword.block_storage_is_short}} add-on.

### 16 November 2020
{: #containers-nov1620}
{: release-note}


      
GPU worker nodes
:   Added a reference to the [NVIDIA GPU operator installation guide](https://docs.nvidia.com/datacenter/cloud-native/gpu-operator/getting-started.html#operator-install-guide){: external} in the [deploying a sample GPU workload](/docs/containers?topic=containers-deploy_app#gpu_app) topic.


  
Master versions
:   Master fix pack update change log documentation is available for Kubernetes version [1.19.4_1527](/docs/containers?topic=containers-changelog_119#1194_1527), [1.18.12_1533](/docs/containers?topic=containers-118_changelog#11812_1533), [1.17.14_1545](/docs/containers?topic=containers-117_changelog#11714_1545), and [1.16.15_1552](/docs/containers?topic=containers-116_changelog#11615_1552)..

### 13 November 2020
{: #containers-nov1320}
{: release-note}

{{site.data.keyword.at_full_notm}} and IAM events
:   Added [IAM actions and {{site.data.keyword.cloudaccesstrailshort}} events](/docs/containers?topic=containers-api-at-iam#ks-ingress) for the Ingress secret, Ingress ALB, and NLB DNS APIs.

### 9 November 2020
{: #containers-nov0920}
{: release-note}



Worker node versions
:   Worker node fix pack update change log documentation is available.

:   Kubernetes version [1.19.3_1526](/docs/containers?topic=containers-changelog_119#1193_1526), [1.18.10_1532](/docs/containers?topic=containers-118_changelog#11810_1532), [1.17.13_1544](/docs/containers?topic=containers-117_changelog#11713_1544), and [1.16.15_1551](/docs/containers?topic=containers-116_changelog#11615_1551).

### 5 November 2020
{: #containers-nov0520}
{: release-note}

{{site.data.keyword.block_storage_is_short}}
:   Added topics for [verifying your {{site.data.keyword.block_storage_is_short}} file system](/docs/containers?topic=containers-vpc-block#vpc-block-fs-verify), [enabling every user to customize the default PVC settings](/docs/containers?topic=containers-vpc-block#customize-with-secret), and [enforcing base64 encoding for the {{site.data.keyword.keymanagementserviceshort}} root key CRN](/docs/containers?topic=containers-vpc-block#static-secret).

Classic-enabled VPCs
:   Added steps in [Creating VPC subnets for classic access](/docs/containers?topic=containers-vpc-subnets#ca_subnet_cli) for creating a classic-enabled VPC and VPC subnets without the automatic default address prefixes.



Gateway firewalls and Calico policies
:   For classic clusters in Dallas and Frankfurt, updated the required IP addresses and ports that you must open in a [public gateway firewall device](/docs/containers?topic=containers-firewall#firewall_outbound), [private gateway device firewall](/docs/containers?topic=containers-firewall#firewall_private), or [Calico network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies){: external}.


 
Istio add-on
:   Versions [1.6.13](/docs/containers?topic=containers-istio-changelog#1613) and [1.7.4](/docs/containers?topic=containers-istio-changelog#174) of the Istio managed add-on are released.



### 2 November 2020
{: #containers-nov0220}
{: release-note}



General availability of Kubernetes Ingress support
:   The Kubernetes Ingress image, which is built on the community Kubernetes project's implementation of the NGINX Ingress controller, is now generally available for the Ingress ALBs in your cluster.



Persistent storage
:   Added the following topics.
    - [Creating {{site.data.keyword.cos_full_notm}} service credentials](/docs/containers?topic=containers-storage-cos-understand#create_cos_secret)
    - [Adding your {{site.data.keyword.cos_full_notm}} credentials to the default storage classes](/docs/containers?topic=containers-storage-cos-understand#service_credentials)
    - [Backing up and restoring storage data](/docs/containers?topic=containers-storage_br)
    


## October 2020
{: #containers-oct20}

### 26 October 2020
{: #containers-oct2620}
{: release-note}

Master versions
:   Master fix pack update change log documentation is available.

:   Kubernetes version [1.19.3_1525](/docs/containers?topic=containers-changelog_119#1193_1525), [1.18.10_1531](/docs/containers?topic=containers-118_changelog#11810_1531), [1.17.13_1543](/docs/containers?topic=containers-117_changelog#11713_1543), and [1.16.15_1550](/docs/containers?topic=containers-116_changelog#11615_1550).

Worker node versions
:   Worker node fix pack update change log documentation is available.
:   Kubernetes version [1.19.3_1525](/docs/containers?topic=containers-changelog_119#1193_1525_worker), [1.18.10_1531](/docs/containers?topic=containers-118_changelog#11810_1531_worker), [1.17.13_1543](/docs/containers?topic=containers-117_changelog#11713_1543_worker), and [1.16.15_1550](/docs/containers?topic=containers-116_changelog#11615_1550_worker).


### 22 October 2020
{: #containers-oct2220}
{: release-note}

API key
:   Added more information about how the {{site.data.keyword.containerlong_notm}} API key is used.



Benchmark for Kubernetes 1.19
:   Review the [1.5 CIS Kubernetes benchmark results](/docs/containers?topic=containers-cis-benchmark-119) for clusters that run Kubernetes version 1.19.

Huge pages
:   In clusters that run Kubernetes 1.19 or later, you can [enable Kubernetes `HugePages` scheduling on your worker nodes](/docs/containers?topic=containers-kernel#huge-pages).

Istio add-on
:   Version [1.6.12](/docs/containers?topic=containers-istio-changelog#1612) of the Istio managed add-on is released.


  
### 16 October 2020
{: #containers-oct1620}
{: release-note}

Gateway firewalls and Calico policies
:   For classic clusters in Dallas, updated the required IP addresses and ports that you must open in a [public gateway firewall device](/docs/containers?topic=containers-firewall#firewall_outbound), [private gateway device firewall](/docs/containers?topic=containers-firewall#firewall_private), or [Calico network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies){: external}.



Ingress classes
:   Added information about specifying Ingress classes to apply Ingress resources to specific ALBs.



{{site.data.keyword.cos_short}}

:   Added steps to help you [decide on the object storage configuration](/docs/containers?topic=containers-storage_cos_install#configure_cos) and added troubleshooting steps for when [app pods fail because of an `Operation not permitted` error](/docs/containers?topic=containers-cos_operation_not_permitted).


### 13 October 2020
{: #containers-oct1320}
{: release-note}



New! Certified Kubernetes version 1.19
:   You can now create clusters that run Kubernetes version 1.19. To update an existing cluster, see the [Version 1.19 preparation actions](/docs/containers?topic=containers-cs_versions_119). The Kubernetes 1.19 release is also certified.

Deprecated: Kubernetes version 1.16
:   With the release of version 1.19, clusters that run version 1.16 are deprecated. Update your clusters to at least [version 1.17](/docs/containers?topic=containers-cs_versions#k8s_version_archive) today.

New! Network load balancer for VPC
:   In VPC Gen 2 clusters that run Kubernetes version 1.19, you can now create a layer 4 Network Load Balancer for VPC. VPC network load balancers offer source IP preservation and increased performance through direct server return (DSR). For more information, see [About VPC load balancing in {{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-vpc-lbaas).



Version change logs
:   Change log documentation is available for [1.19.2_1524](/docs/containers?topic=containers-changelog_119#1192_1524).

VPC load balancer
:   Added support for setting the `service.kubernetes.io/ibm-load-balancer-cloud-provider-vpc-node-selector` and `service.kubernetes.io/ibm-load-balancer-cloud-provider-vpc-subnet` annotations when you create new VPC load balancers in clusters that run Kubernetes version 1.19.

VPC security groups
:   Expanded the list of required rules based on the cluster version for default VPC security groups.

{{site.data.keyword.cos_short}} in VPC Gen 2
:   Added support for authorized IP addresses in {{site.data.keyword.cos_full_notm}} for VPC Gen 2. For more information, see [Allowing IP addresses for {{site.data.keyword.cos_full_notm}}](/docs/containers?topic=containers-storage_cos_vpc_ip).

### 12 October 2020
{: #containers-oct1220}
{: release-note}

Versions
:   Worker node fix pack update change log documentation is available.:   Kubernetes version [1.18.9_1530](/docs/containers?topic=containers-118_changelog#1189_1530), [1.17.12_1542](/docs/containers?topic=containers-117_changelog#11712_1542), and [1.16.15_1549](/docs/containers?topic=containers-116_changelog#11615_1549).

### 8 October 2020
{: #containers-oct0820}
{: release-note}

Ingress ALB change log
:   Updated the [Kubernetes Ingress image build to `0.35.0_474_iks`](/docs/containers?topic=containers-cs_versions_ingress#0_35_0).

### 6 October 2020
{: #containers-oct0620}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.178](/docs/containers?topic=containers-cs_cli_changelog#10).

Ingress secret expiration synchronization
:   Added a troubleshooting topic for when Ingress secret expiration dates are out of sync or are not updated.



Istio add-on
:   Versions [1.7.3](/docs/containers?topic=containers-istio-changelog#173) and [1.6.11](/docs/containers?topic=containers-istio-changelog#1611) of the Istio managed add-on are released.



### 1 October 2020
{: #containers-oct0120}
{: release-note}

Default version
:   The default version for clusters is now 1.18.

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 652 and the `ingress-auth` build to 424](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.

## September 2020
{: #containers-sep20}



### 29 September 2020
{: #containers-sept2920}
{: release-note}

Gateway firewalls and Calico policies
:   For classic clusters in London or Dallas, updated the required IP addresses and ports that you must open in a [public gateway firewall device](/docs/containers?topic=containers-firewall#firewall_outbound), [private gateway device firewall](/docs/containers?topic=containers-firewall#firewall_private), or [Calico network isolation policies](https://github.com/IBM-Cloud/kube-samples/tree/master/calico-policies){: external}.

### 26 September 2020
{: #containers-sept2620}
{: release-note}

Versions
:   Worker node fix pack update change log documentation is available.
:   Kubernetes version [1.18.9_1529](/docs/containers?topic=containers-118_changelog#1189_1529), [1.17.12_1541](/docs/containers?topic=containers-117_changelog#11712_1541), and [1.16.15_1548](/docs/containers?topic=containers-116_changelog#11615_1548).


### 24 September 2020
{: #containers-sept2420}
{: release-note}

CLI change log
:   Updated the {{site.data.keyword.containerlong_notm}} CLI plug-in change log page for the [release of version 1.0.171](/docs/containers?topic=containers-cs_cli_changelog#10).

### 23 September 2020
{: #containers-sept2320}
{: release-note}

Ingress ALB change log
:   Updated the [`nginx-ingress` build to 651 and the `ingress-auth` build to 423](/docs/containers?topic=containers-ingress-alb-manage#alb-version-list) for the {{site.data.keyword.containerlong_notm}} Ingress image.



Istio add-on
:   Version [1.7.2](/docs/containers?topic=containers-istio-changelog#172) of the Istio managed add-on is released.



### 22 September 2020
{: #containers-sept2220}
{: release-note}

Unsupported: Kubernetes version 1.15
:   Clusters that run version 1.15 are unsupported. To continue receiving important security updates and support, you must [update the cluster to a supported version](/docs/containers?topic=containers-cs_versions#prep-up) immediately.

### 21 September 2020
{: #containers-sept2120}
{: release-note}

Versions
:   Master fix pack update change log documentation is available.
:   Kubernetes version [1.18.9_1528](/docs/containers?topic=containers-118_changelog#1189_1528), [1.17.12_1540](/docs/containers?topic=containers-117_changelog#11712_1540), and [1.16.15_1547](/docs/containers?topic=containers-116_changelog#11615_1547).




Versions
:   Worker node fix pack update change log documentation is available.
:   Kubernetes version [1.18.8_1527](/docs/containers?topic=containers-118_changelog#1188_1527), [1.17.11_1539](/docs/containers?topic=containers-117_changelog#11711_1539), [1.16.14_1546](/docs/containers?topic=containers-116_changelog#11614_1546), and 1.15.12_1552.




Istio add-on
:   Versions [1.7.1](/docs/containers?topic=containers-istio-changelog#171) and [1.6.9](/docs/containers?topic=containers-istio-changelog#169) of the Istio managed add-on are released.

VPC load balancer
:   In version 1.18 and later VPC clusters, added the `service.kubernetes.io/ibm-load-balancer-cloud-provider-enable-features: "proxy-protocol"` annotation to preserve the source IP address of requests to apps in your cluster.
  
### 4 September 2020
{: #containers-sept0420}
{: release-note}

New! CIS Kubernetes Benchmark
:   Added information about {{site.data.keyword.containerlong_notm}} compliance with the [Center for Internet Security (CIS) Kubernetes Benchmark](/docs/containers?topic=containers-cis-benchmark) 1.5 for clusters that run Kubernetes version 1.18.



### 3 September 2020
{: #containers-sept0320}
{: release-note}

CA certificate rotation
:   Added steps to [revoke existing certificate authority (CA) certificates in your cluster and issue new CA certificates](/docs/containers?topic=containers-cert-rotate).


  
### 2 September 2020
{: #containers-sept0220}
{: release-note}

Istio add-on
:   [Version 1.7 of the Istio managed add-on](/docs/containers?topic=containers-istio-changelog#v17) is released.

### 1 September 2020
{: #containers-sept120}
{: release-note}

Deprecation of VPC Gen 1 compute
:   Virtual Private Cloud Generation 1 is deprecated. If you did not create any VPC Gen 1 resources before 01 September 2020, you can no longer provision any VPC Gen 1 resources. If you created any VPC Gen 1 resources before 01 September 2020, you can continue to provision and use VPC Gen 1 resources until 26 February 2021, when all service for VPC Gen 1 ends and all remaining VPC Gen 1 resources are deleted. To ensure continued support, create new VPC clusters on Generation 2 compute only, and move your workloads from existing VPC Gen 1 clusters to VPC Gen 2 clusters.

Istio add-on
:   [Version 1.5.10](/docs/containers?topic=containers-istio-changelog#1510) of the Istio managed add-on is released.



