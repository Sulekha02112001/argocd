# ArgoCD

1. kubectl create namespace argocd
2. kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

3. kubectl edit svc argocd-server -n argocd

change type: NodePort

4. kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

5. kubectl apply -f aplication.yml
