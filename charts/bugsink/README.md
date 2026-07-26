## Bugsink Helm Chart

Helm chart for deploying Bugsink on Kubernetes using [Helm](https://github.com/helm/helm).

## Before You Begin

Before you proceed with the installation, make sure that:

- You satisfy the prerequisites mentioned
  [here](https://github.com/bugsink/helm-charts/blob/main/README.md#Prerequisites).
- You have added and updated the Bugsink Helm repository in your Helm repositories list as explained
  [here](https://github.com/bugsink/helm-charts/blob/main/README.md#Usage).

## Installing

To install Bugsink using Helm with the release name `my-bugsink`:

```console
helm install my-bugsink bugsink/bugsink
```

Refer to the chart [values](https://github.com/bugsink/helm-charts/blob/main/charts/bugsink/values.yaml) file for
configuration options.

## Upgrading

### Upgrading to 0.2.0

Version `0.2.0` replaces the bundled Bitnami `postgresql` dependency with the
[HelmForge `postgresql`](https://helmforge.dev/docs/charts/postgresql) chart. **There is no automatic upgrade path**
if you use the bundled database (`postgresql.enabled: true`): back up your database, upgrade the chart, then restore
your backup into the newly created PostgreSQL instance. Instances using `externalDatabase` are unaffected.

## Uninstalling

To uninstall the deployed Bugsink instance:

```console
helm uninstall my-bugsink
```

**Note:** Replace `my-bugsink` with the release name that you have used during installation.

**Note:** If you have deployed Bugsink with the built-in PostgreSQL chart, make sure to delete its PVCs as well.

