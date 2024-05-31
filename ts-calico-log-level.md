---

copyright: 
  years: 2021, 2024
lastupdated: "2024-05-29"


keywords: kubernetes, containers

subcollection: containers

content-type: troubleshoot

---

{{site.data.keyword.attribute-definition-list}}





# Debugging Calico components
{: #calico_log_level}
{: troubleshoot}
{: support}

[Virtual Private Cloud]{: tag-vpc} [Classic infrastructure]{: tag-classic-inf}

You experience issues with Calico components such as pods that don't deploy or intermittent networking issues. 
{: tsSymptoms}


Increase the logging level of Calico components to gather more information about the issue.
{: tsResolve}

## Increasing the log level for the `calico-typha` components
{: #calico-increase-logging-typha}

Complete the following steps to increase the log level for the `calico-typha` component.

1. Run the following command to edit the `calico-typha` deployment. 
    
    For 1.29 and later:
    ```sh
    kubectl edit deploy calico-typha -n calico-system
    ```
    {: pre}

    For 1.28 and earlier:
    ```sh
    kubectl edit deploy calico-typha -n kube-system
    ```
    {: pre}
    
2. Change the `TYPHA_LOGSEVERITYSCREEN` environment variable from `info` to `debug`.
    ```sh
          containers:
        - env:
          - name: TYPHA_LOGSEVERITYSCREEN
            value: debug
    ```
    {: screen}

    
3. Save and close the file to apply the changes and restart the `calico-typha` deployment.

## Increasing the log level for the `calico-cni` components
{: #calico-increase-logging-cni}

Complete the following steps to increase the log level for the `calico-cni` component.

1. Run the following command to edit the `calico-config` ConfigMap.  
    
    ```sh
    kubectl edit cm -n kube-system calico-config
    ```
    {: pre}
    
2. Change the `cni_network_config` > `plugins` > `log_level` environment variable to `debug`.
    
    ```sh
      cni_network_config: |-
      {
        "name": "k8s-pod-network",
        "cniVersion": "0.3.1",
        "plugins": [
          {
            "type": "calico",
            "log_level": "debug",
    ```
    {: screen}
  
3. Save and close the file. The change won't take effect until the `calico-node` pods are restarted. 

4. Restart the `calico-node` pods to apply the changes.
    
    ```sh
    kubectl rollout restart daemonset/calico-node -n kube-system
    ```
    {: pre}
      
    Example output
      
    ```sh
    daemonset.apps/calico-node restarted
    ```
    {: screen}

## Increasing the log level for the `calico-node` components
{: #calico-increase-logging-node}

Complete the following steps to increase the log level for the `calico-node` component.

1. Run the following command: 
    
    For 1.29 and later:
    ```sh
    kubectl edit ds calico-node -n calico-system
    ```
    {: pre}

    For 1.28 and earlier:
    ```sh
    kubectl edit ds calico-node -n kube-system
    ```
    {: pre}
    

2. Under the `FELIX_USAGEREPORTINGENABLED` name and value pair (or after any of the `FELIX_*` environment variable name value pairs), add the following entry.

    ```sh
    - name: FELIX_LOGSEVERITYSCREEN
      value: Debug
    ```
    {: pre}    
    
3. Save the change. After saving your changes, all the pods in the `calico-node` daemonset complete a rolling update that applies the changes. The `calico-cni` also applies any changes to logging levels in the `kube-system/calico-config` ConfigMap.

## Increasing the log level for the `calico-kube-controllers` components
{: #calico-increase-logging-kube-controllers}

Complete the following steps to increase the log level for the `calico-kube-controllers` component.

1. Edit the daemonset by running the following command. 
    
    For 1.29 and later:
    ```sh
    kubectl edit ds calico-node -n calico-system
    ```
    {: pre}

    For 1.28 and earlier:
    ```sh
    kubectl edit ds calico-node -n kube-system
    ```
    {: pre}
    
    
2. Under the `DATASTORE_TYPE` name and value pair, add the following entry.

    ```sh
    - name: LOG_LEVEL
      value: debug
    ```
    {: pre}
    
3. Save the change. The `calico-kube-controllers` pod restarts and applies the changes.


## Gathering Calico logs
{: #calico-log-gather}

1. List the pods and nodes in your cluster and make a node of the pod name, pod IP address, and worker node that has the issue.
2. Get the logs for the `calico-node` pod on the worker node where the problem occurred.
    
    For 1.29 and later:
    ```sh
    kubectl logs calico-typha-aaa11111a-aaaaa -n calico-system
    ```
    {: pre}

    For 1.28 and earlier:
    ```sh
    kubectl logs calico-typha-aaa11111a-aaaaa -n kube-system
    ```
    {: pre}

3. Get logs for the `calico-kube-controllers` pod.
    
    For 1.29 and later:
    ```sh
    kubectl logs calico-kube-controllers-11aaa11aa1-a1a1a -n calico-system
    ```
    {: pre}

    For 1.28 and earlier:
    ```sh
    kubectl logs calico-kube-controllers-11aaa11aa1-a1a1a -n kube-system
    ```
    {: pre}
  
4. Follow the instructions for [Debugging by using kubectl exec](/docs/containers?topic=containers-cs_ssh_worker#kubectl-exec) to get `/var/log/syslog`, `containerd.log`, `kubelet.log`, and `kern.log` from the worker node.

