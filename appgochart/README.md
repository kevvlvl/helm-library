# Helm Chart libraries

Make use of helm libraries in an effort to centralise your chart templates in a single source of truth.

The relationship here is with gochart which is a library Helm chart

## Run the charts in dry-run debug mode

Update the dependencies (to the chart libraries)
```
helm dependency update appgochart
```

Validate the charts by generating k8s manifests
```
helm template appgochart --dry-run --debug

---
# Source: appgochart/templates/configmap.yaml
apiVersion: v1
data:
  geolocation: Houston
  instanceName: go-app-implementer
kind: ConfigMap
metadata:
  labels:
    app: Unlocked
  name: appgochart-release-name
```

## Documentation

- https://helm.sh/docs/chart_template_guide/getting_started/
- https://helm.sh/docs/chart_template_guide/function_list/