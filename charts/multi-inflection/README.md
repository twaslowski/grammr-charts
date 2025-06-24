# multi-inflection

This chart utilizes a Docker image built on top of the `verbecc` Python library to provide
conjugations for Italian, French, Spanish, Portuguese and Romanian.

It will spawn Pods/Services listening on port 8000 for each language supplied in the `languageCodes`
array. Allowed values for the `languageCodes` array are: `it`, `fr`, `es`, `pt`, `ro`.

Usage instructions are available at the main
[grammr](https://github.com/twaslowski/grammr/blob/main/sidecars/multi-inflection/README.md) repository.

## Installation

Sample installation command:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts

helm install --namespace grammr --create-namespace multi-inflection grammr/multi-inflection \
  --set languageCodes=\{it,fr,es\}
```