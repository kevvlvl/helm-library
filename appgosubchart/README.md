# Helm Chart and Subcharts

Make use of a helm subchart and global values to refer to a parent (centralized) chart in an effort to make the a centralized chart and its related templates.
The use of global variables makes it possible for the subchart to override values defined in the parent chart

The relationship here is with gochartparent which is an application parent Helm Chart

## Run the charts in dry-run debug mode

Update the dependencies (to the chart libraries)
```
helm dependency update appgosubchart
```

Validate the charts by generating k8s manifests
```
helm template appgosubchart --dry-run --debug
```

## Documentation

- https://helm.sh/docs/chart_template_guide/subcharts_and_globals/