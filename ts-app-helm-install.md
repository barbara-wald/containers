---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Why can't I install a Helm chart with updated configuration values?
{: #ts-app-helm-install}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}


When you try to install an updated Helm chart by running `helm install <release_name> <helm_repo>/<chart_name> -f config.yaml`, you get the following error message.
{: tsSymptoms}

```sh
Error: failed to download "<helm_repo>/<chart_name>"
```
{: screen}


You might need to update your Helm installation because of the following reasons:
{: tsCauses}

* The URL to the {{site.data.keyword.cloud_notm}} Helm repository that is configured on your local machine might be incorrect.
* The name of your local Helm repository might not match the Helm repository name or URL of the installation command that you copied from the Helm chart instructions.
* The Helm chart that you want to install does not support the version of Helm that you installed on your local machine.
* Your cluster network setup changed from public access to private-only access, but Helm was not updated.


To troubleshoot your Helm chart:
{: tsResolve}

1. List the {{site.data.keyword.cloud_notm}} Helm repositories currently available in your Helm instance.
    ```sh
    helm repo list
    ```
    {: pre}

2. Remove the {{site.data.keyword.cloud_notm}} Helm repositories.
    ```sh
    helm repo remove <helm_repo>
    ```
    {: pre}

3. Reinstall the Helm version that matches a supported version of the Helm chart that you want to install. As part of the installation, add and update the {{site.data.keyword.cloud_notm}} Helm repositories. For more information, see [Installing Helm v3 in your cluster](/docs/containers?topic=containers-helm#install_v3).

Now, you can follow the instructions in the Helm chart `README` to install the Helm chart in your cluster.








