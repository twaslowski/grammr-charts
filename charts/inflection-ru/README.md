# inflection-ru

This chart deploys the `inflection-ru` service, which provides inflection functionality for Russian words.

No configuration values are required for basic usage.

Documentation on the sidecar can be found in the [grammr documentation](https://github.com/twaslowski/grammr/blob/main/sidecars/inflection-ru/README.md).

## Installation

Sample installation command:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts

helm install --namespace grammr --create-namespace inflection-ru grammr/inflection-ru
```
