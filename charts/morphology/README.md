# morphology

This chart deploys the `morphology` sidecar, which utilizes a Docker image with `spaCy` models to provide
morphological analysis for a variety of languages.

The main required values it accepts is a list of language code/model combinations. Models are downloaded at runtime,
which adds launch time overhead. It is recommended to set `startupProbe` to a higher value to allow the sidecar
to download the models before it starts serving requests.

You can browse models on the [spaCy models page](https://spacy.io/models) to find the appropriate language codes.
Consider the different sizes (`sm`, `md`, `lg`) based on your performance and accuracy needs. Size examples:

| model            | size  |
|------------------|-------|
| `en_core_web_sm` | 12MB  |
| `en_core_web_md` | 31MB  |
| `en_core_web_lg` | 382MB |

Documentation on the sidecar can be found in the [grammr documentation](https://github.com/twaslowski/grammr/blob/main/sidecars/morphology/README.md).

## Values

A sample values.yaml could look like this:

```yaml
languages:
  - code: de
    model: de_core_news_lg
  - code: en
    model: en_core_web_lg

startupProbe:
  httpGet:
    path: /actuator/health
    port: 8080
  initialDelaySeconds: 60
  timeoutSeconds: 5
 ```

## Installation

Sample installation command:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts

# Use the values.yaml defined above
helm install --namespace grammr --create-namespace morphology grammr/morphology \
  --values values.yaml
```