# anki-exporter

This chart deploys the `anki-exporter` service, which provides the capability to export Flashcard and Deck
entities from grammr-core to the Anki `APKG` or `DB` formats.

No configuration values are required for basic usage.

## Installation

Sample installation command:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts

helm install --namespace grammr --create-namespace anki-exporter grammr/anki-exporter
```
