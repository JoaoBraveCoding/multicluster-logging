# multicluster-logging

This repo was used to test the interaction between SSA and ArgoCD in the context
of the multicluster-observability-addon.

```sh
# Install ArgoCD
oc create ns argocd
helm -n argocd upgrade --install argocd bootstrap
```

## Create Applications

```sh
# Application with full LokiStack specification
oc apply -f applications/application-ls-full.yaml

# Application with partial LokiStack specification
oc apply -f applications/application-ls-partial.yaml

# Application with simple LokiStack specification
oc apply -f applications/application-ls-simple.yaml
```

## Results

### Full specificaton

- Update cycle if users try to update LS in fields they should not own
- No update cycle as users only specify fields that they own

### Simple specification

- Update cycle if users try to update LS in fields they should not own
- No update cycle as users only specify fields that they own

### Partial specification

- No update cycle as users only specify fields that they own
