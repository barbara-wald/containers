---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, help, network, connectivity

subcollection: containers

content-type: troubleshoot

---


{{site.data.keyword.attribute-definition-list}}





# Why does installing the {{site.data.keyword.cos_full_notm}} plug-in fail?
{: #cos_plugin_fails}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}


When you install the `ibm-object-storage-plugin`, the installation fails with an error similar to the following:
{: tsSymptoms}

```sh
Error: rendered manifest contains a resource that already exists. Unable to continue with install. Existing resource conflict: namespace: , name: ibmc-s3fs-smart-cross-region, existing_kind: storageClass, new_kind: storage.k8s.io/v1, Kind=StorageClass
Error: plugin "ibmc" exited with error
```
{: screen}


During the installation, many different tasks are executed by the {{site.data.keyword.cos_full_notm}} plug-in such as creating storage classes and cluster role bindings. 
{: tsCauses}

Some resources might already exist in your cluster from previous {{site.data.keyword.cos_full_notm}} plug-in installations and were not properly removed when you removed or upgraded the plug-in.

Delete the resource that is display in the error message and retry the installation.
{: tsResolve}

1. Delete the resource that is displayed in the error message.
    ```sh
    kubectl delete <resource_kind> <resource_name>
    ```
    {: pre}

    Example for deleting a storage class resource:
    ```sh
    kubectl delete storageclass <storage_class_name>
    ```
    {: pre}

1. [Retry the installation](/docs/containers?topic=containers-storage_cos_install).

1. If you continue to see the same error, get a list of the resources that are installed when the plug-in is installed. Get a list of storage classes that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get sc --all-namespaces \
            -l app=ibmcloud-object-storage-plugin \
            -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of cluster role bindings that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get ClusterRoleBinding --all-namespaces \
            -l app=ibmcloud-object-storage-plugin \
            -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of role bindings that are created by the `ibmcloud-object-storage-driver`.
    ```sh
    kubectl get RoleBinding --all-namespaces \
        -l app=ibmcloud-object-storage-driver \
        -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of role bindings that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get RoleBinding --all-namespaces \
            -l app=ibmcloud-object-storage-plugin \
            -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of cluster roles that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get ClusterRole --all-namespaces \
        -l app=ibmcloud-object-storage-plugin \
        -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of deployments that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get deployments --all-namespaces \
        -l app=ibmcloud-object-storage-plugin \
        -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of the daemon sets that are created by the `ibmcloud-object-storage-driver`.
    ```sh
    kubectl get DaemonSets --all-namespaces \
        -l app=ibmcloud-object-storage-driver \
        -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}

1. Get a list of the service accounts that are created by the `ibmcloud-object-storage-driver`.
    ```sh
    kubectl get ServiceAccount --all-namespaces \
        -l app=ibmcloud-object-storage-driver \
        -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre }

1. Get a list of the service accounts that are created by the `ibmcloud-object-storage-plugin`.
    ```sh
    kubectl get ServiceAccount --all-namespaces \
        -l app=ibmcloud-object-storage-plugin \
        -o jsonpath='{range .items[*]}{.metadata.namespace}{"\t"}{.metadata.name}{"\n"}{end}'
    ```
    {: pre}
    
1. Delete the conflicting resources.

1. After you delete the conflicting resources, [retry the installation](/docs/containers?topic=containers-storage_cos_install).








