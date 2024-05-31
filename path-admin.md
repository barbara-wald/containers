---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Learning path for administrators
{: #learning-path-admin}

Following a curated learning path through {{site.data.keyword.containerlong}} to create a cluster, manage the cluster's resources and lifecycle, and use the powerful tools of {{site.data.keyword.containerlong_notm}} to secure, manage, and monitor your cluster workloads.
{: shortdesc}



## Plan your environment
{: #admin_plan}

Start by designing a cluster for maximum availability and capacity for your workloads.
{: shortdesc}

1. **Environment strategy**:
    1. Define your [Kubernetes strategy](/docs/containers?topic=containers-strategy) for the cluster, such as deciding how many clusters to create for your environments.
    2. Plan your [security strategy](/docs/containers?topic=containers-security#network_segmentation), such as ensuring network segmentation and workload isolation.

2. **Cluster setup**: After you plan your environment, plan the setup for a specific cluster.
    1. Choose a [supported infrastructure provider](/docs/containers?topic=containers-overview#what-compute-infra-is-offered).
    2. Plan your cluster network setup.
        - [Understanding VPC cluster network basics](/docs/containers?topic=containers-plan_vpc_basics).
        - [Understanding Classic cluster network basics](/docs/containers?topic=containers-plan_basics).
    3. Plan your cluster for [high availability](/docs/containers?topic=containers-ha_clusters).
    4. Plan your [worker node setup](/docs/containers?topic=containers-planning_worker_nodes).

Looking for serverless? Try [{{site.data.keyword.codeengineshort}}](/docs/codeengine?topic=codeengine-getting-started).
{: tip}

## Create a cluster
{: #admin_cluster}

Create a cluster with infrastructure, network, and availability setups that are customized to your use case and cloud environment.
{: shortdesc}

1. **Firewall**: If you have corporate firewalls, make sure that you [open the required ports and IP addresses](/docs/containers?topic=containers-firewall#corporate) to work with {{site.data.keyword.containerlong_notm}}.
2. **CLI and API**:
    1. [Set up the CLIs](/docs/containers?topic=containers-cli-install) that are necessary to create and work with clusters. As you work with your cluster, refer to the [command reference](/docs/containers?topic=containers-kubernetes-service-cli) and keep track of CLI version updates with the [CLI change log](/docs/containers?topic=containers-cs_cli_changelog).
    2. Optionally set up [automated deployments with the API](/docs/containers?topic=containers-cs_api_install). As you work with your cluster, refer to the [IBM Cloud Kubernetes Service API reference](https://containers.cloud.ibm.com/global/swagger-global-api/#/){: external} and [Community Kubernetes API reference](https://kubernetes.io/docs/reference/){: external}.
3. **Cluster deployment**:
    1. [Create the cluster](/docs/containers?topic=containers-clusters).
    2. After the cluster is ready, [access your cluster](/docs/containers?topic=containers-access_cluster).
    3. Spread your cluster across availability zones [adding worker nodes to Classic clusters](/docs/containers?topic=containers-add-workers-classic) or [adding worker nodes to VPC clusters](/docs/containers?topic=containers-add-workers-vpc). 
4. **User access**:
    * Make sure that your authorized cluster users can now also access the cluster by planning your user access strategy.
    * [Pick the correct access policy and role for your users](/docs/containers?topic=containers-iam-platform-access-roles). Choose the scope of user access to cluster instances, Kubernetes namespace, or resource groups.



Need help? Check out [Troubleshooting clusters and masters](/docs/containers?topic=containers-debug_clusters) and [Troubleshooting worker nodes](/docs/containers?topic=containers-debug_worker_nodes).
{: tip}


## Manage the network
{: #admin_network}

Review the following optional topics to manage the network connectivity of your cluster components and connections to other networks. For example, you might need to connect the workloads in your cluster to workloads in another private network. Or, you might return to this section later if you need to make more portable IP addresses available for load balancer services that expose apps in your cluster.
{: shortdesc}

- **Connections to other networks and workloads**:
    - Set up VPN connectivity between your [classic cluster](/docs/containers?topic=containers-vpn) or [VPC cluster](/docs/containers?topic=containers-vpc-vpnaas) and remote network environments, other VPCs, and more.
    - To route responses from your cluster back to your on-premises network in VPN solutions that preserve the request source IP address, add [custom static routes](/docs/containers?topic=containers-static-routes) to worker nodes for on-premises subnets.
- **Subnets, service endpoints, and VLANs**:
    - Add or change the available subnets and IP addresses for your [classic cluster](/docs/containers?topic=containers-subnets) or [VPC cluster](/docs/containers?topic=containers-vpc-subnets).
    - Change the [service endpoints that your Kubernetes master is accessible through](/docs/containers?topic=containers-cs_network_cluster).
    - Classic clusters: Change the [VLAN connections for your worker nodes](/docs/containers?topic=containers-cs_network_cluster#change-vlans).



## Secure your cluster
{: #admin_secure}

Use built-in security features to protect your cluster infrastructure and network communication, isolate your compute resources, and ensure security compliance across your infrastructure components and container deployments.
{: shortdesc}

1. **Security strategy**: Start by reviewing all [security options](/docs/containers?topic=containers-security) that are available for your cluster.
2. **Network security**:
    - Classic clusters:
        1. To isolate networking workloads, you can restrict network traffic to [edge worker nodes](/docs/containers?topic=containers-edge).
        2. Set up a firewall by using a [gateway appliance](/docs/containers?topic=containers-firewall#vyatta_firewall) or [Calico network policies](/docs/containers?topic=containers-network_policies).
    - VPC clusters: Control traffic to and from your cluster with [VPC security groups](/docs/containers?topic=containers-vpc-security-group-manage).
3. **Workload security**:
    1. [Encrypt sensitive information](/docs/containers?topic=containers-encryption) in the cluster, such as the master's local disk and secrets.
    2. Set up a [private image registry](/docs/containers?topic=containers-security#images_registry) for your developers, such as the one provided by {{site.data.keyword.registryshort}}, to control access to the registry and the image content that can be pushed.
    3. [Set pod priority](/docs/containers?topic=containers-pod_priority) to indicate the relative priority of the pods that make up your cluster's workload.
    4. Authorize who can create and update pods by configuring [pod security policies (PSPs)](/docs/containers?topic=containers-psp).



## Logging and monitoring
{: #admin_health}

Set up logging and monitoring to help you troubleshoot issues and improve the health and performance of your Kubernetes clusters and apps.
{: shortdesc}



1. **Cluster and app logging**: [Choose a logging solution](/docs/containers?topic=containers-health#logging_overview), such as {{site.data.keyword.la_full}}, to monitor container logs as well as user-initiated administrative activities.
2. **Audit logging**: [Forwarding Kubernetes API audit logs to {{site.data.keyword.la_full_notm}}](/docs/containers?topic=containers-health-audit)
3. **Monitoring**: [Choose a monitoring solution](/docs/containers?topic=containers-health-monitor#view_metrics), such as {{site.data.keyword.mon_full}}, to gain operational visibility into the performance and health of your apps.

Need help? Check out [Troubleshooting logging and monitoring](/docs/containers?topic=containers-cs_dashboard_graphs).
{: tip}





## Add a registry and CI/CD
{: #admin_registry}

Set up an image registry and a continuous integration and delivery (CI/CD) pipeline for your cluster.
{: shortdesc}

1. **Registry**: Choose and set up an [image registry](/docs/containers?topic=containers-registry) so that developers can pull images from the registry in their app deployment YAML files.
2. **CI/CD**:
    - Review available [options for automating app deployment](/docs/containers?topic=containers-cicd).
    - Set up toolchains with [{{site.data.keyword.deliverypipelinelong}}](/docs/containers?topic=containers-cicd).

## Add storage
{: #admin_storage}

Plan and add highly available persistent storage based on your app requirements, the type of data that you want to store, and how often you want to access this data.
{: shortdesc}

1. **Requirements**: Determine your [requirements for a storage solution](/docs/containers?topic=containers-storage-plan).
2. **Choose a solution**: Using your storage requirements, choose a storage solution by comparing [non-persistent](/docs/containers?topic=containers-storage-plan), [single-zone persistent](/docs/containers?topic=containers-storage-plan), or [multizone persistent](/docs/containers?topic=containers-storage-plan) storage.

Need help? Check out the troubleshooting page for your persistent storage solution.
{: tip}


## Add integrations
{: #admin_integrate}

Enhance cluster capabilities by integrating various external services and catalog services with your Kubernetes cluster.
{: shortdesc}

1. **Review supported integrations**:
    - [All supported integrations](/docs/containers?topic=containers-supported_integrations)
    - [{{site.data.keyword.containerlong_notm}} partners](/docs/containers?topic=containers-supported_integrations)

    - [{{site.data.keyword.cloud_notm}} services and third-party integrations](/docs/containers?topic=containers-ibm-3rd-party-integrations)
2. **Add services to your cluster**:
    - [Adding services by using managed add-ons](/docs/containers?topic=containers-managed-addons)
    - [Adding services by using Helm](/docs/containers?topic=containers-helm)
    - [Adding services by using {{site.data.keyword.cloud_notm}} service binding](/docs/containers?topic=containers-service-binding)

Need help? Check out [Troubleshooting apps and integrations](/docs/containers?topic=containers-debug_worker_nodes).
{: tip}


## Manage the lifecycle
{: #admin_lifecycle}

Manage your cluster and worker nodes through each phase of the cluster lifecycle.
{: shortdesc}

- **Autoscaling**: [Automatically increase or decrease the number of worker nodes](/docs/containers?topic=containers-cluster-scaling-install-addon) based on the sizing needs of your scheduled workloads.
- **Updating**: Keep your environment up-to-date by frequently [updating clusters, worker nodes, and cluster components](/docs/containers?topic=containers-update). While you update, refer to these version reference pages:
    - [Kubernetes version information](/docs/containers?topic=containers-cs_versions)
    - [Fluentd and Ingress ALB change log](/docs/containers?topic=containers-cs_versions_ingress)
- **Removing**: [Remove clusters and clean up related resources](/docs/containers?topic=containers-remove).



Need help? Check out troubleshooting [clusters and masters](/docs/containers?topic=containers-debug_clusters), [worker nodes](/docs/containers?topic=containers-debug_worker_nodes), or the [cluster autoscaler](/docs/containers?topic=containers-debug_cluster_autoscaler).
{: tip}



