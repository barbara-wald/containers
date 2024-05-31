---

copyright:
  years: 2014, 2022
lastupdated: "2024-05-29"

keywords: kubernetes, nginx, ingress controller

subcollection: containers

---

{{site.data.keyword.attribute-definition-list}}




# Customizing ALB routing 
{: #comm-ingress-annotations}

Modify the default settings for ALBs that run the Kubernetes Ingress image.
{: shortdesc}

Sometimes, you can customize routing for Ingress by adding [Kubernetes NGINX annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/){: external} (`nginx.ingress.kubernetes.io/<annotation>`). Kubernetes NGINX annotations are always applied to all service paths in the resource, and you can't specify service names within the annotations. Custom {{site.data.keyword.containerlong_notm}} annotations (`ingress.bluemix.net/<annotation>`) are **not** supported.
{: note}

Kubernetes Ingress Controllers (ALBs) on clusters created on or after 31 January 2022 do not process Ingress resources that have snippet annotations (for example, `nginx.ingress.kubernetes.io/configuration-snippet`) by default as all new clusters are deployed with `allow-snippet-annotations: "false"` configuration in the ALB's ConfigMap. If you add any configuration snippets recommended here, you need to edit the ALB's ConfigMap (`kube-system/ibm-k8s-controller-config`) and change `allow-snippet-annotations: "false"` to `allow-snippet-annotations: "true"`.
{: note}

## Adding a server port to a host header
{: #add-sport-hheader}

To add a server port to the client request before the request is forwarded to your back-end app, configure a proxy to external services in a [server snippet annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#server-snippet){: external} or as an `ibm-k8s-controller-config` ConfigMap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#proxy-set-headers){: external}.
{: shortdesc}


## Routing incoming requests with a private ALB
{: #alb_id_anno}

To route incoming requests to your apps with a private ALB, specify the `private-iks-k8s-nginx` class annotation in the [Ingress resource](/docs/containers?topic=containers-managed-ingress-setup). Private ALBs are configured to use resources with this class.
{: shortdesc}

```sh
kubernetes.io/ingress.class: "private-iks-k8s-nginx"
```
{: screen}

## Authenticating apps with {{site.data.keyword.appid_short_notm}} 
{: #app-id-authentication}

Configure Ingress with [{{site.data.keyword.appid_full_notm}}](https://cloud.ibm.com/catalog/services/app-id){: external} to enforce authentication for your apps by changing specific Kubernetes Ingress fields. See [Adding {{site.data.keyword.appid_short_notm}} authentication to apps](#app-id-auth) for more information.
{: shortdesc}

## Setting the maximum client request body size
{: #client-request-bodysize}

To set the maximum size of the body that the client can send as part of a request, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#custom-max-body-size){: external}. 
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/proxy-body-size: 8m
```
{: screen}

## Enabling and disabling client response data buffering
{: #client-response-data-buffering}

You can disable or enable the storage of response data on the ALB while the data is sent to the client. This setting is disabled by default. To enable, set the following Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#rewrite){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/proxy-buffering: "on"
```
{: screen}

## Customizing connect and read timeouts
{: #custom-connect-read-timeouts}

To set the amount of time that the ALB waits to connect to and read from the back-end app before the back-end app is considered unavailable, use the following [annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#custom-timeouts){: external}.
{: shortdesc}


```sh
nginx.ingress.kubernetes.io/proxy-connect-timeout: 62
```
{: screen}

```sh
nginx.ingress.kubernetes.io/proxy-read-timeout: 62
```
{: screen}


## Customizing error actions
{: #custom-error-actions}

To indicate custom actions that the ALB can take for specific HTTP errors, set the `custom-http-errors` [field](https://kubernetes.github.io/ingress-nginx/examples/customization/custom-errors/){: external}.
{: shortdesc}

## Changing the default HTTP and HTTPS ports
{: #custom-http-https-ports}

To change the default ports for HTTP (port 80) and HTTPS (port 443) network traffic, [modify each ALB service](#comm-customize-deploy) with the following Kubernetes Ingress `ibm-ingress-deploy-config` ConfigMap [fields](#comm-customize-deploy).
{: shortdesc}

Example field setting.

```sh
httpPort=8080
httpsPort=8443
```
{: screen}

## Customizing the request header
{: #custom-request-header}

To add header information to a client request before forwarding the request to your back-end app, use the following Kubernetes `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#proxy-set-headers){: external}
{: shortdesc}

```sh
proxy-set-headers: "ingress-nginx/custom-headers"
```
{: screen}

For the `custom-headers` ConfigMap requirements, see [this example](https://github.com/kubernetes/ingress-nginx/blob/main/docs/examples/customization/custom-headers/custom-headers.yaml){: external}.


## Customizing the response header
{: #custom-response-header}

To add header information to a client response before sending it to the client, use the following [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#configuration-snippet){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/configuration-snippet: |
    more_set_headers "Request-Id: $req_id";
```
{: screen}

## Adding path definitions to external services
{: #external-services-path}

To add path definitions to external services, such as services hosted in IBM Cloud, configure a proxy to external services in a [location snippet](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#configuration-snippet){: external}. Or, replace the proxy with a [permanent redirect to external services](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#permanent-redirect){: external}.
{: shortdesc}

## Redirecting insecure requests 
{: #http-redirects-https}

By default, insecure HTTP client requests redirect to HTTPS. To disable this setting, use the following field and annotation.
{: shortdesc}

* `ibm-k8s-controller-config` ConfigMap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#server-side-https-enforcement-through-redirect){: external}
    ```sh
    ssl-redirect: "false"
    ```
    {: screen}

* Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#server-side-https-enforcement-through-redirect){: external}:
    ```sh
    nginx.ingress.kubernetes.io/ssl-redirect: "false"
    ```
    {: screen}


## Enabling and disabling HTTP Strict Transport Security
{: #http-strict-transport-security}

Set the browser to access the domain only by using HTTPS. This option is enabled by default. 
{: shortdesc}

* To add max age and subdomain granularity, see [this NGINX blog](https://blog.nginx.org/blog/http-strict-transport-security-hsts-and-nginx){: external}.
* To disable, set the `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#hsts){: external}.
    ```sh
    hsts: false
    ```
    {: screen}


## Setting a maximum number of keepalive requests
{: #keepalive-requests}

To set the maximum number of requests that can be served through one keepalive connection, use the following Kubernetes `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#keep-alive-requests){: external}.
{: shortdesc}

```sh
keep-alive-requests: 100
```
{: screen}

The default value for `keep-alive-requests` in Kubernetes Ingress is `100`, which is much less than the default value of `4096` in {{site.data.keyword.containerlong_notm}} Ingress. If you migrated your Ingress setup from {{site.data.keyword.containerlong_notm}} Ingress to Kubernetes Ingress, you might need to change `keep-alive-requests` to pass existing performance tests.
{: note}

## Setting a maximum keepalive request timeout
{: #keepalive-request-timeout}

To set the maximum time that a keepalive connection stays open between the client and the ALB proxy server, use the following Kubernetes `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#keep-alive){: external}.
{: shortdesc}

```sh
keep-alive: 60
```
{: screen}

## Setting a maximum number of large client header buffers
{: #large-client-header-buffers}

To set the maximum number and size of buffers that read large client request headers, use the following Kubernetes `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#large-client-header-buffers){: external}.
{: shortdesc}

```sh
large-client-header-buffers: 4 8k
```
{: screen}

## Modifying how the ALB matches the request URI
{: #location-modifier}

To modify the way the ALB matches the request URI against the app path, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#use-regex){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/use-regex: "true"
```
{: screen}

For more info, see [this blog](https://kubernetes.github.io/ingress-nginx/user-guide/ingress-path-matching/#ingress-path-matching){: external}.


## Adding custom location block configurations
{: #location-snippets}

To add a custom location block configuration for a service, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#configuration-snippet){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/configuration-snippet: |
    more_set_headers "Request-Id: $req_id";
```
{: screen}


## Configuring mutual authentication
{: #mutual-authentication}

To configure mutual authentication for the ALB, use the following Kubernetes Ingress resource [annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#client-certificate-authentication){: external}. Note that mutual authentication can't be applied to custom ports and must be applied to the HTTPS port.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/auth-tls-verify-client: "on"
nginx.ingress.kubernetes.io/auth-tls-secret: "default/ca-secret"
nginx.ingress.kubernetes.io/auth-tls-verify-depth: "1"
nginx.ingress.kubernetes.io/auth-tls-error-page: "http://www.mysite.com/error-cert.html"
nginx.ingress.kubernetes.io/auth-tls-pass-certificate-to-upstream: "true"
```
{: screen}

## Configuring proxy buffer size
{: #proxy-buffer-size}

To configure the size of the proxy buffer that reads the first part of the response, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#proxy-buffer-size){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/proxy-buffer-size: "8k"
```
{: screen}


## Configuring proxy buffer numbers
{: #config-proxy-buffers}

To configure the number of proxy buffers for the ALB, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#proxy-buffering){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/proxy-buffers-number: "4"
```
{: screen}


## Configuring busy proxy buffer size
{: #proxy-busy-buffer-size}

To configure the size of proxy buffers that can be busy, use a [location snippet](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#configuration-snippet){: external}. For more info, see the [NGINX docs](http://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_busy_buffers_size){: external}.
{: shortdesc}

## Configuring when an ALB can pass a request
{: #proxy-next-upstream}

To set when the ALB can pass a request to the next upstream server, use the following Kubernetes Ingress fields.
{: shortdesc}

* Global setting: `ibm-k8s-controller-config` ConfigMap [fields](http://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_next_upstream){: external}:
    ```sh
    retry-non-idempotent: true
    proxy-next-upstream: error timeout http_500
    ```
    {: screen}

* Per-resource setting: Ingress resource [annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#custom-timeouts){: external}:

    ```sh
    nginx.ingress.kubernetes.io/proxy-next-upstream: http_500
    nginx.ingress.kubernetes.io/proxy-next-upstream-timeout: 50
    nginx.ingress.kubernetes.io/proxy-next-upstream-tries: 3
    ```
    {: screen}


## Rate limiting
{: #rate-limiting}

To limit the request processing rate and number of connections per a defined key for services, use the Ingress resource [annotations for rate limiting](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#rate-limiting){: external}.
{: shortdesc}

## Removing the response header 
{: #response-header-removal}

You can remove header information that is included in the client response from the back-end end app before the response is sent to the client. Configure the response header removal in a [location snippet](https://github.com/openresty/headers-more-nginx-module#more_clear_headers){: external}, or use the [`proxy_hide_header` field](http://nginx.org/en/docs/http/ngx_http_proxy_module.html#proxy_hide_header){: external} as a [configuration snippet](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#configuration-snippet){: external} in the `ibm-k8s-controller-config` ConfigMap.
{: shortdesc}

## Rewriting paths
{: #alb-rewrite-paths}

To route incoming network traffic on an ALB domain path to a different path that your back-end app listens on, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#rewrite){: external}. 
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/rewrite-target: /newpath
```
{: screen}


## Customizing server block configurations
{: #server-snippets-custom}

To add a custom server block configuration, use the following Kubernetes Ingress resource [annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#server-snippet){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/server-snippet: |
    location = /health {
    return 200 'Healthy';
    add_header Content-Type text/plain;
    }
```
{: screen}

## Routing incoming network traffic
{: #session-affinity-cookies}

To always route incoming network traffic to the same upstream server by using a sticky cookie, use the following Kubernetes Ingress resource [annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#session-affinity){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/affinity: "cookie"
nginx.ingress.kubernetes.io/session-cookie-name: "cookie_name1"
nginx.ingress.kubernetes.io/session-cookie-expires: "172800"
nginx.ingress.kubernetes.io/session-cookie-max-age: "172800"
nginx.ingress.kubernetes.io/configuration-snippet: |
  more_set_headers "Set-Cookie: HttpOnly";
```
{: screen}

The Kubernetes Ingress controller adds the `Secure` and `HttpOnly` attributes to the sticky cookies by default, which can't be changed.
{: note}

## Allowing SSL services support to encrypt traffic
{: #ssl-services-support}

To allow SSL services support to encrypt traffic to your upstream apps that require HTTPS, use the Kubernetes Ingress resource [backend protocol annotation](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#backend-protocol){: external} and the [backend certificate authentication annotations](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/annotations/#backend-certificate-authentication){: external}.
{: shortdesc}

```sh
nginx.ingress.kubernetes.io/backend-protocol: "HTTPS"
nginx.ingress.kubernetes.io/proxy-ssl-secret: app1-ssl-secret
nginx.ingress.kubernetes.io/proxy-ssl-verify-depth: 5
nginx.ingress.kubernetes.io/proxy-ssl-name: proxy-ssl-name=mydomain.com
nginx.ingress.kubernetes.io/proxy-ssl-verify: true
```
{: screen}


## Accessing apps with non-standard TCP ports
{: #tcp-ports-non-standard}

To access an app via a non-standard TCP port, follow these steps.
{: shortdesc}

1. Create a `tcp-services` ConfigMap to specify your TCP port, such as the following example ports. For the requirements of the `tcp-services` ConfigMap, see [this blog](https://kubernetes.github.io/ingress-nginx/user-guide/exposing-tcp-udp-services/){: external}.
    ```yaml
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: tcp-services
      namespace: kube-system
    data:
      9000: "<namespace>/<service>:8080"
    ```
    {: codeblock}

2. Create the ConfigMap in the `kube-system` namespace.

    ```sh
    kubectl apply -f tcp-services.yaml -n kube-system
    ```
    {: pre}

3. Specify the `tcp-services` ConfigMap as a field in the [`ibm-ingress-deploy-config` ConfigMap](#comm-customize-deploy).

    ```sh
    "tcpServicesConfig":"kube-system/tcp-services"
    ```
    {: screen}

4. [Modify each ALB service](#comm-customize-deploy) to add the ports.

## Setting a maximum number of upstream keepalive requests
{: #upstream-keepalive-requests}

To set the maximum number of requests that can be served through one keepalive connection, use the following Kubernetes `ibm-k8s-controller-config` ConfigMap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#upstream-keepalive-requests){: external}.
{: shortdesc}

```sh
upstream-keepalive-requests: 32
```
{: screen}


## Setting the maximum upstream keepalive timeout
{: #upstream-keepalive-timeout}

To set the maximum time that a keepalive connection stays open between the ALB proxy server and your app's upstream server, use the following Kubernetes `ibm-k8s-controller-config` configmap [field](https://kubernetes.github.io/ingress-nginx/user-guide/nginx-configuration/configmap/#upstream-keepalive-timeout){: external}.
{: shortdesc}

```sh
upstream-keepalive-timeout: 32
```
{: screen}

## Customizing the ALB deployment
{: #comm-customize-deploy}

Customize the deployment for ALBs that run the Kubernetes Ingress image by creating an `ibm-ingress-deploy-config` ConfigMap.
{: shortdesc}

1. Get the names of the services that expose each ALB.

    * Classic clusters:
    
        ```sh
        kubectl get svc -n kube-system | grep alb
        ```
        {: pre}

    * VPC clusters: In the output, look for a service name that is formatted such as `public-crc204dl7w0qf6n6sp7tug`.
    
        ```sh
        kubectl get svc -n kube-system | grep LoadBalancer
        ```
        {: pre}

### Creating a ConfigMap to customize the Ingress deployment
{: #create-ingress-configmap-custom}


1. Create a YAML file for an `ibm-ingress-deploy-config` ConfigMap. For each ALB ID, you can specify one or more of the following optional settings. Note that you can specify only the settings that you want to configure, and don't need to specify all the settings.

    ```yaml
    apiVersion: v1
    kind: ConfigMap
    metadata:
      name: ibm-ingress-deploy-config
      namespace: kube-system
    data:
      <alb1-id>: '{"deepInspect":"<true|false>", "defaultBackendService":"<service_name>", "defaultCertificate":"<namespace>/<secret_name>", "defaultConfig":"<namespace>/<configmap-name>","enableSslPassthrough":"<true|false>", "httpPort":"<port>", "httpsPort":"<port>", "ingressClass":"<class>", "logLevel":<log_level>, "replicas":<number_of_replicas>, "tcpServicesConfig":"<kube-system/tcp-services>"}'
      <alb2-id>: '{"deepInspect":"<true|false>", "defaultBackendService":"<service_name>", "defaultCertificate":"<namespace>/<secret_name>", "enableSslPassthrough":"<true|false>", "httpPort":"<port>", "httpsPort":"<port>", "ingressClass":"<class>","logLevel":<log_level>, "replicas":<number_of_replicas>, "tcpServicesConfig":"<kube-system/tcp-services>"}'
    ```
    {: screen}

    `deepInspect`
    :   Enable or disable Ingress object security deep inspector. When enabled, ALBs inspect configuration values in Ingress resources before processing. For more information, see [the ingress-nginx source code](https://github.com/kubernetes/ingress-nginx/tree/main/internal/ingress/inspector){: external}.
    :   This feature is available for ALB versions 1.2.0 and later and enabled by default.
    

    `defaultBackendService`
    :   Specify the name of an optional default service to receive requests when no host is configured or no matching host is found. This service replaces the IBM-provided default service that generates a `404` message. You might use this service to configure custom error pages or for testing connections.
    
   `defaultCertificate`
    :   A secret for a default TLS certificate to apply to any subdomain that is configured with Ingress ALBs in the format `secret_namespace/secret_name`. To create a secret, you can run the [ibmcloud ks ingress secret create](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_secret_create) command. If a secret for a different TLS certificate is specified in the `spec.tls` section of an Ingress resource, and that secret exists in the same namespace as the Ingress resource, then that secret is applied instead of this default secret.
    
    `defaultConfig`
    :   Specify a default configmap for your ALBs. Enter the location of the configmap you want to use in the format `namespace/configmap-name`. For example, `kube-system/ibm-k8s-controller-config`.

    `enableAnnotationValidation`
    :   Enable or disable Ingress object annotation validation. When enabled, ALBs validate annotation values in Ingress resources before processing. For more information, see [the ingress-nginx source code](https://github.com/kubernetes/ingress-nginx/tree/main/internal/ingress/annotations){: external}.
    :   This feature is available for ALB versions 1.9.0 and later and enabled by default.
    
    `enableSslPassthrough`
    :   Enable SSL passthrough for the ALB. The TLS connection is not terminated and passes through untouched.
    
    `httpPort`, `httpsPort`
    :   Expose non-default ports for the Ingress ALB by adding the HTTP or HTTPS ports that you want to open.
    
    `ingressClass`
    :   If you specified a class other than `public-iks-k8s-nginx` or `private-iks-k8s-nginx` in your Ingress resource, specify the class.
    
    `logLevel`
    :   Specify the log level that you want to use. Choose from the following values. 
    :   `2`: Shows the details by using the `**diff**` command to show changes in the configuration in `NGINX`. 
    :   `3`: Shows the details about the service, Ingress rule, endpoint changes in JSON format.
    :   `5`: Configures `NGINX` in debug mode.
    :   For more information about logging, see [Debug Logging](https://kubernetes.github.io/ingress-nginx/troubleshooting/#debug-logging){: external}.
    
    `replicas`
    :   By default, each ALB has 2 replicas. Scale up your ALB processing capabilities by increasing the number of ALB pods. For more information, see [Increasing the number of ALB pod replicas](/docs/containers?topic=containers-ingress-alb-manage#scale_albs).
    
    `tcpServicesConfig`
    :   Specify a ConfigMap and the namespace that the ConfigMap is in, such as [`kube-system/tcp-services`](#tcp-ports-non-standard), that contains information about accessing your app service through a non-standard TCP port.


2. Create the `ibm-ingress-deploy-config` ConfigMap in your cluster.
    ```sh
    kubectl create -f ibm-ingress-deploy-config.yaml
    ```
    {: pre}

3. To pick up the changes, update your ALBs. Note that it might take up to 5 minutes for the changes to be applied to your ALBs.
    ```sh
    ibmcloud ks ingress alb update -c <cluster_name_or_ID>
    ```
    {: pre}

4. If you specified non-standard HTTP, HTTPS, or TCP ports, you must open the ports on each ALB service.
    1. For each ALB service that you found in step 1, edit the YAML file.
        ```sh
        kubectl edit svc -n kube-system <alb_svc_name>
        ```
        {: pre}

    2. In the `spec.ports` section, add the ports that you want to open. By default, ports 80 and 443 are open. If you want to keep 80 and 443 open, don't remove them from this file. Any port that is not specified is closed. Do not specify a `nodePort`. After you add the port and apply the changes, a `nodePort` is automatically assigned
            
        ```sh
        ...
        ports:
        - name: port-80
          nodePort: 32632
          port: 80
          protocol: TCP
          targetPort: 80
        - name: port-443
          nodePort: 32293
          port: 443
          protocol: TCP
          targetPort: 443
        - name: <new_port>
          port: <port>
          protocol: TCP
          targetPort: <port>
        ...
        ```
        {: screen}

    3. Save and close the file. Your changes are applied automatically.



## Customizing the Ingress class
{: #-custom-ingress-class}

An Ingress class associates a class name with an Ingress controller type. Use the [`IngressClass`](https://kubernetes.io/docs/concepts/services-networking/ingress/#ingress-class){: external} resource to customize Ingress classes.
{: shortdesc}



## Adding {{site.data.keyword.appid_short_notm}} authentication to apps
{: #app-id-auth}

Enforce authentication for your apps by configuring Ingress with [{{site.data.keyword.appid_full_notm}}](https://cloud.ibm.com/catalog/services/app-id){: external}.
{: shortdesc}


1. Choose an existing or create a new {{site.data.keyword.appid_short_notm}} instance.

    An {{site.data.keyword.appid_short_notm}} instance can be used in only one namespace in your cluster. If you want to configure {{site.data.keyword.appid_short_notm}} for Ingress resources in multiple namespaces, repeat the steps in this section to specify a unique {{site.data.keyword.appid_short_notm}} instance for the Ingress resources in each namespace.
    {: note}
    
    * To use an existing instance, ensure that the service instance name contains only **lowercase** alphanumeric characters and its length does not exceed 25 characters. To change the name, select **Rename service** from the more options menu on your service instance details page.
    * To provision a [new {{site.data.keyword.appid_short_notm}} instance](https://cloud.ibm.com/catalog/services/app-id):
        1. Replace the **Service name** with your own unique name for the service instance. The service instance name must contain only lowercase alphanumeric characters and can not be longer than 25 characters.
        2. Choose the same region that your cluster is deployed in.
        3. Click **Create**.

2. Add redirect URLs for your app. A redirect URL is the callback endpoint of your app. To prevent phishing attacks, {{site.data.keyword.appid_full_notm}} validates the request URL against the allowlist of redirect URLs.
    1. In the {{site.data.keyword.appid_short_notm}} management console, navigate to **Manage Authentication**.
    2. In the **Identity providers** tab, make sure that you have an Identity Provider selected. If no Identity Provider is selected, the user will not be authenticated but is issued an access token for anonymous access to the app.
    3. In the **Authentication settings** tab, add redirect URLs for your app in the format `https://<hostname>/oauth2-<App_ID_service_instance_name>/callback`. Note that all letters in the service instance name must specified as lowercase.

    If you use the [{{site.data.keyword.appid_full_notm}} logout function](/docs/appid?topic=appid-cd-sso#cd-sso-log-out), you must append `/sign_out` to your domain in the format `https://<hostname>/oauth2-<App_ID_service_instance_name>/sign_out` and include this URL in the redirect URLs list. If you want to use a custom logout page, you must set `whitelist_domains` in the ConfigMap for OAuth2-Proxy. Call the `https://<hostname>/oauth2-<App_ID_service_instance_name>/sign_out` endpoint with the `rd` query parameter or set the `X-Auth-Request-Redirect` header with your custom logout page. For more details, see [Sign out](https://oauth2-proxy.github.io/oauth2-proxy/features/endpoints/#sign-out){: external}.
    {: note}

3. Bind the {{site.data.keyword.appid_short_notm}} service instance to your cluster. The command creates a service key for the service instance, or you can include the `--key` option to use existing service key credentials. Be sure to bind the service instance to the same namespace that your Ingress resources exist in. Note that all letters in the service instance name must specified as lowercase.
    ```sh
    ibmcloud ks cluster service bind --cluster <cluster_name_or_ID> --namespace <namespace> --service <App_ID_service_instance_name> [--key <service_instance_key>]
    ```
    {: pre}

    When the service is successfully bound to your cluster, a cluster secret is created that holds the credentials of your service instance. Example CLI output:
    ```sh
    ibmcloud ks cluster service bind --cluster mycluster --namespace mynamespace --service appid1
    Binding service instance to namespace...
    OK
    Namespace:    mynamespace
    Secret name:  binding-<service_instance_name>
    ```
    {: screen}

4. Enable the ALB OAuth Proxy add-on in your cluster. This add-on creates and manages the following Kubernetes resources: an OAuth2-Proxy deployment for your {{site.data.keyword.appid_short_notm}} service instance, a secret that contains the configuration of the OAuth2-Proxy deployment, and an Ingress resource that configures ALBs to route incoming requests to the OAuth2-Proxy deployment for your {{site.data.keyword.appid_short_notm}} instance. The name of each of these resources begins with `oauth2-`.
    1. Enable the `alb-oauth-proxy` add-on.
        ```sh
        ibmcloud ks cluster addon enable alb-oauth-proxy --cluster <cluster_name_or_ID>
        ```
        {: pre}

    2. Verify that the ALB OAuth Proxy add-on has a status of `Addon Ready`.
        ```sh
        ibmcloud ks cluster addon ls --cluster <cluster_name_or_ID>
        ```
        {: pre}

5. In the Ingress resources for apps where you want to add {{site.data.keyword.appid_short_notm}} authentication, make sure that the resource name does not exceed 25 characters in length. Then, add the following annotations to the `metadata.annotations` section.
    1. Add the following `auth-url` annotation. This annotation specifies the URL of the OAuth2-Proxy for your {{site.data.keyword.appid_short_notm}} instance, which acts as the OIDC Relying Party (RP) for {{site.data.keyword.appid_short_notm}}. Note that all letters in the service instance name must be specified as lowercase.
        ```yaml
        ...
        annotations:
           nginx.ingress.kubernetes.io/auth-url: https://oauth2-<App_ID_service_instance_name>.<namespace_of_Ingress_resource>.svc.cluster.local/oauth2-<App_ID_service_instance_name>/auth
        ...
        ```
        {: codeblock}

    2. Sometimes the authentication cookie used by `OAuth2-Proxy` exceeds 4 KB. Therefore it is split into two parts. The following snippet must be added to ensure that both cookies could be properly updated by `OAuth2-Proxy`.
        ```yaml
        ...
        annotations:
            nginx.ingress.kubernetes.io/configuration-snippet: |
            auth_request_set $_oauth2_<App_ID_service_instance_name>_upstream_1 $upstream_cookie__oauth2_<App_ID_service_instance_name>_1;
            access_by_lua_block {
                if ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 ~= "" then
                ngx.header["Set-Cookie"] = "_oauth2_<App_ID_service_instance_name>_1=" .. ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 .. ngx.var.auth_cookie:match("(; .*)")
                end
            }
        ...
        ```
        {: codeblock}


    3. Choose which tokens to send in the `Authorization` header to your app. For more information about ID and access tokens, see the [{{site.data.keyword.appid_short_notm}} documentation](/docs/appid?topic=appid-tokens){: external}.
        * To send only the `ID Token`, add the following annotation:
        
            ```yaml
            ...
            annotations:
                nginx.ingress.kubernetes.io/auth-response-headers: Authorization
            ...
            ```
            {: codeblock}

        * To send only the `Access Token`, add the following information to the `configuration-snippet` annotation. (This extends the snippet from Step 5.2.)
        
            ```yaml
            ...
            annotations:
                nginx.ingress.kubernetes.io/configuration-snippet: |
                auth_request_set $_oauth2_<App_ID_service_instance_name>_upstream_1 $upstream_cookie__oauth2_<App_ID_service_instance_name>_1;
                auth_request_set $access_token $upstream_http_x_auth_request_access_token;
                access_by_lua_block {
                    if ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 ~= "" then
                    ngx.header["Set-Cookie"] = "_oauth2_<App_ID_service_instance_name>_1=" .. ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 .. ngx.var.auth_cookie:match("(; .*)")
                    end
                    if ngx.var.access_token ~= "" then
                    ngx.req.set_header("Authorization", "Bearer " .. ngx.var.access_token)
                    end
                }
            ...
            ```
            {: codeblock}

        * To send the `Access Token` and the `ID Token`, add the following information to the `configuration-snippet` annotation. (This extends the snippet from Step 5.2.)
            ```yaml
            ...
             annotations:
                nginx.ingress.kubernetes.io/configuration-snippet: |
                auth_request_set $_oauth2_<App_ID_service_instance_name>_upstream_1 $upstream_cookie__oauth2_<App_ID_service_instance_name>_1;
                auth_request_set $access_token $upstream_http_x_auth_request_access_token;
                auth_request_set $id_token $upstream_http_authorization;
                access_by_lua_block {
                    if ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 ~= "" then
                    ngx.header["Set-Cookie"] = "_oauth2_<App_ID_service_instance_name>_1=" .. ngx.var._oauth2_<App_ID_service_instance_name>_upstream_1 .. ngx.var.auth_cookie:match("(; .*)")
                    end
                    if ngx.var.id_token ~= "" and ngx.var.access_token ~= "" then
                    ngx.req.set_header("Authorization", "Bearer " .. ngx.var.access_token .. " " .. ngx.var.id_token:match("%s*Bearer%s*(.*)"))
                    end
                }
            ...
            ```
            {: codeblock}

    4. Optional: If your app supports the [web app strategy](/docs/appid?topic=appid-key-concepts#term-web-strategy) in addition to or instead of the [API strategy](/docs/appid?topic=appid-key-concepts#term-api-strategy), add the `nginx.ingress.kubernetes.io/auth-signin: https://$host/oauth2-<App_ID_service_instance_name>/start?rd=$escaped_request_uri` annotation. Note that all letters in the service instance name must be in lowercase.
        * If you specify this annotation, and the authentication for a client fails, the client is redirected to the URL of the OAuth2-Proxy for your {{site.data.keyword.appid_short_notm}} instance. This OAuth2-Proxy, which acts as the OIDC Relying Party (RP) for {{site.data.keyword.appid_short_notm}}, redirects the client to your {{site.data.keyword.appid_short_notm}} login page for authentication.
        * If you don't specify this annotation, a client must authenticate with a valid bearer token. If the authentication for a client fails, the client's request is rejected with a `401 Unauthorized` error message.

6. Re-apply your Ingress resources to enforce {{site.data.keyword.appid_short_notm}} authentication. After an Ingress resource with the appropriate annotations is re-applied, the ALB OAuth Proxy add-on deploys an OAuth2-Proxy deployment, creates a service for the deployment, and creates a separate Ingress resource to configure routing for the OAuth2-Proxy deployment messages. Do not delete these add-on resources.
    ```sh
    kubectl apply -f <app_ingress_resource>.yaml -n namespace
    ```
    {: pre}

7. Verify that {{site.data.keyword.appid_short_notm}} authentication is enforced for your apps.
    * If your apps supports the [web app strategy](/docs/appid?topic=appid-key-concepts#term-web-strategy): Access your app's URL in a web browser. If {{site.data.keyword.appid_short_notm}} is correctly applied, you are redirected to an {{site.data.keyword.appid_short_notm}} authentication log-in page.
    * If your apps supports the [API strategy](/docs/appid?topic=appid-key-concepts#term-api-strategy): Specify your `Bearer` access token in the Authorization header of requests to the apps. To get your access token, see the [{{site.data.keyword.appid_short_notm}} documentation](/docs/appid?topic=appid-obtain-tokens). If {{site.data.keyword.appid_short_notm}} is correctly applied, the request is successfully authenticated and is routed to your app. If you send requests to your apps without an access token in the Authorization header, or if the access token is not accepted by {{site.data.keyword.appid_short_notm}}, then the request is rejected.

8. Optional: You can customize the default behavior of the OAuth2-Proxy by creating a Kubernetes ConfigMap.
    1. Create a ConfigMap YAML file that specifies values for the OAuth2-Proxy settings that you want to change.
        ```yaml
        apiVersion: v1
        kind: ConfigMap
        metadata:
          name: oauth2-<App_ID_service_instance_name>
          namespace: <ingress_resource_namespace>
        data:
          auth_logging: <true|false>
          # Log all authentication attempts.
          auth_logging_format:
          # Format for authentication logs. For more info, see https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview#logging-configuration
          cookie_csrf_expire: "15m"
          # Expiration timeframe for CSRF cookie. Default is "15m".
          cookie_csrf_per_request: <true|false>
          # Enable multiple CSRF cookies per request, making it possible to have parallel requests. Default is "false".
          cookie_domains:
          # A list of optional domains to force cookies to. The longest domain that matches the request’s host is used. If there is no match for the request’s host, the shortest domain is used. Example: sub.domain.com,example.com
          cookie_expire: "168h0m0s"
          # Expiration timeframe for cookies. Default: "168h0m0s".
          cookie_samesite: ""
          # SameSite attribute for cookies. Supported values: "lax", "strict", "none", or "".
          email_domains: ""
          # Authenticate IDs that use the specified email domain. To authenticate IDs that use any email domain, use "*". Default: "". Example: example.com,example2.com
          pass_access_token: <true|false>
          # Pass the OAuth access token to the backend app via the X-Forwarded-Access-Token header.
          request_logging: <true|false>
          # Log all requests to the backend app.
          request_logging_format:
          # Format for request logs. For more info, see https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview#request-log-format
          scope:
          # Scope of the OAuth authentication. For more info, see https://oauth.net/2/scope/
          set_authorization_header: <true|false>
          # Set the Authorization Bearer response header when the app responds to the Ingress ALB, such when using the NGINX auth_request mode.
          set_xauthrequest: <true|false>
          # Set X-Auth-Request-User, X-Auth-Request-Email, and X-Auth-Request-Preferred-Username response headers when the app responds to the Ingress ALB, such as when using the NGINX auth_request mode.
          standard_logging: <true|false>
          # Log standard runtime information.
          standard_logging_format:
          # Format for standard logs. For more info, see https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview#standard-log-format
          tls_secret_name:
          # The name of a secret that contains the server-side TLS certificate and key to enable TLS between the OAuth2-Proxy and the Ingress ALB. By default, the TLS secret defined in your Ingress resources is used.
          whitelist_domains:
          # Allowed domains for redirection after authentication. Default: "". Example: example.com,*.example2.com For more info, see: https://oauth2-proxy.github.io/oauth2-proxy/configuration/overview#command-line-options
          oidc_extra_audiences:
          # Additional audiences which are allowed to pass verification. 
          cookie_refresh: 
          # Refresh the cookie after this duration. Example: "15m". To use this feature, you must enable "Refresh token" for the AppID instance. For more info, see: /docs/appid?topic=appid-managing-idp&interface=ui#idp-token-lifetime
        ```
        {: codeblock}

    2. Apply the ConfigMap resource to your add-on. Your changes are applied automatically.
        ```sh
        kubectl apply -f oauth2-<App_ID_service_instance_name>.yaml
        ```
        {: pre}

For the list of changes for each ALB OAuth Proxy add-on version, see the [{{site.data.keyword.cloud_notm}} ALB OAuth Proxy add-on change log](/docs/containers?topic=containers-alb-oauth-proxy-changelog).
{: tip}

### Upgrading ALB OAuth Proxy add-on
{: #upgrading-alb-oauth-proxy-add-on}

To upgrade the ALB OAuth Proxy add-on, you must first disable the add-on, then re-enable the add-on and specify the desired version.
{: shortdesc}

The upgrade process is non-interruptive as the supervised OAuth2 Proxy instances remain on the cluster even when the add-on is disabled.
{: note}

1. Disable the add-on.
    ```sh
    ibmcloud ks cluster addon disable alb-oauth-proxy --cluster <cluster_name_or_ID>
    ```
    {: pre}

1. List the available add-on versions and decide which version you want to use.
    ```sh
    ibmcloud ks cluster addon versions --addon alb-oauth-proxy
    ```
    {: pre}

1. Enable the add-on and specify the `--version` option. If you don't specify a version, the default version is enabled.
    ```sh
    ibmcloud ks cluster addon enable alb-oauth-proxy --cluster <cluster_name_or_ID> [--version <version>]
    ```
    {: pre}


## Preserving the source IP address
{: #preserve_source_ip}

By default, the source IP addresses of client requests are not preserved by the Ingress ALB. To preserve source IP addresses, you can enable the [PROXY protocol in VPC clusters](#preserve_source_ip_vpc) or [change the `externalTrafficPolicy` in classic clusters](#preserve_source_ip_classic).
{: shortdesc}

### Enabling the PROXY protocol in VPC clusters
{: #preserve_source_ip_vpc}

To preserve the source IP address of the client request in a VPC cluster, you can enable the [NGINX PROXY protocol](https://docs.nginx.com/nginx/admin-guide/load-balancer/using-proxy-protocol/){: external} for all load balancers that expose Ingress ALBs in your cluster.
{: shortdesc}

The PROXY protocol enables load balancers to pass client connection information that is contained in headers on the client request, including the client IP address, the proxy server IP address, and both port numbers, to ALBs.

1. Enable the PROXY protocol. For more information about this command's parameters, see the [CLI reference](/docs/containers?topic=containers-kubernetes-service-cli#cs_ingress_lb_proxy-protocol_enable). After you run this command, new load balancers are created with the updated PROXY protocol configuration. Two unused IP addresses for each load balancer must be available in each subnet during the load balancer recreation. After these load balancers are created, the existing ALB load balancers are deleted. This load balancer recreation process might cause service disruptions.

    ```sh
    ibmcloud ks ingress lb proxy-protocol enable --cluster <cluster_name_or_ID> --cidr <subnet_CIDR> --header-timeout <timeout>
    ```
    {: pre}

2. Confirm that the PROXY protocol is enabled for the load balancers that expose ALBs in your cluster.
    ```sh
    ibmcloud ks ingress lb get --cluster <cluster_name_or_ID>
    ```
    {: pre}

3. To later disable the PROXY protocol, you can run the following command:
    ```sh
    ibmcloud ks ingress lb proxy-protocol disable --cluster <cluster_name_or_ID>
    ```
    {: pre}

### Changing the `externalTrafficPolicy` in classic clusters
{: #preserve_source_ip_classic}

Preserve the source IP address for client requests in a classic cluster.
{: shortdesc}

By default, the source IP address of the client request is not preserved. When a client request to your app is sent to your cluster, the request is routed to a pod for the load balancer service that exposes the ALB. If no app pod exists on the same worker node as the load balancer service pod, the load balancer forwards the request to an app pod on a different worker node. The source IP address of the package is changed to the public IP address of the worker node where the app pod runs.

To preserve the original source IP address of the client request, you can enable [source IP preservation](https://kubernetes.io/docs/tutorials/services/source-ip/#source-ip-for-services-with-typeloadbalancer){: external}. Preserving the client’s IP is useful, for example, when app servers have to apply security and access-control policies.

When source IP preservation is enabled, load balancers shift from forwarding traffic to an app pod on a different worker node to an app pod on the same worker node. Your apps might experience downtime during this shift. If you [disable an ALB](/docs/containers?topic=containers-kubernetes-service-cli#cs_alb_configure), any source IP changes you make to the load balancer service that exposes the ALB are lost. When you re-enable the ALB, you must enable source IP again.

If you configured edge nodes in your cluster, ALB pods are deployed to edge nodes and can only forward traffic to app pods that are also deployed to those edge nodes. Ensure that you have [at least three edge worker nodes per zone](/docs/containers?topic=containers-edge#edge_nodes_alb).
{: important}

To enable source IP preservation, edit the load balancer service that exposes an Ingress ALB:

1. Enable source IP preservation for a single ALB or for all the ALBs in your cluster.
    * To set up source IP preservation for a single ALB:
        1. Get the ID of the ALB for which you want to enable source IP. The ALB services have a format similar to `public-cr18e61e63c6e94b658596ca93d087eed9-alb1` for a public ALB or `private-cr18e61e63c6e94b658596ca93d087eed9-alb1` for a private ALB.
        
            ```sh
            kubectl get svc -n kube-system | grep alb
            ```
            {: pre}

        2. Open the YAML for the load balancer service that exposes the ALB.
        
            ```sh
            kubectl edit svc <ALB_ID> -n kube-system
            ```
            {: pre}

        3. Under **`spec`**, change the value of **`externalTrafficPolicy`** from `Cluster` to `Local`.

        4. Save and close the configuration file. The output is similar to the following:

            ```sh
            service "public-cr18e61e63c6e94b658596ca93d087eed9-alb1" edited
            ```
            {: screen}

    * To set up source IP preservation for all public ALBs in your cluster, run the following command:
        ```sh
        kubectl get svc -n kube-system | grep alb | awk '{print $1}' | grep "^public" | while read alb; do kubectl patch svc $alb -n kube-system -p '{"spec":{"externalTrafficPolicy":"Local"}}'; done
        ```
        {: pre}

        Example output
        
        ```sh
        "public-cr18e61e63c6e94b658596ca93d087eed9-alb1", "public-cr17e61e63c6e94b658596ca92d087eed9-alb2" patched
        ```
        {: screen}

    * To set up source IP preservation for all private ALBs in your cluster, run the following command:
        ```sh
        kubectl get svc -n kube-system | grep alb | awk '{print $1}' | grep "^private" | while read alb; do kubectl patch svc $alb -n kube-system -p '{"spec":{"externalTrafficPolicy":"Local"}}'; done
        ```
        {: pre}

        Example output
        
        ```sh
        "private-cr18e61e63c6e94b658596ca93d087eed9-alb1", "private-cr17e61e63c6e94b658596ca92d087eed9-alb2" patched
        ```
        {: screen}

2. Verify that the source IP is being preserved in your ALB pods logs.
    1. Get the ID of a pod for the ALB that you modified.
        ```sh
        kubectl get pods -n kube-system | grep alb
        ```
        {: pre}

    2. Open the logs for that ALB pod. Verify that the IP address for the `client` field is the client request IP address instead of the load balancer service IP address.
        ```sh
        kubectl logs <ALB_pod_ID> nginx-ingress -n kube-system
        ```
        {: pre}

3. Now, when you look up the headers for the requests that are sent to your back-end app, you can see the client IP address in the `x-forwarded-for` header.

4. If you no longer want to preserve the source IP, you can revert the changes that you made to the service.
    * To revert source IP preservation for your public ALBs:
        ```sh
        kubectl get svc -n kube-system | grep alb | awk '{print $1}' | grep "^public" | while read alb; do kubectl patch svc $alb -n kube-system -p '{"spec":{"externalTrafficPolicy":"Cluster"}}'; done
        ```
        {: pre}

    * To revert source IP preservation for your private ALBs:
        ```sh
        kubectl get svc -n kube-system | grep alb | awk '{print $1}' | grep "^private" | while read alb; do kubectl patch svc $alb -n kube-system -p '{"spec":{"externalTrafficPolicy":"Cluster"}}'; done
        ```
        {: pre}



## Configuring SSL protocols and SSL ciphers at the HTTP level
{: #ssl_protocols_ciphers}

Enable SSL protocols and ciphers at the global HTTP level by editing the `ibm-k8s-controller-config` ConfigMap.
{: shortdesc}

For example, if you still have legacy clients that require TLS 1.0 or 1.1 support, you must manually enable these TLS versions to override the default setting of TLS 1.2 and TLS 1.3 only.

When you specify the enabled protocols for all hosts, the TLSv1.1 and TLSv1.2 parameters (1.1.13, 1.0.12) work only when OpenSSL 1.0.1 or higher is used. The TLSv1.3 parameter (1.13.0) works only when OpenSSL 1.1.1 built with TLSv1.3 support is used.
{: note}

To edit the ConfigMap to enable SSL protocols and ciphers:

1. Edit the configuration file for the `ibm-k8s-controller-config` ConfigMap resource.

    ```sh
    kubectl edit cm ibm-k8s-controller-config -n kube-system
    ```
    {: pre}

2. Add the SSL protocols and ciphers. Format ciphers according to the [OpenSSL library cipher list format](https://www.openssl.org/docs/man1.1.1/man1/ciphers.html){: external}.

    ```yaml
    apiVersion: v1
    data:
      ssl-protocols: "TLSv1 TLSv1.1 TLSv1.2 TLSv1.3"
      ssl-ciphers: "HIGH:!aNULL:!MD5:!CAMELLIA:!AESCCM:!ECDH+CHACHA20"
    kind: ConfigMap
    metadata:
      name: ibm-k8s-controller-config
      namespace: kube-system
    ```
    {: codeblock}

3. Save the configuration file.

4. Verify that the ConfigMap changes were applied. The changes are applied to your ALBs automatically.

    ```sh
    kubectl get cm ibm-k8s-controller-config -n kube-system -o yaml
    ```
    {: pre}



## Sending your custom certificate to legacy clients
{: #default_server_cert}

If you have legacy devices that don't support Server Name Indication (SNI) and you use a [custom TLS certificate in your Ingress resources](/docs/containers?topic=containers-secrets#tls-custom), you must edit the ALB's server settings to use your custom TLS certificate and custom TLS secret.
{: shortdesc}

When you create a classic cluster, a Let's Encrypt certificate is generated for the default Ingress secret that IBM provides. If you create a custom secret in your cluster and specify this custom secret for TLS termination in your Ingress resources, the Ingress ALB sends the certificate for your custom secret to the client instead of the default Let's Encrypt certificate. However, if a client does not support SNI, the Ingress ALB defaults to the Let's Encrypt certificate because the default secret is listed in the ALB's default server settings. To send your custom certificate to devices that don't support SNI, complete the following steps to change the ALB's default server settings to your custom secret.

The Let's Encrypt certificates that are generated by default aren't intended for production usage. For production workloads, bring your own custom certificate.
{: important}

1. Edit the `alb-default-server` Ingress resource.
    ```sh
    kubectl edit ingress alb-default-server -n kube-system
    ```
    {: pre}

2. In the `spec.tls` section, change the value of the `hosts.secretName` setting to the name of your custom secret that contains your custom certificate.
    Example:
    ```yaml
    spec:
        rules:
        ...
        tls:
        - hosts:
        - invalid.mycluster-<hash>-0000.us-south.containers.appdomain.cloud
        secretName: <custom_secret_name>
    ```
    {: codeblock}

3. Save the resource file.

4. Verify that the resource now points to your custom secret name. The changes are applied to your ALBs automatically.
    ```sh
    kubectl get ingress alb-default-server -n kube-system -o yaml
    ```
    {: pre}



## Tuning ALB performance
{: #perf_tuning}

To optimize performance of your Ingress ALBs, you can change the default settings according to your needs.
{: shortdesc}


### Enabling log buffering and flush timeout
{: #access-log}

By default, the Ingress ALB logs each request as it arrives. If you have an environment that is heavily used, logging each request as it arrives can greatly increase disk I/O utilization. To avoid continuous disk I/O, you can enable log buffering and flush timeout for the ALB by editing the `ibm-k8s-controller-config` Ingress ConfigMap. When buffering is enabled, instead of performing a separate write operation for each log entry, the ALB buffers a series of entries and writes them to the file together in a single operation.
{: shortdesc}

1. Edit the `ibm-k8s-controller-config` ConfigMap.
    ```sh
    kubectl edit cm ibm-k8s-controller-config -n kube-system
    ```
    {: pre}

2. Set the threshold for when the ALB should write buffered contents to the log.
    * Buffer size: Add the `buffer` field and set it to how much log memory can be held in the buffer before the ALB writes the buffered contents to the log file. For example, if the default value of `100KB` is used, the ALB writes buffer contents to the log file every time the buffer reaches 100KB of log content.
    * Time interval: Add the `flush` field and set it to how often the ALB should write to the log file. For example, if the default value of `5m` is used, the ALB writes buffer contents to the log file once every 5 minutes.
    * Time interval or buffer size: When both `flush` and `buffer` are set, the ALB writes buffer content to the log file based on whichever threshold parameter is met first.

    ```yaml
    apiVersion: v1
    kind: ConfigMap
    data:
        access-log-params: "buffer=100KB, flush=5m"
      metadata:
    name: ibm-k8s-controller-config
    ...
    ```
    {: codeblock}

3. Save and close the configuration file. The changes are applied to your ALBs automatically.

4. Verify that the logs for an ALB now contain buffered content that is written according to the memory size or time interval you set.
    ```sh
    kubectl logs -n kube-system <ALB_ID> -c nginx-ingress
    ```
    {: pre}

### Changing the number or duration of keepalive connections
{: #keepalive_time}

Keepalive connections can have a major impact on performance by reducing the CPU and network usage that is needed to open and close connections. To optimize the performance of your ALBs, you can change the maximum number of keepalive connections between the ALB and the client and how long the keepalive connections can last.
{: shortdesc}

1. Edit the `ibm-k8s-controller-config` ConfigMap.
    ```sh
    kubectl edit cm ibm-k8s-controller-config -n kube-system
    ```
    {: pre}

2. Change the values of `keep-alive-requests` and `keep-alive`.
    * `keep-alive-requests`: The number of keepalive client connections that can stay open to the Ingress ALB. The default is `100`.
    * `keep-alive`: The timeout, in seconds, during which the keepalive client connection stays open to the Ingress ALB. The default is `75`.

    ```yaml
    apiVersion: v1
    data:
      keep-alive-requests: 100
      keep-alive: 75
    kind: ConfigMap
    metadata:
      name: ibm-k8s-controller-config
      ...
    ```
    {: codeblock}

3. Save and close the configuration file. The changes are applied to your ALBs automatically.

4. Verify that the ConfigMap changes were applied.
    ```sh
    kubectl get cm ibm-k8s-controller-config -n kube-system -o yaml
    ```
    {: pre}

### Changing the number of simultaneous connections or worker processes
{: #worker_processes_connections}

Change the default setting for how many simultaneous connections the NGINX worker processes for one ALB can handle or how many worker processes can occur for one ALB.
{: shortdesc}

Each ALB has NGINX worker processes that process the client connections and communicate with the upstream servers for the apps that the ALB exposes. By changing the number of worker processes per ALB or how many connections the worker processes can handle, you can manage the maximum number of clients that an ALB can handle. Calculate your maximum client connections with the following formula: `maximum clients = worker_processes * worker_connections`.

* The `max-worker-connections` field sets the maximum number of simultaneous connections that can be handled by the NGINX worker processes for one ALB. The default value is `16384`. Note that the `max-worker-connections` parameter includes all connections that the ALB proxies, not just connections with clients. Additionally, the actual number of simultaneous connections can't exceed the [limit on the maximum number of open files](#max-worker-files), which is set by the `max-worker-open-files` parameter. If you set the value of `max-worker-connections` to `0`, the value for `max-worker-open-files` is used instead.
* The `worker-processes` field sets the maximum number of NGINX worker processes for one ALB. The default value is `"auto"`, which indicates that the number of worker processes matches the number of cores on the worker node where the ALB is deployed. You can change this value to a number if your worker processes must perform high levels of I/0 operations.

1. Edit the `ibm-k8s-controller-config` ConfigMap.
    ```sh
    kubectl edit cm ibm-k8s-controller-config -n kube-system
    ```
    {: pre}

2. Change the value of `max-worker-connections` or `worker-processes`.

    ```yaml
    apiVersion: v1
    data:
      max-worker-connections: 16384
      worker-processes: "auto"
    kind: ConfigMap
    metadata:
      name: ibm-k8s-controller-config
      ...
    ```
    {: codeblock}

3. Save the configuration file. The changes are applied to your ALBs automatically.

4. Verify that the ConfigMap changes were applied.
    ```sh
    kubectl get cm ibm-k8s-controller-config -n kube-system -o yaml
    ```
    {: pre}

### Changing the number of open files for worker processes
{: #max-worker-files}

Change the default maximum for the number of files that can be opened by each worker node process for an ALB.
{: shortdesc}

Each ALB has NGINX worker processes that process the client connections and communicate with the upstream servers for the apps that the ALB exposes. If your worker processes are hitting the maximum number of files that can be opened, you might see a `Too many open files` error in your NGINX logs. By default, the `max-worker-open-files` parameter is set to `0`, which indicates that the value from the following formula is used: `system limit of maximum open files / worker-processes - 1024`. If you change the value to another integer, the formula no longer applies.

1. Edit the `ibm-k8s-controller-config` ConfigMap.
    ```sh
    kubectl edit cm ibm-k8s-controller-config -n kube-system
    ```
    {: pre}

2. Change the value of `max-worker-open-files`.

    ```yaml
    apiVersion: v1
    data:
      max-worker-open-files: 0
    kind: ConfigMap
    metadata:
      name: ibm-k8s-controller-config
      ...
    ```
    {: codeblock}

3. Save the configuration file. The changes are applied to your ALBs automatically.

4. Verify that the ConfigMap changes were applied.

    ```sh
    kubectl get cm ibm-k8s-controller-config -n kube-system -o yaml
    ```
    {: pre}

### Tuning kernel performance
{: #ingress_kernel}

To optimize performance of your Ingress ALBs, you can also [change the Linux kernel `sysctl` parameters on worker nodes](/docs/containers?topic=containers-kernel). Worker nodes are automatically provisioned with optimized kernel tuning, so change these settings only if you have specific performance optimization requirements.
{: shortdesc}
