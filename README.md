# Charts

Public QAware Helm chart repository

## Included packages

Chart | Version | Description 
--- | --- | ---
Reflector | 0.3.1 | Synchronizes secrets and configmaps across namespaces

## Build and upload package

``` bash
git checkout master
helm package <name>
git checkout gh-pages
helm repo index . --url https://qaware.github.io/charts/
git add .
git commit -m "Add <name>-<version> chart"
git push
```
