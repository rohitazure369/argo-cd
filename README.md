# argo-cd


# update argo cd service to convert as LoadBalancer type to get public IP
## not recommeded to production
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'


# get the Argo CD default admin password 
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

