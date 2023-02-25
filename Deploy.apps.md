
guestbook

```   
argocd app create kustomize-guestbook --repo https://github.com argoproj/argocd-example-apps.git --path kustomize-guestbook --dest-namespace default --dest-server https://kubernetes.default.svc --kustomize-image gcr.io/heptio-images/ks-guestbook-demo:0.1

argocd app create helm-guestbook --repo https://github.com/argoproj/argocd-example-apps.git --path helm-guestbook --dest-namespace default --dest-server https://kubernetes.default.svc --helm-set replicaCount=2
```


EKS Workshop App

```
kubectl apply -f https://raw.githubusercontent.com/aws-containers/retail-store-sample-app/main/dist/kubernetes/deploy.yaml

kubectl wait --for=condition=available deployments -l app.kubernetes.io/created-by=retail-store-sample -A

kubectl get svc -n ui

```


