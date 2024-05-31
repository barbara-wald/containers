---

copyright: 
  years: 2022, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers

---

{{site.data.keyword.attribute-definition-list}}




# {{site.data.keyword.containerlong_notm}} CLI Map
{: #icks_map}

This page lists all `ibmcloud ks` commands as they are structured in the CLI. For more details on a specific command, click on the command or see the [{{site.data.keyword.containerlong_notm}} CLI reference](/docs/containers?topic=containers-kubernetes-service-cli).



## ibmcloud ks cluster
{: #icks_map_cluster}

[View and modify cluster and cluster service settings](/docs/containers?topic=containers-kubernetes-service-cli#cluster).
{: shortdesc}

* **`cluster addon`**: View, enable, update, and disable cluster add-ons.
    * [`ibmcloud ks cluster addon disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_disable)
    * [`ibmcloud ks cluster addon enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_enable)
    * [`ibmcloud ks cluster addon get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_get)
    * [`ibmcloud ks cluster addon ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addons)
    * [`ibmcloud ks cluster addon options`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_options)
    * [`ibmcloud ks cluster addon update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_addon_update)
    * [`ibmcloud ks cluster addon versions`](/docs/containers?topic=containers-kubernetes-service-cli#cs_addon_versions)
* **`cluster ca`**: Manage the Certificate Authority (CA) certificates of a cluster.
    * [`ibmcloud ks cluster ca create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_create)
    * [`ibmcloud ks cluster ca get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_get)
    * [`ibmcloud ks cluster ca rotate`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_rotate)
    * [`ibmcloud ks cluster ca status`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_ca_status)
* [`ibmcloud ks cluster config`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_config)
* **`cluster create`**: Create a classic or VPC cluster.
    * [`ibmcloud ks cluster create classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_create)
    * [`ibmcloud ks cluster create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_cluster-create-vpc-gen2)
* [`ibmcloud ks cluster get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_get)
* **`cluster image-security`**: Manage image security enforcement in your cluster.
    * [`ibmcloud ks cluster image-security disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs-image-security-disable)
    * [`ibmcloud ks cluster image-security enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs-image-security-enable)
* [`ibmcloud ks cluster ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_clusters)
* **`cluster master`**: View and modify the master for a cluster.
    * **`cluster master audit-webhook`**: View and modify the audit webhook configuration for a cluster's Kubernetes API server.
        * [`ibmcloud ks cluster master audit-webhook get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_config_get) 
        * [`ibmcloud ks cluster master audit-webhook set`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_config_set) 
        * [`ibmcloud ks cluster master audit-webhook unset`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_config_unset)
    * **`cluster master pod-security`**: View and modify your Pod Security configurations.
        * [`ibmcloud ks cluster master pod-security get`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-get)
        * [`ibmcloud ks cluster master pod-security set`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-set)
        * [`ibmcloud ks cluster master pod-security unset`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-unset)
        * **`ibmcloud ks cluster master pod-security policy`**: View and modify the deprecated Pod Security policy configuration in supported clusters.
            * [`ibmcloud ks cluster master pod-security policy disable`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-policy-disable)
            * [`ibmcloud ks cluster master pod-security policy enable`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-policy-enable)
            * [`ibmcloud ks cluster master pod-security policy get`](/docs/containers?topic=containers-kubernetes-service-cli#cluster-master-pod-security-policy-get)
    * **`cluster master private-service-endpoint`**: Manage the private service endpoint of a cluster.
        * **`ibmcloud ks cluster master private-service-endpoint allowlist`**: Manage the private service endpoint allowlist.
            * [`ibmcloud ks cluster master private-service-endpoint allowlist add`](/docs/containers?topic=containers-kubernetes-service-cli#cs_master_pse_allowlist_add)
            * [`ibmcloud ks cluster master private-service-endpoint allowlist disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_master_pse_allowlist_disable)
            * [`ibmcloud ks cluster master private-service-endpoint allowlist enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_master_pse_allowlist_enable)
            * [`ibmcloud ks cluster master private-service-endpoint allowlist get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_master_pse_allowlist_get)
            * [`ibmcloud ks cluster master private-service-endpoint allowlist remove`](/docs/containers?topic=containers-kubernetes-service-cli#cs_master_pse_allowlist_rm)
        * [`ibmcloud ks cluster master private-service-endpoint enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pse_enable)
    * **`cluster master public-service-endpoint`**: Manage the public service endpoint of a cluster.
        * [`ibmcloud ks cluster master public-service-endpoint disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pub_se_disable)
        * [`ibmcloud ks cluster master public-service-endpoint enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_master_pub_se_enable)
    * [`ibmcloud ks cluster master refresh`](/docs/containers?topic=containers-kubernetes-service-cli#cs_apiserver_refresh)
    * [`ibmcloud ks cluster master update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_update)
* **`cluster pull-secret`**: Manage image pull secrets for the cluster to access images in IBM Cloud Container Registry.
    * [`ibmcloud ks cluster pull-secret apply`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_pull_secret_apply) 
* [`ibmcloud ks cluster rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_rm)
* **`cluster service`**: View, bind, and unbind IBM Cloud services on a cluster.
    * [`ibmcloud ks cluster service bind`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_service_bind)
    * [`ibmcloud ks cluster service ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_services)
    * [`ibmcloud ks cluster service unbind`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_service_unbind)
* **`cluster subnet`**: Add and create portable subnets for a classic cluster.
    * [`ibmcloud ks cluster subnet add`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_subnet_add)
    * [`ibmcloud ks cluster subnet create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_subnet_create)
    * [`ibmcloud ks cluster subnet detach`](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_subnet_detach)

## ibmcloud ks worker
{: #icks_map_worker}

[View and modify worker nodes for a cluster](/docs/containers?topic=containers-kubernetes-service-cli#worker_node_commands).
{: shortdesc}

* **Deprecated** [`ibmcloud ks worker add`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_add) 
* [`ibmcloud ks worker get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_get)
* [`ibmcloud ks worker ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_workers)
* [`ibmcloud ks worker reboot`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reboot)
* [`ibmcloud ks worker reload`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reload)
* [`ibmcloud ks worker replace`](/docs/containers?topic=containers-kubernetes-service-cli#cli_worker_replace)
* [`ibmcloud ks worker rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_rm)
* [`ibmcloud ks worker update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_update)

## ibmcloud ks worker-pool
{: #icks_map_worker-pool}

[View and modify worker pools for a cluster](/docs/containers?topic=containers-kubernetes-service-cli#worker-pool).
{: shortdesc}

* **`worker-pool create`**: Add a worker pool to a cluster. No worker nodes are created until zones are added to the worker pool.
    * [`ibmcloud ks worker-pool create classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_create)
    * [`ibmcloud ks worker-pool create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_worker_pool_create_vpc_gen2)
* [`ibmcloud ks worker-pool get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_get)
* **`worker-pool label`**: Set and remove custom Kubernetes labels for all worker nodes in a worker pool.
    * [`ibmcloud ks worker-pool label rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_label_rm)
    * [`ibmcloud ks worker-pool label set`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_label_set)
* [`ibmcloud ks worker-pool ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pools)
* [`ibmcloud ks worker-pool rebalance`](/docs/containers?topic=containers-kubernetes-service-cli#cs_rebalance)
* [`ibmcloud ks worker-pool resize`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_resize)
* [`ibmcloud ks worker-pool rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_rm)
* **[`worker-pool taint`]**: Set and remove Kubernetes taints for all worker nodes in a worker pool.
    * [`ibmcloud ks worker-pool taint rm`](/docs/containers?topic=containers-kubernetes-service-cli#worker_pool_taint_rm)
    * [`ibmcloud ks worker-pool taint set`](/docs/containers?topic=containers-kubernetes-service-cli#worker_pool_taint_set)
* [`ibmcloud ks worker-pool zones`](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_pool_zones)

## ibmcloud ks zone
{: #icks_map_zone}

[List availability zones and modify the zones attached to a worker pool](/docs/containers?topic=containers-kubernetes-service-cli#zone).
{: shortdesc}

* **`zone add`**: Add a zone to one or more worker pools in a cluster.
    * [`ibmcloud ks zone add classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_zone_add)
    * [`ibmcloud ks zone add vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_zone-add-vpc-gen2)
* [`ibmcloud ks zone ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_datacenters)
* [`ibmcloud ks zone network-set`](/docs/containers?topic=containers-kubernetes-service-cli#cs_zone_network_set)
* [`ibmcloud ks zone rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_zone_rm)

## ibmcloud ks ingress
{: #icks_map_ingress}

[View and modify Ingress services and settings](/docs/containers?topic=containers-kubernetes-service-cli#alb-commands).
{: shortdesc}

* **`ingress alb`**: View and configure an Ingress application load balancer (ALB).
    * **`ingress alb autoscale`**: Configure autoscaling for Ingress ALBs. 
        * [`ibmcloud ks ingress alb autouscale get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoscale_get)
        * [`ibmcloud ks ingress alb autouscale set`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoscale_set)
        * [`ibmcloud ks ingress alb autouscale unset`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoscale_unset)
    * **`ingress alb autoupdate`**: Manage automatic updates for the Ingress ALB add-on in a cluster.
        * [`ibmcloud ks ingress alb autoupdate disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_disable)
        * [`ibmcloud ks ingress alb autoupdate enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_enable)
        * [`ibmcloud ks ingress alb autoupdate get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_autoupdate_get)
    * **`ingress alb create`**: Create an Ingress ALB in a cluster.
        * [`ibmcloud ks ingress alb create classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_create)
        * [`ibmcloud ks ingress alb create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_alb-create-vpc-gen2)
    * [`ibmcloud ks ingress alb disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_disable)
    * **`ingress alb enable`**: Enable an Ingress ALB in a cluster.
        * [`ibmcloud ks ingress alb enable classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_configure)
        * [`ibmcloud ks ingress alb enable vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cli_alb_configure_vpc_gen2)
    * [`ibmcloud ks ingress alb get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_get)
    * **`ingress alb health-checker`**: Manage the Ingress ALB health checker.
        * [`ibmcloud ks ingress alb health-checker disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_healthchecker_disable)
        * [`ibmcloud ks ingress alb health-checker enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_healthchecker_enable)
        * [`ibmcloud ks ingress alb health-checker get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_healthchecker_get)
    * [`ibmcloud ks ingress alb ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_albs)
    * [`ibmcloud ks ingress alb update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_update)
    * [`ibmcloud ks ingress alb versions`](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_versions)
* **`ingress lb`**: Modify load balancers that expose Ingress ALBs in your cluster.
    * [`ibmcloud ks ingress lb get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_lb_proxy-protocol_get)
    * **`ingress lb proxy-protocol`**: **VPC only** Modify the PROXY protocol configuration for ALB load balancers.
        * [`ibmcloud ks ingress lb proxy-protocol disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_lb_proxy-protocol_disable)
        * [`ibmcloud ks ingress lb proxy-protocol enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_lb_proxy-protocol_enable)
* **`ingress secret`**: Manage Ingress secrets in a cluster.
    * [`ibmcloud ks ingress secret create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_create)
    * [`ibmcloud ks ingress secret get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_get)
    * [`ibmcloud ks ingress secret ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_ls)
    * [`ibmcloud ks ingress secret rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_rm)
    * [`ibmcloud ks ingress secret update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_update) 
* **`ingress status-report`**: View and manage ingress status reporting.
    * [`ibmcloud ks ingress status-report disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_disable)
    * [`ibmcloud ks ingress status-report enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_enable)
    * [`ibmcloud ks ingress status-report get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_get)
* **`ibmcloud ks ingress status-report ignore`**: Manage warnings to be ignored by ingress status reports.
    * [`ibmcloud ks ingress status-report ignore add`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_add)
    * [`ibmcloud ks ingress status-report ignore ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_ignore_ls)
    * [`ibmcloud ks ingress status-report ignore rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_status_report_ignore_rm)
    

## ibmcloud ks logging
{: #icks_map_logging}

[Forward logs from your cluster.](/docs/containers?topic=containers-kubernetes-service-cli#logging_commands).
{: shortdesc}

* **`logging autoupdate`**: Manage automatic updates of the Fluentd add-on in a cluster.
    * [`ibmcloud ks logging autoupdate disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_autoupdate_disable)
    * [`ibmcloud ks logging autoupdate enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_autoupdate_enable)
    * [`ibmcloud ks logging autoupdate get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_autoupdate_get)
* **`logging config`**: View or modify log forwarding configurations for a cluster.
    * [`ibmcloud ks logging config create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_logging_create)
    * [`ibmcloud ks logging config get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_logging_get)
    * [`ibmcloud ks logging config rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_logging_rm)
    * [`ibmcloud ks logging config update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_logging_update)
* **`logging filter`**: View or modify log filters for a cluster.
    * [`ibmcloud ks logging filter create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_filter_create)
    * [`ibmcloud ks logging filter get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_filter_view)
    * [`ibmcloud ks logging filter rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_filter_delete)
    * [`ibmcloud ks logging filter update`](/docs/containers?topic=containers-kubernetes-service-cli#cs_log_filter_update)
* [`ibmcloud ks logging refresh`](/docs/containers?topic=containers-kubernetes-service-cli#cs_logging_refresh)

## ibmcloud ks nlb-dns
{: #icks_map_nlb-dns}

[Create and manage host names for network load balancer (NLB) IP addresses in a cluster and health check monitors for host names](/docs/containers?topic=containers-kubernetes-service-cli#nlb-dns).
{: shortdesc}

* [`ibmcloud ks nlb-dns add`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-add)
* **`nlb-dns create`**: Create a DNS host name.
    * [`ibmcloud ks nlb-dns create classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-create)
    * [`ibmcloud ks nlb-dns create vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-create-vpc-gen2)
* [`ibmcloud ks nlb-dns ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-ls)
* [`ibmcloud ks nlb-dns get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-get)
* **`nlb-dns monitor`**: Create and manage health check monitors for network load balancer (NLB) IP addresses and host names in a cluster.
    * [`ibmcloud ks nlb-dns monitor configure`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-configure)
    * [`ibmcloud ks nlb-dns monitor disable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-disable)
    * [`ibmcloud ks nlb-dns monitor enable`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-enable)
    * [`ibmcloud ks nlb-dns monitor get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-get)
    * [`ibmcloud ks nlb-dns monitor ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-monitor-ls)
* [`ibmcloud ks nlb-dns replace`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-replace)
* **`nlb-dns rm`**: Create and manage health check monitors for network load balancer (NLB) IP addresses and host names in a cluster.
    * [`ibmcloud ks nlb-dns rm classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-rm)
    * [`ibmcloud ks nlb-dns rm vpc-gen2`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-rm-vpc-gen2)
* **Beta** **`nlb-dns secret`**:  Manage the secret for an NLB subdomain.
    * [`ibmcloud ks nlb-dns secret regenerate`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-secret-regenerate)
    * [`ibmcloud ks nlb-dns secret rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_nlb-dns-secret-rm)

## ibmcloud ks webhook-create
{: #icks_map_webhook-create}

[Register a webhook in a cluster](/docs/containers?topic=containers-kubernetes-service-cli#cs_webhook_create).
{: shortdesc}

## ibmcloud ks api-key 
{: #icks_map_api-key}

[View information about the API key for a cluster or reset it to a new key](/docs/containers?topic=containers-kubernetes-service-cli#api_key-commands).
{: shortdesc}

* [`ibmcloud ks api-key info`](/docs/containers?topic=containers-kubernetes-service-cli#cs_api_key_info)
* [`ibmcloud ks api-key reset`](/docs/containers?topic=containers-kubernetes-service-cli#cs_api_key_reset)

## ibmcloud ks credential
{: #icks_map_credential}

[Set and unset credentials that allow you to access the IBM Cloud classic infrastructure portfolio through your IBM Cloud account](/docs/containers?topic=containers-kubernetes-service-cli#credential).
{: shortdesc}

* [`ibmcloud ks credential get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_credential_get)
* [`ibmcloud ks credential set classic`](/docs/containers?topic=containers-kubernetes-service-cli#cs_credentials_set)
* [`ibmcloud ks credential unset`](/docs/containers?topic=containers-kubernetes-service-cli#cs_credentials_unset)

## ibmcloud ks infra-permissions
{: #icks_map_infra-permissions}

[View information about infrastructure permissions that allow you to access the IBM Cloud classic infrastructure portfolio through your IBM Cloud account](/docs/containers?topic=containers-kubernetes-service-cli#infra-commands).
{: shortdesc}

* [`ibmcloud ks infra-permissions get`](/docs/containers?topic=containers-kubernetes-service-cli#infra_permissions_get)

## ibmcloud ks kms 
{: #icks_map_kms}

[View and configure Key Management Service integrations](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms).
{: shortdesc}

* **`kms crk`**: List and configure the root keys for a Key Management Service instance.
    * [`ibmcloud ks kms crk ls`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_crk_ls)
* [`ibmcloud ks kms enable`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_enable)
* **`kms instance`**: View and configure available Key Management Service instances.
    * [`ibmcloud ks kms instance ls`](/docs/containers?topic=containers-kubernetes-service-cli#ks_kms_instance_ls)

## ibmcloud ks quota 
{: #icks_map_quota}

[View the quota and limits for cluster-related resources in your IBM Cloud account](/docs/containers?topic=containers-kubernetes-service-cli#cs_quota).

* [`ibmcloud ks quota ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_quota_ls)

## ibmcloud ks subnets 
{: #icks_map_subnets}

[List available portable subnets in your IBM Cloud infrastructure account](/docs/containers?topic=containers-kubernetes-service-cli#cs_subnets).
{: shortdesc}

## ibmcloud ks vlan 
{: #icks_map_vlan}

[List public and private VLANs for a zone and view the VLAN spanning status](/docs/containers?topic=containers-kubernetes-service-cli#vlan).
{: shortdesc}

* [`ibmcloud ks vlan ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_vlans)
* **`vlan spanning`**: View the VLAN spanning status for your IBM Cloud classic infrastructure account.
    * [`ibmcloud ks vlan spanning get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_vlan_spanning_get)
    
## ibmcloud ks vpcs 
{: #icks_map_vpcs}

[List all VPCs in the targeted resource group. If no resource group is targeted, then all VPCs in the account are listed.](/docs/containers?topic=containers-kubernetes-service-cli#vpc-ls-cli).
{: shortdesc}

## ibmcloud ks flavors
{: #icks_map_flavors}

[List available flavors for a zone](/docs/containers?topic=containers-kubernetes-service-cli#cs_machine_types).
{: shortdesc}

## ibmcloud ks locations
{: #icks_map_locations}

[List supported IBM Cloud Kubernetes Service locations](/docs/containers?topic=containers-kubernetes-service-cli#cs_supported-locations).
{: shortdesc}

## ibmcloud ks messages
{: #icks_map_messages}

[View the current user messages](/docs/containers?topic=containers-kubernetes-service-cli#cs_messages).
{: shortdesc}

## ibmcloud ks versions
{: #icks_map_versions}

[List all the container platform versions that are available for IBM Cloud Kubernetes Service clusters](/docs/containers?topic=containers-kubernetes-service-cli#cs_versions_command).
{: shortdesc}

## ibmcloud ks api
{: #icks_map_api}

**Deprecated** [View or set the API endpoint and API version for the service](/docs/containers?topic=containers-kubernetes-service-cli#cs_cli_api).
{: shortdesc}

## ibmcloud ks `init`
{: #icks_map_init}

[Initialize the Kubernetes Service plug-in and get authentication tokens](/docs/containers?topic=containers-kubernetes-service-cli#cs_init).
{: shortdesc}

## ibmcloud ks script  
{: #icks_map_script}

[Rewrite scripts that call IBM Cloud Kubernetes Service plug-in commands](/docs/containers?topic=containers-kubernetes-service-cli#script).
{: shortdesc}

* [`ibmcloud ks script update`](/docs/containers?topic=containers-kubernetes-service-cli#script_update)




## ibmcloud ks security-group
{: #icks_map_security_group}

[Reset or sync security group settings](/docs/containers?topic=containers-kubernetes-service-cli#security_group)

* [`ibmcloud ks security-group reset`](/docs/containers?topic=containers-kubernetes-service-cli#security_group_reset)
* [`ibmcloud ks security-group sync`](/docs/containers?topic=containers-kubernetes-service-cli#security_group_sync)



## ibmcloud ks storage 
{: #icks_map_storage}

**Beta** [View and modify storage resources](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage).
{: shortdesc}

* **`storage attachment`**: View and modify storage volume attachments of worker nodes in your cluster.
    * [`ibmcloud ks storage attachment create`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_cr)
    * [`ibmcloud ks storage attachment get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_get)
    * [`ibmcloud ks storage attachment ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_ls)
    * [`ibmcloud ks storage attachment rm`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_rm)
* **`storage volume`**: View a list of storage volumes.
    * [`ibmcloud ks storage volume get`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_ls_c)
    * [`ibmcloud ks storage volume ls`](/docs/containers?topic=containers-kubernetes-service-cli#cs_storage_att_ls_2)
    
    
