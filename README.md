# argocd-apps-bootstrap

## Prerequisites

```
# option 1
helm repo add argo https://argoproj.github.io/argo-helm
helm -n argocd upgrade -i argocd-appprojects-bootstrap argo/argocd-apps --values values.projects.yaml
# option 2
helm -n argocd upgrade -i argocd-appprojects-bootstrap oci://ghcr.io/argoproj/argo-helm/argocd-apps --values values.projects.yaml
```

## Template
```
helm template <app-name>-bootstrap [<repo-name>/]<chart-name> | <folder> | . --values /path/to/values.bootstrap.yaml --debug
helm template <app-name>-bootstrap [<repo-name>/]<chart-name> | <folder> | . --values /path/to/values.yaml --debug
```

## Install and upgrade
```
helm -n argocd upgrade -i <app-name>-bootstrap [<repo-name>/]<chart-name> | <folder> | . --values /path/to/values.bootstrap.yaml
```

## References

- https://github.com/argoproj/argo-helm/tree/main/charts/argocd-apps
- https://github.com/argoproj/argo-cd/tree/master/docs/operator-manual
