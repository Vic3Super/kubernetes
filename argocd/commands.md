https://argo-cd.readthedocs.io/en/latest/try_argo_cd_locally/

https://argo-cd.readthedocs.io/en/latest/getting_started/#4-log-in-using-the-cli

### Install ArgoCD
```
kubectl create namespace argocd
kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Expose ArgoCD API Server

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### Access ArgoCD UI

```
http://localhost:8080
```

### Login + Change password

```
argocd admin initial-password -n argocd

argocd login localhost:8080 --insecure

argocd account update-password
```

### Sync Manually

```
argocd app create nginx \
  --repo https://github.com/Vic3Super/kubernetes.git \
  --path app \
  --dest-server https://kubernetes.default.svc \
  --dest-namespace default
```

### Sync with YAML

```
kubectl apply -f argocd/application.yaml


kubectl get applications -n argocd
```