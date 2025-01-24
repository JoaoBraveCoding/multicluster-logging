# multicluster-logging

This repo was used to test the interaction between SSA and ArgoCD in the context
of the multicluster-observability-addon.

```sh
# Install ArgoCD
helm upgrade --install argocd bootstrap
```

## Create Applications

```sh
# Application with full LokiStack specification
oc apply -f applications/lokistack-full

# Application with partial LokiStack specification
oc apply -f applications/lokistack-partial

# Application with simple LokiStack specification
oc apply -f applications/lokistack-simple
```
