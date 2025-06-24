# grammr

This chart deploys `grammr-core` application, which provides language processing services and APIs.
It is highly configurable and can be connected to various language models and services.

## Values

A sample `values.yaml` could look like this:

```yaml
openai_api_key: <YOUR_OPENAI_API_KEY>
allowedOrigin: "yourdomain.com"
environment: "production"

languages:
  - code: ru
    morphology:
      enabled: true
      uri: "https://morphology-ru.grammr.svc.cluster.local:8000/morphology"
    inflection:
      enabled: true
      uri: "http://inflection-ru.grammr.svc.cluster.local:8000/inflection"
  - code: de
    morphology:
      enabled: true
      uri: "https://<some-other-domain>/morphology"
    inflection:
      enabled: false

service:
  type: ClusterIP
  port: 8080
ingress:
  enabled: true
  className: "nginx"
  host: "grammr.yourdomain.com"
  path: "/"
```

Other values (such as `image`, `replicaCount`, `podAnnotations`, etc.) can be customized as needed. See the `values.yaml` for all options.

## Installation

Sample installation command:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts

# Use the values.yaml defined above
helm install --namespace grammr --create-namespace grammr grammr/grammr \
  --values values.yaml
```
