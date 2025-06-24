# grammr-charts

This repository contains the Helm charts for the [grammr project](https://github.com/twaslowski/grammr).

It is a utility repository, because the charts are hosted via GitHub Pages, and the main repository already hosts
its Swagger API documentation there, which leads to incompatibilities with the Helm repository structure.

For documentation of the services that these charts deploy, please refer to the main repository.

## Usage

To use the Helm charts in this repository, you can add it as a Helm repository:

```bash
helm repo add grammr https://twaslowski.github.io/grammr-charts
helm repo update

helm search repo grammr
```

Then, you can install the charts using:

```bash
helm install <release-name> grammr/<chart-name>
```

