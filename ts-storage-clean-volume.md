---

copyright: 
  years: 2022, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, help, storage

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Why am I still seeing charges for block storage devices after deleting my cluster?
{: #ts_storage_clean_volume}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}

You have already deleted your cluster but your account is still charged for the storage volumes associated with the cluster.
{: tsSymptoms}


When you delete your cluster, you have the option to delete the storage volumes used by the cluster. If you select no, the storage volumes remain in your account, and continue incurring charges until they are deleted.
{: tsCauses}

Delete the storage volumes from your account.
{: tsResolve}

1. Find the cluster ID of the deleted cluster. This ID is used to remove associated block storage volumes. If you don't have the cluster ID of the deleted cluster, run `ibmcloud ks cluster ls` and a make a note of the cluster IDs whose block storage volumes you want to keep.

    ```sh
    ibmcloud ks cluster ls
    ```
    {: pre}
    
2. Find the remaining volumes that are associated with the deleted cluster.

    Classic clusters:
    ```sh
    ibmcloud ks storage volume ls --provider classic | awk '{print $1 " " $8}'
    ```
    {: pre}
    
    Example output for Classic Block Storage volumes. Note the volume ID and the cluster ID.
    ```sh
    102413596 blntvemw0j6snjt04jr0
    ```
    {: screen}
    
    
    VPC clusters:
    ```sh
    ibmcloud ks storage volume ls --provider vpc-gen2 | awk '{print $1 " " $8}'
    ```
    {: pre}

3. Remove the volumes.
    
    Classic clusters:
    ```sh
    ibmcloud sl block volume-cancel VOLUME_ID
    ```
    {: pre}

    VPC clusters:
    ```sh
    ibmcloud is vold VOLUME_NAME_OR_ID
    ```
    {: pre}

4. Optional: Verify there are no more volumes associated with the deleted cluster.
    
    Classic clusters:
    ```sh
    ibmcloud ks storage volume ls --provider classic | awk '{print $1 " " $8}'
    ```
    {: pre}

    VPC clusters:
    ```sh
    ibmcloud ks storage volume ls --provider vpc-gen2 | awk '{print $1 " " $8}'
    ```
    {: pre}
