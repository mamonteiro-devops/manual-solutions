

```
export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>
export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>
export AWS_DEFAULT_REGION=us-east-1
```

-- ArgoCD
helm repo add argo https://argoproj.github.io/argo-helm
kubectl create ns argocd
helm install my-argo-cd argo/argo-cd --version 4.5.8


-- Port-forward
kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443
http://127.0.0.1:8080

-- Get ArgoCD password
kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d


-- App

kubectl apply -f https://raw.githubusercontent.com/aws-containers/retail-store-sample-app/main/dist/kubernetes/deploy.yaml
kubectl wait --for=condition=available deployments -l app.kubernetes.io/created-by=retail-store-sample -A

kubectl get svc -n ui
--



