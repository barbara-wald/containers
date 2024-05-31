---

copyright:
  years: 2022, 2024
lastupdated: "2024-05-29"


keywords: containers, ingress, troubleshoot ingress, errahcf

subcollection: containers
content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}



# Why does the Ingress status show an `ERRAHCF` error?
{: #ts-ingress-errahcf}
{: troubleshoot}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}

You can use the `ibmcloud ks ingress status-report ignored-errors add` command to add an error to the ignored-errors list. Ignored errors still appear in the output of the `ibmcloud ks ingress status-report get` command, but are ignored when calculating the overall Ingress Status.
{: tip}

When you check the status of your cluster's Ingress components by running the `ibmcloud ks ingress status-report get` command, you see an error similar to the following example.
{: tsSymptoms}

```sh
The ALB is unable to respond to health requests (ERRAHCF).
```
{: screen}

{{site.data.keyword.containerlong_notm}} deploys an application into your cluster that checks whether your ALBs can respond to HTTPS requests. The application reports problems getting replies from one or more ALBs on your cluster.
{: tsCauses}

Review your access control lists to make sure that health traffic is allowed.
{: tsResolve}

1. List your cluster ALBs using the following command. 

    ```sh
    ibmcloud ks ingress alb ls
    ```
    {: pre}

1. Make a note of the load balancer address.
    - **VPC clusters**: Make a note of the address in the `Load Balancer Hostname` column.
    - **Classic clusters**: Make a note of the address in the `ALB IP` column.

1. Get your cluster details running the following command. Make a note of your Ingress subdomain.
    ```sh
    ibmcloud ks cluster get
    ```
    {: pre }
    

1. Check that the ALB responds to health requests by running the following command. Enter the load balancer address and Ingress subdomain that you retrieved earlier.
    ```sh
    curl -k https://LOAD-BALANCER-ADDRESS -H "Host: albhealth.INGRESS-SUBDOMAIN"
    ```
    {: pre}

1. Ensure that no firewall rules or access control lists are blocking communication between the health checker application and your ALBs.
    - **VPC clusters**:
        - Health check traffic originates from one of the worker nodes of your cluster. In the case of public ALBs, the traffic is directed to the public floating IP address of the VPC Load Balancer instance, therefore it is required to have a Public Gateway attached to all the worker subnets. In the case of private ALBs, the traffic is directed to the VPC subnet IP address of the VPC Load Balancer, therefore a Public Gateway is not required.
        - If your VPC Load Balancers are located on a subnet other than the worker nodes of your cluster, you must update the Security Group attached to the VPC Load Balancer subnet to allow incoming traffic from the worker subnets.
        - For more information, see [Controlling traffic with VPC security groups](/docs/containers?topic=containers-vpc-security-group).
    - **Classic clusters**:
        - Make sure you enabled [Virtual Router Forwarding (VRF)](/docs/account?topic=account-vrf-service-endpoint&interface=ui) in your account. Health check traffic does not leave the cluster but might be sent from one node to another. Ensure your network policies do not block this traffic.
        - For more information, see [Controlling traffic with network policies on classic clusters](/docs/containers?topic=containers-network_policies). 

1. Wait 10-15 minutes to see if the issue is resolved.

1. If the issue persists, contact support. Open a [support case](/docs/get-support?topic=get-support-using-avatar). In the case details, be sure to include any relevant log files, error messages, or command outputs.

If you don't want to use the ALB health check, you can remove the health checker application using running the **`ibmcloud ks ingress alb health-checker disable`** [command](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_healthchecker_disable).
{: tip}

