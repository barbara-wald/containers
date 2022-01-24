---

copyright: 
  years: 2014, 2022
lastupdated: "2022-01-11"

keywords: kubernetes, help, network, connectivity

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}


# Classic: Why is the bare metal instance ID inconsistent with worker records?
{: #bm_machine_id}

**Infrastructure provider**: ![Classic infrastructure provider icon.](images/icon-classic-2.svg) Classic


When you use `ibmcloud ks worker` commands with your bare metal worker node, you see a message similar to the following.
{: tsSymptoms}

```
The worker node instance ID changed. Reload the worker node if bare metal hardware was serviced.
```
{: screen}


The machine ID can become inconsistent with the {{site.data.keyword.containerlong_notm}} worker record when the machine experiences hardware issues. When IBM Cloud infrastructure resolves this issue, a component can change within the system that the service does not identify.
{: tsCauses}


For {{site.data.keyword.containerlong_notm}} to re-identify the machine, [reload the bare metal worker node](/docs/containers?topic=containers-kubernetes-service-cli#cs_worker_reload). Note that reloading also updates the machine's [patch version](/docs/containers?topic=containers-changelog).
{: tsResolve}

You can also [delete the bare metal worker node](/docs/containers?topic=containers-kubernetes-service-cli#cs_cluster_rm). Remember that bare metal instances are billed monthly.





