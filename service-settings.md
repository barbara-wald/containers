---

copyright: 
  years: 2014, 2024
lastupdated: "2024-05-29"


keywords: containers, {{site.data.keyword.containerlong_notm}}

subcollection: containers


---

{{site.data.keyword.attribute-definition-list}}





# Default service settings for Kubernetes components
{: #service-settings}

Review the default settings for Kubernetes components, such as the `kube-apiserver`, `kubelet`, `kube-scheduler`, or `kube-proxy` that {{site.data.keyword.containerlong}} sets when you create your cluster. 
{: shortdesc}



## `kube-apiserver`
{: #kube-apiserver}

Review the default settings for the `kube-apiserver` master component in {{site.data.keyword.containerlong_notm}}. 
{: shortdesc}

Default pod tolerations
:   `default-not-ready-toleration-seconds=600s`
:   `default-unreachable-toleration-seconds=600s`

Privileged pods
:   `allow-privileged=true`

Request and response headers
:   `strict-transport-security-directives="max-age=31536000"` (Kubernetes version 1.28 and later)
:   `requestheader-client-ca-file=/mnt/etc/kubernetes-cert/ca.pem`
:   `requestheader-username-headers=X-Remote-User`
:   `requestheader-group-headers=X-Remote-Group`
:   `requestheader-extra-headers-prefix=X-Remote-Extra-`

Number of client requests
:   `max-requests-inflight=1600`
:   `max-mutating-requests-inflight=800`

Admission controllers
:   `ClusterTrustBundleAttest` (Kubernetes version 1.27 and later)
:   `ValidatingAdmissionPolicy` (Kubernetes version 1.27 and later)
:   `DefaultStorageClass`
:   `NamespaceLifecycle`
:   `LimitRanger`
:   `ServiceAccount`
:   `MutatingAdmissionWebhook`
:   `ValidatingAdmissionWebhook`
:   `ResourceQuota`
:   `DefaultTolerationSeconds`
:   `StorageObjectInUseProtection`
:   `PersistentVolumeClaimResize`
:   `Priority`
:   `PodSecurity` (Optional in Kubernetes version 1.24, enabled in version 1.25 and later)
:   `PodSecurityPolicy` (Kubernetes version 1.24 and earlier)
:   `NodeRestriction`
:   `TaintNodesByCondition`
:   `CertificateApproval` 
:   `CertificateSigning` 
    - `CertificateSubjectRestriction` 
    - `DefaultIngressClass` 
    - `RuntimeClass` 
    - `DenyServiceExternalIPs`


Feature gates 
:   See [Feature gates](#feature-gates) 

TLS cipher support
:   TLS version 1.2:
    - `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`
    - `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`

:   TLS version 1.3:
    - `TLS_AES_128_GCM_SHA256`
    - `TLS_CHACHA20_POLY1305_SHA256`
    - `TLS_AES_256_GCM_SHA384`


## `kube-controller-manager`
{: #kube-controller-manager}

Review the default settings for the `kube-controller-manager` master component in {{site.data.keyword.containerlong_notm}}. 
{: shortdesc}

Node monitor grace period
:   `node-monitor-grace-period=50s` (Kubernetes version 1.30 and later)

Feature gates
:   See [Feature gates](#feature-gates)

Pod garbage collection threshold
:   `terminated-pod-gc-threshold=12500`

TLS cipher support
:   TLS version 1.2:
    - `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`
    - `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`

:   TLS version 1.3:
    - `TLS_AES_128_GCM_SHA256`
    - `TLS_CHACHA20_POLY1305_SHA256`
    - `TLS_AES_256_GCM_SHA384`



## `kubelet`
{: #kubelet}

Review the default settings for the `kubelet` worker node component in {{site.data.keyword.containerlong_notm}}. 
{: shortdesc}

`imageGCHighThresholdPercent: 75` (Kubernetes version 1.26 and later)

`imageGCLowThresholdPercent: 65` (Kubernetes version 1.26 and later)

`kubeAPIQPS: 50` (Kubernetes version 1.27 and later)

`kubeAPIBurst: 100` (Kubernetes version 1.27 and later)

`eventBurst: 100` (Kubernetes version 1.27 and later)

`eventRecordQPS: 50` (Kubernetes version 1.27 and later)

`serializeImagePulls: false`

`registryPullQPS: 5`

`registryBurst: 5`


cgroups 
:   `kubeletCgroups: /podruntime/kubelet`
:   `runtime-cgroups=/podruntime/runtime`

Container logs
:   `containerLogMaxSize: 100Mi`
:   `containerLogMaxFiles: 3`

Container runtime endpoint
:   `containerRuntimeEndpoint: "unix:///run/containerd/containerd.sock"`

CPU CFS quota
:   `cpuCFSQuotaPeriod: 20ms`

Feature gates
:   See [Feature gates](#feature-gates).

File check frequency
:   `fileCheckFrequency: 5s`

Graceful Node Shutdown
:   `shutdownGracePeriodCriticalPods: 15s`

Kubernetes and system reserves
:   `kubeReserved calculated based on worker node flavor`
:   `systemReserved calculated based on worker node flavor`

Pod eviction
```sh
evictionSoft:
  memory.available:  "100Mi"
  nodefs.available: "10%"
  imagefs.available: "10%"
  nodefs.inodesFree: "10%"
  imagefs.inodesFree: "10%"
```
{: screen}

```sh
evictionSoftGracePeriod:
  memory.available: "10m"
  nodefs.available: "10m"
  imagefs.available: "10m"
  nodefs.inodesFree: "10m"
  imagefs.inodesFree: "10m"
```
{: screen}

```sh
evictionHard:
  memory.available: "100Mi"
  nodefs.available: "5%"
  imagefs.available: "5%"
  nodefs.inodesFree: "5%"
  imagefs.inodesFree: "5%"
```
{: screen}

Pod manifest path
:   `staticPodPath: /etc/kubernetes/manifests`

TLS cipher support
:   TLS version 1.2:
    - `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`
    - `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`

:   TLS version 1.3: 
    - `TLS_AES_128_GCM_SHA256`
    - `TLS_CHACHA20_POLY1305_SHA256`
    - `TLS_AES_256_GCM_SHA384`


## `kube-scheduler`
{: #kube-scheduler}

Review the default settings for the `kube-scheduler` worker node component in {{site.data.keyword.containerlong_notm}}. 
{: shortdesc}

TLS cipher support
:   TLS version 1.2:
    - `TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256`
    - `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
    - `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
    - `TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256`

:   TLS version 1.3:
    - `TLS_AES_128_GCM_SHA256`
    - `TLS_CHACHA20_POLY1305_SHA256`
    - `TLS_AES_256_GCM_SHA384`


## `kube-proxy`
{: #kube-proxy}

Review the default settings for the `kube-proxy` worker node component in {{site.data.keyword.containerlong_notm}}. 
{: shortdesc}


Iptable settings
:   `iptables-sync-period 120` (Kubernetes version 1.29 and later)
:   `iptables-min-sync-period 2s` (Kubernetes version 1.29 and later)
:   `iptables-sync-period 180s` (Kubernetes version 1.28)
:   `iptables-min-sync-period 3s` (Kubernetes version 1.28)
:   `iptables-sync-period 300s` (Kubernetes version 1.27 and earlier)
:   `iptables-min-sync-period 5s` (Kubernetes version 1.27 and earlier)
:   `iptables-localhost-nodeports false` (Kubernetes versions 1.26 and later)


Proxy mode
:   `proxy-mode=iptables`

Feature gates
:   See [Feature gates](#feature-gates)




## Feature gates
{: #feature-gates}


Review the feature gates that are applied to all master and worker node components by default in {{site.data.keyword.containerlong_notm}} clusters. These feature gates differ from the ones that are set up in community distributions. In clusters that run version 1.23 or earlier, the {{site.data.keyword.cloud_notm}} provider version enables Kubernetes APIs and features that are at beta. In version 1.24 and later, most new beta features are disabled by default. Kubernetes alpha features, which are subject to change, are disabled in all versions. 
{: shortdesc}




In cluster version 1.26 and later, you can use the **`kubectl get --raw /metrics | grep kubernetes_feature_enabled`** command to determine if a feature gate is enabled or disabled.
{: tip}

1.30
:   `CustomCPUCFSQuotaPeriod=true`

1.29
:   `CustomCPUCFSQuotaPeriod=true`
:   `KMSv1=true`
:   `StructuredAuthenticationConfiguration=true`

1.28
:   `CustomCPUCFSQuotaPeriod=true`
:   `UnauthenticatedHTTP2DOSMitigation=true`

1.27
:   `CustomCPUCFSQuotaPeriod=true`
:   `UnauthenticatedHTTP2DOSMitigation=true`

1.26
:   `CustomCPUCFSQuotaPeriod=true`
:   `UnauthenticatedHTTP2DOSMitigation=true`


1.25
:   `CustomCPUCFSQuotaPeriod=true`
:   `UnauthenticatedHTTP2DOSMitigation=true`


1.24
:   `CustomCPUCFSQuotaPeriod=true`
:   `LegacyServiceAccountTokenNoAutoGeneration=false`
:   `PodSecurity=false`

1.23
:   `CustomCPUCFSQuotaPeriod=true`
:   `ServiceLBNodePortControl=false`
:   `PodSecurity=false`

1.22
:   `ServiceLBNodePortControl=false`
:   `CustomCPUCFSQuotaPeriod=true`
:   `IPv6DualStack=false`

1.21
:   `ServiceLoadBalancerClass=true`
:   `CustomCPUCFSQuotaPeriod=true`
:   `IPv6DualStack=false`

1.20
:   `AllowInsecureBackendProxy=false`
:   `CustomCPUCFSQuotaPeriod=true`

1.19
:   `RuntimeClass=false`
:   `CustomCPUCFSQuotaPeriod=true`
:   `AllowInsecureBackendProxy=false`
:   `SCTPSupport=false`
:   `ServiceAppProtocol=false`

1.18
:   `RuntimeClass=false`
:   `CustomCPUCFSQuotaPeriod=true`
:   `AllowInsecureBackendProxy=false`





