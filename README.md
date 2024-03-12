# argo-cd

    helm repo add argo https://argoproj.github.io/argo-helm

    helm install argo-cd argo/argo-cd --namespace argocd --create-namespace

    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
PASSword: XX6UaGUGSDz65yke

# update argo cd service to convert as LoadBalancer type to get public IP
## not recommeded to production
    kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'


# get the Argo CD default admin password 
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

