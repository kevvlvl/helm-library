# Helm Chart libraries

Make use of helm libraries in an effort to centralise your chart templates in a single source of truth.

The relationship here is with chartlibrary which is a library Helm chart

## Run the charts in dry-run debug mode

Update the dependencies (to the chart libraries)
```
helm dependency update applibraryimpl
```

Validate the charts by generating k8s manifests
```
helm template applibraryimpl --dry-run --debug

---
# Source: applibraryimpl/templates/configmap.yaml
apiVersion: v1
data:
  geolocation: Houston
  instanceName: app-lib-implementer
kind: ConfigMap
metadata:
  labels:
    app: Unlocked
  name: applibraryimpl-release-name
```

## Documentation

- https://helm.sh/docs/chart_template_guide/getting_started/
- https://helm.sh/docs/chart_template_guide/function_list/