# Keycloak

## Install with Helm

```
helm repo add my-repo https://charts.bitnami.com/bitnami
helm install my-release my-repo/keycloak

export HTTP_SERVICE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[?(@.name=='http')].port}" services my-release-keycloak)

export SERVICE_IP=$(kubectl get svc --namespace default my-release-keycloak -o jsonpath='{.status.loadBalancer.ingress[0].ip}')

echo "http://${SERVICE_IP}:${HTTP_SERVICE_PORT}/"
```


## Install with ArgoCD

```
argocd app create keycloak --repo https://charts.bitnami.com/bitnami --helm-chart keycloak --revision ???? --dest-server https://kubernetes.default.svc --dest-namespace keycloak
```



## Configure




