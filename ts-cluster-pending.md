---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Why does my cluster stay in a pending state?
{: #cs_cluster_pending}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}


When you deploy your cluster, it remains in a pending state and doesn't start.
{: tsSymptoms}


If you just created the cluster, the worker nodes might still be configuring. If you already wait for a while, you might have an invalid VLAN.
{: tsCauses}



You can try one of the following solutions:
{: tsResolve}

- Check the status of your cluster by running `ibmcloud ks cluster ls`. Then, check to be sure that your worker nodes are deployed by running `ibmcloud ks worker ls --cluster <cluster_name>`.

- Check to see whether your VLAN is valid. To be valid, a VLAN must be associated with infrastructure that can host a worker with local disk storage. You can [list your VLANs](/docs/containers?topic=containers-kubernetes-service-cli#cs_vlans) by running `ibmcloud ks vlan ls --zone <zone>` if the VLAN does not show in the list, then it is not valid. Choose a different VLAN.


If the issue persists, contact support. Open a [support case](/docs/get-support?topic=get-support-using-avatar). In the case details, be sure to include any relevant log files, error messages, or command outputs.



