---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: containers, {{site.data.keyword.containerlong_notm}}, clusters, worker nodes, worker pools

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}



# Preparing your account to create clusters
{: #clusters}

Complete the following steps to prepare your account for creating {{site.data.keyword.containerlong_notm}} clusters.
{: shortdesc}

After the account administrator makes these preparations, you might not need to change them each time that you create a cluster. However, each time that you create a cluster, you still want to verify that the current account-level state is what you need it to be.


## Create or upgrade your account
{: #prepare-create-account}
{: step}

[Create or upgrade your account to a billable account ({{site.data.keyword.cloud_notm}} Pay-As-You-Go or Subscription)](https://cloud.ibm.com/registration).{: #cluster_prepare}


## Setting user permissions
{: #prepare-verify-permissions}
{: step}

Confirm that you [have the required permissions to create clusters](/docs/containers?topic=containers-iam-platform-access-roles). Make sure that your account administrator does not assign you the **Administrator** platform access role at the same time as scoping the access policy to a namespace.



## Plan your resource groups
{: #prepare-resource-groups}
{: step}

If your account uses multiple resource groups, figure out your account's strategy for [managing resource groups](/docs/containers?topic=containers-iam-platform-access-roles). You might want one resource group and create all clusters within that one. You might want to set up different resource groups to group different environments or resource types.


Keep in mind:
    * To create a cluster in a different resource group than the default, you need at least the **Viewer** role for the resource group. If you don't have any role for the resource group, your cluster is created in the default resource group.


## Cluster-specific account setup
{: #prepare-cluster-account}
{: step}

If you know what kind of cluster you need already, you can start thinking about what kind of cluster-specific setup tasks you might complete. If you don't know what kind of cluster you need yet, no worries! You can make these decisions later.

1. **Classic clusters only**: Consider [creating a reservation](/docs/containers?topic=containers-reservations) to lock in a discount over 1 or 3 year terms for your worker nodes. After you create the cluster, add worker pools that use the reserved instances. Typical savings range between 30-50% compared to regular worker node costs.

1.  Set up your IBM Cloud infrastructure networking to allow worker-to-master and user-to-master communication. Your cluster network setup varies with the infrastructure provider that you choose (classic or VPC).
    * **VPC clusters only**: Your VPC clusters are created with a public and a private cloud service endpoint by default. **Optional**: If you want your VPC clusters to communicate with classic clusters over the private network interface, you can choose to set up classic infrastructure access from the VPC that your cluster is in. Note that you can set up classic infrastructure access for only one VPC per region and [Virtual Routing and Forwarding (VRF)](/docs/account?topic=account-vrf-service-endpoint&interface=ui) is required in your {{site.data.keyword.cloud_notm}} account. For more information, see [Setting up access to your Classic Infrastructure from VPC](/docs/vpc?topic=vpc-setting-up-access-to-classic-infrastructure).

    * **Classic clusters only, VRF and service endpoint enabled accounts**: You must set up your account to use VRF and service endpoints to support scenarios such as running internet-facing workloads and extending your on-premises data center. After you set up the account, your VPC and classic clusters are created with a public and a private cloud service endpoint by default.
        1. Enable [VRF](/docs/account?topic=account-vrf-service-endpoint&interface=ui) in your IBM Cloud infrastructure account. To check whether a VRF is already enabled, use the `ibmcloud account show` command.
        2. [Enable your {{site.data.keyword.cloud_notm}} account to use service endpoints](/docs/account?topic=account-vrf-service-endpoint#service-endpoint).

    * **Classic clusters only, Non-VRF and non-service endpoint accounts**: If you don't set up your account to use VRF and service endpoints, you can create only classic clusters that use VLAN spanning to communicate with each other on the public and private network.
        * To use the public cloud service endpoint only (run internet-facing workloads), enable [VLAN spanning](/docs/vlans?topic=vlans-vlan-spanning#vlan-spanning) for your IBM Cloud infrastructure account so that your worker nodes can communicate with each other on the private network. To perform this action, you need the **Network > Manage Network VLAN Spanning** [infrastructure permission](/docs/containers?topic=containers-access-creds), or you can request the account owner to enable it. To check whether VLAN spanning is already enabled, use the `ibmcloud ks vlan spanning get --region <region>` [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_vlan_spanning_get).
        * To use a gateway appliance (extend your on-premises data center), enable [VLAN spanning](/docs/vlans?topic=vlans-vlan-spanning#vlan-spanning) for your IBM Cloud infrastructure account so that your worker nodes can communicate with each other on the private network. To perform this action, you need the **Network > Manage Network VLAN Spanning** [infrastructure permission](/docs/containers?topic=containers-access-creds), or you can request the account owner to enable it. To check whether VLAN spanning is already enabled, use the `ibmcloud ks vlan spanning get --region <region>` [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_vlan_spanning_get).
            1. Configure a gateway appliance to connect your cluster to the on-premises network. For example, you might choose to set up a [Virtual Router Appliance](/docs/virtual-router-appliance?topic=virtual-router-appliance-about-the-vra) to act as your firewall to allow required network traffic and to block unwanted network traffic.
            2. [Open up the required private IP addresses and ports](/docs/containers?topic=containers-firewall#firewall_outbound) for each region so that the master and the worker nodes can communicate and for the {{site.data.keyword.cloud_notm}} services that you plan to use.


## Next steps
{: #next-steps}
{: step}

[Set up an API key for {{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-access-creds) in the region and resource groups where you want to create clusters. 



