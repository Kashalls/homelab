---
template: main.html
---

# Restoring Services

## Bootstraping Flux

### Create or Locate Cluster GPG Key

```sh
export GPG_TTY=$(tty)
gpg --list-secret-keys
```

Find your key fingerprint.

```sh
export FLUX_KEY_FP=<YOUR FINGERPRINT>
```

### Verify cluster is ready for Flux

```sh
flux --kubeconfig=./kubeconfig check --pre
```

### Pre-create the `flux-system` namespace

```sh
kubectl --kubeconfig=./kubeconfig create namespace flux-system --dry-run=client -o yaml | kubectl --kubeconfig=./kubeconfig apply -f -
```

### Add the Age key in-order for Flux to decrypt sops secrets

```sh
gpg --export-secret-keys --armor "${FLUX_KEY_FP}" |
kubectl --kubeconfig=./kubeconfig create secret generic sops-gpg \
    --namespace=flux-system \
    --from-file=sops.asc=/dev/stdin
```

### Install Flux

!!! warning "Due to race conditions with the Flux CRDs you will have to run the below command twice. There should be no errors on this second run."

```sh
kubectl --kubeconfig=./kubeconfig apply --kustomize=./cluster/base/flux-system
```

🎉 At this point after reconciliation Flux state should be restored. 🎉