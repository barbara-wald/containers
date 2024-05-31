---

copyright: 
  years: 2022, 2024
lastupdated: "2024-05-29"


keywords: containers, {{site.data.keyword.containerlong_notm}}, add-on, file

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}



# Enabling the {{site.data.keyword.filestorage_vpc_full_notm}} add-on
{: #storage-file-vpc-install}

[Virtual Private Cloud]{: tag-vpc}

{{site.data.keyword.filestorage_vpc_full_notm}} is persistent, fast, and flexible network-attached, NFS-based {{site.data.keyword.filestorage_vpc_short}} that you can add to your apps by using Kubernetes persistent volumes (PVs). You can choose between predefined storage tiers with GB sizes and IOPS that meet the requirements of your workloads. To find out if {{site.data.keyword.filestorage_vpc_short}} is the correct storage option for you, see [Choosing a storage solution](/docs/containers?topic=containers-storage-plan). For pricing information, see [Pricing](https://cloud.ibm.com/cloud-storage/file/order){: external}.
{: shortdesc}


## Prerequisites
{: #prereqs-store-file-vpc}

1. Update the `container-service` plug-in to the most recent version. You can update the plug-in by running the following command.
    ```shell
    ibmcloud update && ibmcloud plugin update container-service
    ```
    {: pre}

1. Get a list of the add-on versions and decide which version to install for your cluster version.
    ```sh
    ibmcloud ks cluster addon versions --addon vpc-file-csi-driver
    ```
    {: pre}

    Example output
    ```sh
    OK
    Name                  Version         Supported Kubernetes Range   Supported OpenShift Range   Kubernetes Default   OpenShift Default
    vpc-file-csi-driver   1.0 (default)   >=1.24.0 <1.31.0             >=4.10.0 <4.16.0            -                    -
    ```
    {: pre}

1. Enable the add-on. 
    ```sh
    ibmcloud ks cluster addon enable vpc-file-csi-driver --version VERSION --cluster CLUSTERID
    ```
    {: pre}


1. Verify that the add-on is enabled.
    ```sh
    ibmcloud ks cluster addon ls --cluster <cluster_name_or_ID>
    ```
    {: pre}

    Example output
    ```sh
    Name                   Version   Health State   Health Status   
    vpc-file-csi-driver    1.0.0     normal         Addon Ready
    ```
    {: pre}


## Next steps
{: #vpc-enable-next-steps}

Review the following links to continue setting up {{site.data.keyword.filestorage_vpc_short}}.

- [Quick start for {{site.data.keyword.filestorage_vpc_short}}](/docs/containers?topic=containers-storage-file-vpc-apps#vpc-add-file-dynamic)
- [Adding {{site.data.keyword.filestorage_vpc_short}} to apps](/docs/containers?topic=containers-storage-file-vpc-apps).
- [Managing {{site.data.keyword.filestorage_vpc_short}}](/docs/containers?topic=containers-storage-file-vpc-managing).
- [{{site.data.keyword.filestorage_vpc_short}} storage class reference](/docs/containers?topic=containers-storage-file-vpc-sc-ref).

