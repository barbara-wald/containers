---

copyright:
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: kubernetes

subcollection: containers

content-type: tutorial
services: containers, vpc
account-plan: paid
completion-time: 60m

---

{{site.data.keyword.attribute-definition-list}}





# Setting up your first cluster in your Virtual Private Cloud (VPC)
{: #vpc_ks_tutorial}
{: toc-content-type="tutorial"}
{: toc-services="containers, vpc"}
{: toc-completion-time="60m"}

Create an {{site.data.keyword.containerlong}} cluster in your Virtual Private Cloud (VPC).
{: shortdesc}

With **{{site.data.keyword.containerlong_notm}} clusters on VPC**, you can create your cluster in the next generation of the {{site.data.keyword.cloud_notm}} platform, in your [Virtual Private Cloud](/docs/vpc?topic=vpc-about-vpc). VPC gives you the security of a private cloud environment with the dynamic scalability of a public cloud. VPC uses the next version of {{site.data.keyword.containerlong_notm}} [infrastructure providers](/docs/containers?topic=containers-overview), with a select group of v2 API, CLI, and console functionality. You can create only standard clusters for VPC.

## Audience
{: #vpc_ks_audience}

This tutorial is for administrators who are creating a cluster in {{site.data.keyword.containerlong_notm}} in VPC for the first time.
{: shortdesc}

## Objectives
{: #vpc_ks_objectives}

In the tutorial lessons, you create an {{site.data.keyword.containerlong_notm}} cluster in a Virtual Private Cloud (VPC). Then, you deploy an app and expose the app publicly by using a load balancer.

## What you'll get
{: #vpc_rh_get}

In this tutorial, you create the following resources. There are optional steps to delete these resources if you do not want to keep them after completing the tutorial. 

- A VPC cluster
- A simple Hello World app deployed to your cluster
- A VPC load balancer to expose your app

## Prerequisites
{: #vpc_ks_prereqs}

Complete the following prerequisite steps to set up permissions and the command-line environment.
{: shortdesc}

Permissions
:   If you are the account owner, you already have the required permissions to create a cluster and can continue to the next step. Otherwise, ask the account owner to [set up the API key and assign you the minimum user permissions in {{site.data.keyword.cloud_notm}} IAM](/docs/containers?topic=containers-iam-platform-access-roles).

Command-line tools
:   For quick access to your resources from the command line, try the [{{site.data.keyword.cloud-shell_notm}}](https://cloud.ibm.com/shell){: external}. Otherwise, set up your local command-line environment by completing the following steps.

1. [Install the {{site.data.keyword.cloud_notm}} CLI (`ibmcloud`), {{site.data.keyword.containershort_notm}} plug-in (`ibmcloud ks`), and {{site.data.keyword.registrylong_notm}} plug-in (`ibmcloud cr`)](/docs/containers?topic=containers-cli-install).
2. [Install the {{site.data.keyword.redhat_openshift_notm}} (`oc`) and Kubernetes (`kubectl`) CLIs](/docs/containers?topic=containers-cli-install).
3. To work with VPC, install the `infrastructure-service` plug-in. The prefix for running commands is `ibmcloud is`.
    ```sh
    ibmcloud plugin install infrastructure-service
    ```
    {: pre}

4. Update your {{site.data.keyword.containershort_notm}} plug-in to the latest version.
    ```sh
    ibmcloud plugin update kubernetes-service
    ```
    {: pre}

5. Make sure that the [`kubectl` version](/docs/containers?topic=containers-cli-install) matches the Kubernetes version of your VPC cluster. This tutorial creates a cluster that runs version **1.29**.


## Create a cluster in VPC
{: #vpc_ks_create_vpc_cluster}
{: step}

Create an {{site.data.keyword.containerlong_notm}} cluster in your {{site.data.keyword.cloud_notm}} Virtual Private Cloud (VPC) environment. For more information about VPC, see [Getting Started with Virtual Private Cloud](/docs/vpc?topic=vpc-getting-started).
{: shortdesc}

1. Log in to the account, resource group, and {{site.data.keyword.cloud_notm}} region where you want to create your VPC environment. The VPC must be set up in the same multizone metro location where you want to create your cluster. In this tutorial you create a VPC in `us-south`. For other supported regions, see [Multizone metros for VPC clusters](/docs/containers?topic=containers-regions-and-zones#zones-vpc). If you have a federated ID, include the `--sso` option.
    ```sh
    ibmcloud login -r us-south [-g <resource_group>] [--sso]
    ```
    {: pre}

2. Create a VPC for your cluster. For more information, see the docs for creating a VPC in the [console](/docs/vpc?topic=vpc-creating-a-vpc-using-the-ibm-cloud-console) or [CLI](/docs/vpc?topic=vpc-creating-vpc-resources-with-cli-and-api&interface=cli#create-a-vpc-cli).
    1. Create a VPC called `myvpc` and note the **ID** in the output. VPCs provide an isolated environment for your workloads to run within the public cloud. You can use the same VPC for multiple clusters, such as if you plan to have different clusters host separate microservices that need to communicate with each other. If you want to separate your clusters, such as for different departments, you can create a VPC for each cluster.
        ```sh
        ibmcloud is vpc-create myvpc
        ```
        {: pre}

    2. Create a subnet for your VPC, and note its **ID**. Consider the following information when you create the VPC subnet:
        - **Zones**: You must have one VPC subnet for each zone in your cluster. The available zones depend on the metro location that you created the VPC in. To list available zones in the region, run `ibmcloud is zones`.
        - **IP addresses**: VPC subnets provide private IP addresses for your worker nodes and load balancer services in your cluster, so make sure to [create a subnet with enough IP addresses](/docs/containers?topic=containers-vpc-subnets#vpc_basics_subnets), such as 256. You can't change the number of IP addresses that a VPC subnet has later.
        - **Public gateways**: You don't need to attach a public gateway to complete this tutorial. Instead, you can keep your worker nodes isolated from public access by using VPC load balancers to expose workloads securely. You might attach a public gateway if your worker nodes need to access a public URL.

        ```sh
        ibmcloud is subnet-create mysubnet1 <vpc_ID> --zone us-south-1 --ipv4-address-count 256
        ```
        {: pre}

3. Create a cluster in your VPC in the same zone as the subnet. By default, your cluster is created with a public and a private cloud service endpoint. You can use the public cloud service endpoint to access the Kubernetes master, such as to run `kubectl` commands, from your local machine. Your worker nodes can communicate with the master on the private cloud service endpoint. For more information about the command options, see the [`cluster create vpc-gen2` CLI reference docs](/docs/containers?topic=containers-kubernetes-service-cli#cli_cluster-create-vpc-gen2).
    ```sh
    ibmcloud ks cluster create vpc-gen2 --name myvpc-cluster --zone us-south-1 --version 1.29 --flavor bx2.2x8 --workers 1 --vpc-id <vpc_ID> --subnet-id <vpc_subnet_ID>
    ```
    {: pre}

4. Check the state of your cluster. The cluster might take a few minutes to provision.
    1. Verify that the cluster **State** is **normal**.
        ```sh
        ibmcloud ks cluster ls --provider vpc-gen2
        ```
        {: pre}

    2. Download the Kubernetes configuration files.
        ```sh
        ibmcloud ks cluster config --cluster myvpc-cluster
        ```
        {: pre}

    3. Verify that the `kubectl` commands run properly with your cluster by checking the Kubernetes CLI server version.
        ```sh
        kubectl version  --short
        ```
        {: pre}

        Example output
        ```sh
        Client Version: 1.29
        Server Version: 1.29+IKS
        ```
        {: screen}



## Deploy a privately available app
{: #vpc_ks_app}
{: step}

Create a Kubernetes deployment to deploy a single app instance as a pod to your worker node in your VPC cluster.
{: shortdesc}

1. Clone the source code for the [Hello world app](https://github.com/IBM/container-service-getting-started-wt){: external} to your user home directory. The repository contains different versions of a similar app in folders that each start with `Lab`. Each version contains the following files:
    * `Dockerfile`: The build definitions for the image.
    * `app.js`: The Hello world app.
    * `package.json`: Metadata about the app.

    ```sh
    git clone https://github.com/IBM/container-service-getting-started-wt.git
    ```
    {: pre}

1. Go to the `Lab 1` directory.

    ```sh
    cd 'container-service-getting-started-wt/Lab 1'
    ```
    {: pre}

1. Use an existing registry namespace or create one, such as `vpc-gen2`.
    ```sh
    ibmcloud cr namespace-list
    ```
    {: pre}

    ```sh
    ibmcloud cr namespace-add vpc-gen2
    ```
    {: pre}

1. Build a Docker image that includes the app files of the `Lab 1` directory.

    Use lowercase alphanumeric characters or underscores (`_`) only in the image name. Don't forget the period (`.`) at the end of the command. The period tells Docker to look inside the current directory for the Dockerfile and build artifacts to build the image.

    ```sh
    docker build -t us.icr.io/<namespace>/hello-world:1
    ```
    {: pre}

    When the build is complete, verify that you see the following success message:

    ```sh
    => exporting to image                                                                           0.0s
    => => exporting layers                                                                          0.0s
    => => writing image sha256:3ca1eb1d0998f738b552d4c435329edf731fe59e427555b78ba2fb54f2017906     0.0s
    => => naming to <region>.icr.io/<namespace>/hello-world:1                                       0.0s
    ```
    {: screen}

1. Push the image to the {{site.data.keyword.registrylong_notm}} namespace that you created. If you need to change the app in the future, repeat these steps to create another version of the image. **Note**: Learn more about [securing your personal information](/docs/containers?topic=containers-security#pi) when you work with container images.

    ```sh
    docker push us.icr.io/<namespace>/hello-world:1 .
    ```
    {: pre}
    

1. Create a deployment for your app. Deployments are used to manage pods, which include containerized instances of an app. The following command deploys the app in a single pod. For the purposes of this tutorial, the deployment is named **hello-world-deployment**, but you can give the deployment any name that you want.

    ```sh
    kubectl create deployment hello-world-deployment --image=us.icr.io/vpc-gen2/hello-world:1
    ```
    {: pre}

    Example output

    ```sh
    deployment.apps/hello-world-deployment created
    ```
    {: screen}

    Learn more about [securing your personal information](/docs/containers?topic=containers-security#pi) when you work with Kubernetes resources.

1. Make the app accessible by exposing the deployment as a NodePort service. Because your VPC worker nodes are connected to a private subnet only, the NodePort is assigned only a private IP address and is not exposed on the public network. Other services that run on the private network can access your app by using the private IP address of the NodePort service.

    ```sh
    kubectl expose deployment/hello-world-deployment --type=NodePort --name=hello-world-service --port=8080 --target-port=8080
    ```
    {: pre}

    Example output

    ```sh
    service/hello-world-service exposed
    ```
    {: screen}
    
    | Parameter             | Description   | 
    |--------------------|------------------|
    | `expose` | Expose a Kubernetes resource, such as a deployment, as a Kubernetes service so that users can access the resource by using the IP address of the service. | 
    | `deployment/*<hello-world-deployment>*` | The resource type and the name of the resource to expose with this service. |
    | `--name=*<hello-world-service>*` | The name of the service. |
    | `--type=NodePort` | The service type to create. In this lesson, you create a `NodePort` service. In the following lesson, you create a `LoadBalancer` service. |
    | `--port=*<8080>*` | The port on which the service listens for external network traffic. |
    | `--target-port=*<8080>*` | The port that your app listens on and to which the service directs incoming network traffic. In this example, the `target-port` is the same as the `port`, but other apps that you create might use a different port. |
    {: caption="Table 1. Information about the command options." caption-side="bottom"}

1. Now that all the deployment work is done, you can test your app from within the cluster. Get the details to form the private IP address that you can use to access your app.
    1. Get information about the service to see which NodePort was assigned. The NodePorts are randomly assigned when they are generated with the `expose` command, but within 30000-32767. In this example, the **NodePort** is 30872.

        ```sh
        kubectl describe service hello-world-service
        ```
        {: pre}

        Example output

        ```sh
        NAME:                   hello-world-service
        Namespace:              default
        Labels:                 run=hello-world-deployment
        Selector:               run=hello-world-deployment
        Type:                   NodePort
        IP:                     10.xxx.xx.xxx
        Port:                   <unset> 8080/TCP
        NodePort:               <unset> 30872/TCP
        Endpoints:              172.30.xxx.xxx:8080
        Session Affinity:       None
        No events.
        ```
        {: screen}

    2. List the pods that run your app, and note the pod name.
        ```sh
        kubectl get pods
        ```
        {: pre}

        Example output
        ```sh
        NAME                                     READY     STATUS        RESTARTS   AGE
        hello-world-deployment-d99cddb45-lmj2v   1/1       Running       0          2d
        ```
        {: screen}

    3. Describe your pod to find out what worker node the pod is running on. In the example output, the worker node that the pod runs on is **10.xxx.xx.xxx**.
        ```sh
        kubectl describe pod hello-world-deployment-d99cddb45-lmj2v
        ```
        {: pre}

        Example output
        
        ```sh
        NAME:               hello-world-deployment-d99cddb45-lmj2v
        Namespace:          default
        Priority:           0
        PriorityClassName:  <none>
        Node:               10.xxx.xx.xxx/10.xxx.xx.xxx
        Start Time:         Mon, 22 Apr 20122 12:40:48 -0400
        Labels:             pod-template-hash=d99cddb45
                            run=hello-world-deployment
        Annotations:        kubernetes.io/psp=ibm-privileged-psp
        Status:             Running
        IP:                 172.30.xxx.xxx
        ...
        ```
        {: screen}

1. Log in to the pod so that you can make a request to your app from within the cluster.
    ```sh
    kubectl exec -it hello-world-deployment-d99cddb45-lmj2v /bin/sh
    ```
    {: pre}

1. Make a request to the NodePort service by using the worker node private IP address and the node port that you previously retrieved.
    ```sh
    wget -O - 10.xxx.xx.xxx:30872
    ```
    {: pre}

    Example output
    ```sh
    Connecting to 10.xxx.xx.xxx:30872 (10.xxx.xx.xxx:30872)
    Hello world from hello-world-deployment-d99cddb45-lmj2v! Your app is up and running in a cluster!
    -                    100% |*****************************************************************************************|    88   0:00:00 ETA
    ```
    {: screen}

    To close your pod session, enter `exit`.


## Set up a Load Balancer for VPC to expose your app publicly
{: #vpc_ks_vpc_lb}
{: step}

Set up a VPC load balancer to expose your app on the public network.
{: shortdesc}

When you create a Kubernetes `LoadBalancer` service in your cluster, a load balancer for VPC is automatically created in your VPC outside of your cluster. The load balancer is multizonal and routes requests for your app through the private NodePorts that are automatically opened on your worker nodes. The following diagram illustrates how a user accesses an app's service through the load balancer, even though your worker node is connected to only a private subnet.

![VPC load balancing for a cluster.](/images/vpc-alb-mz.svg "VPC load balancing for a cluster"){: caption="Figure 1. VPC load balancing for a cluster" caption-side="bottom"}

1. Create a Kubernetes `LoadBalancer` service in your cluster to publicly expose the hello world app.
    ```sh
    kubectl expose deployment/hello-world-deployment --type=LoadBalancer --name=hw-lb-svc  --port=8080 --target-port=8080
    ```
    {: pre}

    Example output

    ```sh
    service "hw-lb-svc" exposed
    ```
    {: screen}
    
    | Parameter             | Description   | 
    |--------------------|------------------|
    | `expose` | Expose a Kubernetes resource, such as a deployment, as a Kubernetes service so that users can access the resource by using the IP address of the service. | 
    | `deployment/*<hello-world-deployment>*` | The resource type and the name of the resource to expose with this service. |
    | `--name=*<hello-world-service>*` | The name of the service. |
    | `--type=LoadBalancer` | The Kubernetes service type to create. In this lesson, you create a `LoadBalancer` service. |
    | `--port=*<8080>*` | The port on which the service listens for external network traffic. |
    | `--target-port=*<8080>*` | The port that your app listens on and to which the service directs incoming network traffic. In this example, the `target-port` is the same as the `port`, but other apps that you create might use a different port. |
    {: caption="Table 2. Information about the command options." caption-side="bottom"}

2. Verify that the Kubernetes `LoadBalancer` service is created successfully in your cluster. When you create the Kubernetes `LoadBalancer` service, a VPC load balancer is automatically created for you. The VPC load balancer assigns a hostname to your Kubernetes LoadBalancer service that you can see in the **LoadBalancer Ingress** field of your CLI output. The VPC load balancer takes a few minutes to provision in your VPC. Until the VPC load balancer is ready, you can't access the Kubernetes `LoadBalancer` service through its hostname.

    ```sh
    kubectl describe service hw-lb-svc
    ```
    {: pre}

    **Example CLI output**
    ```sh
    NAME:                     hw-lb-svc
    Namespace:                default
    Labels:                   app=hello-world-deployment
    Annotations:              <none>
    Selector:                 app=hello-world-deployment
    Type:                     LoadBalancer
    IP:                       172.21.xxx.xxx
    LoadBalancer Ingress:     1234abcd-us-south.lb.appdomain.cloud
    Port:                     <unset> 8080/TCP
    TargetPort:               8080/TCP
    NodePort:                 <unset> 32040/TCP
    Endpoints:
    Session Affinity:         None
    External Traffic Policy:  Cluster
    Events:
        Type    Reason                Age   From                Message
        ----    ------                ----  ----                -------
        Normal  EnsuringLoadBalancer  1m    service-controller  Ensuring load balancer
        Normal  EnsuredLoadBalancer   1m    service-controller  Ensured load balancer
    ```
    {: screen}

3. Verify that the VPC load balancer is created successfully in your VPC. In the output, verify that the VPC load balancer has a **Provision Status** of `active` and an **Operating Status** of `online`.

    The VPC load balancer is named in the format `kube-<cluster_ID>-<kubernetes_lb_service_UID>`. To see your cluster ID, run `ibmcloud ks cluster get --cluster <cluster_name>`. To see the Kubernetes `LoadBalancer` service UID, run `kubectl get svc hw-lb-svc -o yaml` and look for the **metadata.uid** field in the output.
    {: tip}

    ```sh
    ibmcloud is load-balancers
    ```
    {: pre}

    In the following example CLI output, the VPC load balancer that is named `kube-bsaucubd07dhl66e4tgg-1f4f408ce6d2485499bcbdec0fa2d306` is created for the Kubernetes `LoadBalancer` service:
    
    ```sh
    ID                                          Name                                                         Family        Subnets               Is public   Provision status   Operating status   Resource group
    r006-d044af9b-92bf-4047-8f77-a7b86efcb923   kube-bsaucubd07dhl66e4tgg-1f4f408ce6d2485499bcbdec0fa2d306   Application   mysubnet-us-south-3   true        active             online             default
    ```
    {: screen}

4. Send a request to your app by curling the hostname and port of the Kubernetes `LoadBalancer` service that is assigned by the VPC load balancer that you found in step 2.
    ```sh
    curl 1234abcd-us-south.lb.appdomain.cloud:8080
    ```
    {: pre}

    Example output
    ```sh
    Hello world from hello-world-deployment-5fd7787c79-sl9hn! Your app is up and running in a cluster!
    ```
    {: screen}


## What's next?
{: #vpc_ks_next}

Now that you have a VPC cluster, learn more about what you can do.
{: shortdesc}

* [Setting up block storage for your apps](/docs/containers?topic=containers-vpc-block)
* [VPC cluster limitations](/docs/containers?topic=containers-limitations#ks_vpc_gen2_limits)
* [About the v2 API](/docs/containers?topic=containers-cs_api_install#api_about)

Need help, have questions, or want to give feedback on VPC clusters? Try posting in the [Slack channel](https://cloud.ibm.com/kubernetes/slack){: external}.
{: tip}






