---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}




# Setting Kubernetes API priority and fairness
{: #kubeapi-priority}

Your {{site.data.keyword.containerlong}} clusters have default settings in place to process simultaneous requests to the API server and prevent traffic overload. You can configure your own flow schema and priority levels for requests that are made to the API server of your clusters. For more information, see [API priority and fairness](https://kubernetes.io/docs/concepts/cluster-administration/flow-control/){: external} in the Kubernetes documentation.
{: shortdesc}

For example, you might have a user or namespace that runs your critical apps in prod. You can create a flow schema and priority so that your critical apps have a higher priority for the API server to fulfill their requests than other apps in the cluster.

## Reviewing default flow schema and priority levels
{: #kubeapi-default-priority}

{{site.data.keyword.containerlong_notm}} sets certain default flow schema and priority levels in addition to the default settings from Kubernetes.
{: shortdesc}

| Flow schema | Resources that requests come from | Priority level |
| ----------- | --------- | -------------- |
| `apiserver-health` | Kubernetes API server health resources | [Custom priority level](#kube-api-prioritylevelconfig) for these resources. |
| `calico-system-service-accounts` | Resources in the `calico-system` namespace that use a service account in the namespace | Same priority as `kube-system` namespace service accounts. This schema is available for {{site.data.keyword.containerlong}} version 1.29 and later.|
| `ibm-admin` | Resources from IBM cluster administrators | Exempts requests by cluster administrators from priority restrictions |
| `ibm-system-service-accounts` | Resources in the `ibm-system` namespace that use a service account in the namespace | Same priority as `kube-system` namespace service accounts |
| `ibm-operators-service-accounts` | Resources in the `ibm-operators` namespace that use a service account in the namespace | Same priority as `kube-system` namespace service accounts |
| `system-node-proxiers` | The `kube-proxy` | Same priority as the `kubelet` |
| `tigera-operator-service-accounts` | Resources in the `tigera-operator` namespace that use a service account in the namespace | Same priority as `kube-system` namespace service accounts. This schema is available for {{site.data.keyword.containerlong}} version 1.29 and later.|
{: caption="Default flow schema and priority levels" caption-side="bottom"}

You can create your own flow schema and priorities, but don't modify the default settings. Unexpected results might occur in your cluster when you modify API request priorities.
{: important}

Follow the steps to review the flow schemas and priority levels set by {{site.data.keyword.containerlong_notm}}.

1. List all flow schemas in your cluster, including those set by {{site.data.keyword.containerlong_notm}}, and their corresponding priority levels .
    ```sh
    kubectl get flowschemas
    ```
    {: pre} 


2. Review the details of a particular flow schema including which resources can make prioritized API requests, what type of API requests can be made, and what objects the requests can modify.
    ```sh
    kubectl describe flowschema <flow-schema-name>
    ```
    {: pre}

### Viewing {{site.data.keyword.containerlong_notm}} created priority level configurations
{: #kube-api-prioritylevelconfig}

{{site.data.keyword.containerlong_notm}} sets a custom priority level configuration for the `apiserver-health` resource. 
{: shortdesc}

Use the following commands to view details about the configuration. 

```sh
kubectl get prioritylevelconfiguration apiserver-health
```
{: pre}
 
```sh
kubectl describe prioritylevelconfiguration apiserver-health
```
{: pre}








