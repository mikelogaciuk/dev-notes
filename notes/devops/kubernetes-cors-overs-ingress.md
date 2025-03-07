# CORS over Ingress

## Story

To control CORS (Cross-Origin Resource Sharing) using an Ingress in Kubernetes, you typically need to set the appropriate headers. This can often be done using annotations on the Ingress resource or by configuring your Ingress controller.

Here's a general approach, assuming you are using an NGINX Ingress controller:

**1. Annotations on the Ingress Resource:**

You can add CORS-related annotations to your Ingress resource to enable and configure CORS. Here’s an example:

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: grafana-ingress
  annotations:
    nginx.ingress.kubernetes.io/enable-cors: "true"
    nginx.ingress.kubernetes.io/cors-allow-origin: "https://your-allowed-origin.com"
    nginx.ingress.kubernetes.io/cors-allow-methods: "GET, PUT, POST, DELETE, PATCH, OPTIONS"
    nginx.ingress.kubernetes.io/cors-allow-headers: "DNT, X-CustomHeader, Keep-Alive, User-Agent, X-Requested-With, If-Modified-Since, Cache-Control, Content-Type"
spec:
  rules:
  - host: grafana.yourdomain.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: grafana
            port:
              number: 80
ConfigMap for the Ingress Controller:
```

If the annotations are not enough or you need more customization, you can configure the NGINX Ingress controller via a ConfigMap. This requires access to the ConfigMap managing your ingress settings.

**2. Example ConfigMap snippet:**

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: nginx-ingress-controller
  namespace: ingress-nginx
data:
  enable-cors: "true"
  cors-allow-origin: "https://your-allowed-origin.com"
  cors-allow-methods: "GET, PUT, POST, DELETE, PATCH, OPTIONS"
  cors-allow-headers: "DNT, X-CustomHeader, Keep-Alive, User-Agent, X-Requested-With, If-Modified-Since, Cache-Control, Content-Type"

```

**3. Custom NGINX Configuration:**

If you need more control, you might need to implement a custom NGINX configuration using a ConfigMap and the nginx.ingress.kubernetes.io/configuration-snippet annotation to directly inject NGINX directives.

Example:

```yaml
annotations:
  nginx.ingress.kubernetes.io/configuration-snippet: |
    more_set_headers "Access-Control-Allow-Origin: https://your-allowed-origin.com";
    more_set_headers "Access-Control-Allow-Methods: GET, PUT, POST, DELETE, PATCH, OPTIONS";
    more_set_headers "Access-Control-Allow-Headers: DNT, X-CustomHeader, Keep-Alive, User-Agent, X-Requested-With, If-Modified-Since, Cache-Control, Content-Type";
```

Make sure to replace `"https://your-allowed-origin.com"` with the actual origin you want to allow.

These options require that you are using an NGINX-based Ingress controller. If you are using a different Ingress controller, the configuration steps might vary.
