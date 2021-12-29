# Install Argo CD

```hcl
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```

## edit the service to expose

```hcl
kubectl edit svc argocd-server -n argocd
change type: NodePort
```

- username: admin

## get the argocd password

```hcl
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

## launch application

```hcl
kubectl apply -f aplication.yml
```
