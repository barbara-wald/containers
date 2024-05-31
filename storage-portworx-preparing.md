---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: portworx, kubernetes, containers

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}

# Preparing your cluster for Portworx
{: #storage_portworx_preparing}

If you want to build your Portworx storage layer on non-SDS worker nodes in your classic cluster must add raw, unformatted, and unmounted block storage to your worker nodes first. For VPC clusters, you can either attach storage before installing Portworx or allow Portworx to dynamically create Cloud Drives by using the {{site.data.keyword.block_storage_is_short}} driver during installation.
{: shortdesc}

Raw block storage can't be provisioned by using Kubernetes persistent volume claims (PVCs) as the block storage device is automatically formatted by {{site.data.keyword.containerlong_notm}}. Instead, you can use the {{site.data.keyword.cloud_notm}} Block Volume Attacher plug-in in classic clusters or the VPC console, CLI, or API in VPC clusters to add block storage to your worker nodes.

Portworx supports block storage only. Worker nodes that mount file or object storage can't be used for the Portworx storage layer.
{: note}

Keep in mind that the networking of non-SDS worker nodes in classic clusters is not optimized for Portworx and might not offer the performance benefits that your app requires.
{: note}

## Classic clusters
{: #px-create-classic-volumes}

[Classic]{: tag-classic} 

1. [Install the {{site.data.keyword.cloud_notm}} Block Volume Attacher plug-in](/docs/containers?topic=containers-utilities#block_storage_attacher).
2. [Manually add block storage](/docs/containers?topic=containers-utilities#manual_block) to your worker nodes. For highly available data storage, Portworx requires at least 3 worker nodes with raw and unformatted block storage.
3. If you want to use [journal devices](https://docs.portworx.com/portworx-enterprise/operations/operate-other/performance-and-tuning/tuning.html){: external}, choose from the following options. Journal devices allow Portworx to write logs directly to a local disk on your worker node.
    - Attach an additional disk to at least 3 worker nodes to use for the journal. [Manually add](/docs/containers?topic=containers-utilities#manual_block) a 3 GB block storage device to a worker node in your cluster and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
    - Select one of the block storage devices that you added earlier to use for the journal and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
    - Let Portworx automatically create a journal partition during installation.
4. If you want to use a specific device for the internal Portworx key value database (KVDB), choose from the following options.
    - Attach an additional disk to at least 3 worker nodes to use for key value database (KVDB). [Manually add](/docs/containers?topic=containers-utilities#manual_block) a 3 GB block storage device to at least 3 worker nodes in your cluster and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
    - Select one of the block storage devices that you added earlier and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
5. [Attach the block storage](/docs/containers?topic=containers-utilities#attach_block) to your worker nodes.
6. Continue with your Portworx setup by [Setting up a key-value store for Portworx metadata](/docs/containers?topic=containers-storage_portworx_kv_store).

## VPC clusters
{: #px-create-vpc-volumes}

[Virtual Private Cloud]{: tag-vpc} 

1. Follow the [steps](/docs/containers?topic=containers-utilities#vpc_cli_attach) to create the {{site.data.keyword.block_storage_is_short}} instances and attach these to each worker node that you want to add to the Portworx storage layer. For highly available data storage, Portworx requires at least 3 worker nodes with raw and unformatted block storage.
2. If you want to use [journal devices](https://docs.portworx.com/portworx-enterprise/operations/operate-other/performance-and-tuning/tuning.html){: external}, choose from the following options. Journal devices allow Portworx to write logs directly to a local disk on your worker node.
    - [Attach](/docs/containers?topic=containers-utilities#vpc_cli_attach) an additional 3 GB disk to at least 3 worker nodes in your cluster and find the device path. To find the device path after you attach the disk, log in to your worker node and run `lsblk` to list the devices on that node.
    - Select a device on a worker node where you want Portworx to create the journal.
3. If you want to use a specific device for the internal Portworx KVDB, choose from the following options.
    - Attach an additional disk to at least 3 worker nodes use for the KVDB. [Manually add](/docs/containers?topic=containers-utilities#manual_block) a 3 GB block storage device to at least 3 worker nodes in your cluster and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
    - Select one of the block storage devices that you added earlier to use for the KVDB and find the device path. To find the device path after attaching the disk, log in to your worker node and run `lsblk` to list the devices on that node.
4. Continue with your Portworx setup by [Setting up a key-value store for Portworx metadata](/docs/containers?topic=containers-storage_portworx_kv_store).



## Satellite clusters
{: #px-create-satellite-volumes}

[Satellite]{: tag-satellite} 

1. [Create a {{site.data.keyword.satelliteshort}} location](/docs/satellite?topic=satellite-locations).
1. Create VMs in your cloud provider or set up on-premises hosts that have at least 16 vCPU and 64 GB and enough storage to be attached to your location plus additional storage volumes for app data, the Portworx journal, and KVDB. For highly available data storage, Portworx requires at least 3 worker nodes with raw and unformatted block storage.
1. If you want to use [journal devices](https://docs.portworx.com/portworx-enterprise/operations/operate-other/performance-and-tuning/tuning.html){: external}, choose from the following options. Journal devices allow Portworx to write logs directly to a local disk on your worker node.
    - Attach an additional 3 GB disk to at least 3 worker nodes in your cluster and find the device path. To find the device path after you attach the disk, log in to your worker node with `oc debug <node>` and run `lsblk` to list the devices on that node.
    - Select a device on a worker node where you want Portworx to create the journal.
1. If you want to use a specific device for the internal Portworx KVDB, choose from the following options.
    - Attach an additional disk to at least 3 worker nodes use for the KVDB, add a 3 GB block storage device to at least 3 worker nodes in your cluster and find the device path. To find the device path after attaching the disk, log in to your worker node with `oc debug <node>` and run `lsblk` to list the devices on that node.
    - Select one of the block storage devices that you added earlier to use for the KVDB and find the device path. To find the device path after attaching the disk, log in to your worker node with `oc debug <node>` and run `lsblk` to list the devices on that node.
1. Continue with your Portworx setup by [Setting up a key-value store for Portworx metadata](/docs/containers?topic=containers-storage_portworx_kv_store).










