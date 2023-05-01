# Helm Chart and Subcharts

Make use of a helm subchart and global values to refer to a parent (centralized) chart in an effort to make the a centralized chart and its related templates.
The use of global variables makes it possible for the subchart to override values defined in the parent chart

The relationship here is with chartparent which is an application parent Helm Chart

## Run the charts in dry-run debug mode

Update the dependencies (to the chart libraries)
```
helm dependency update appsubchart
```

Validate the charts by generating k8s manifests
```
helm template appsubchart --dry-run --debug

---
# Source: appsubchart/charts/chartparent/templates/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: chartparent-release-name
  labels:
    app: Unlocked
data:
  geolocation: Austin, TX
  instanceName: app-subchart-imp
```

As we can see, those are values from the subchart's global values yaml. If we do not use global then a subchart cannot override values of a parent chart (in this case gochartpraent). It's the other way around, the parent can override subchart values.

## Documentation

- https://helm.sh/docs/chart_template_guide/subcharts_and_globals/