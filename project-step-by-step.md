

```
export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>
export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>
export AWS_DEFAULT_REGION=us-east-1
```

-- ArgoCD
```
helm repo add argo https://argoproj.github.io/argo-helm
kubectl create ns argocd
helm install my-argo-cd argo/argo-cd --version 4.5.8
```


-- Port-forward
```
kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443
http://127.0.0.1:8080
```

-- Get ArgoCD password

```
kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
or
❯ kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d


```


-- App

```
kubectl apply -f https://raw.githubusercontent.com/aws-containers/retail-store-sample-app/main/dist/kubernetes/deploy.yaml
kubectl wait --for=condition=available deployments -l app.kubernetes.io/created-by=retail-store-sample -A

kubectl get svc -n ui
```

--

-- Calico

```
kubectl apply -f "https://docs.projectcalico.org/manifests/calico.yaml"

helm repo add projectcalico https://docs.tigera.io/calico/charts

echo '{ installation: {kubernetesProvider: EKS }}' > values.yaml

cat > values.yaml <<EOF
installation:
  kubernetesProvider: AKS
  cni:
    type: Calico
  calicoNetwork:
    bgp: Disabled
    ipPools:
    - cidr: 10.244.0.0/16
      encapsulation: VXLAN
EOF

helm show values projectcalico/tigera-operator --version v3.25.0

kubectl create namespace tigera-operator

Install the Tigera Calico operator and custom resource definitions using the Helm chart:

    helm install calico projectcalico/tigera-operator --version v3.25.0 --namespace tigera-operator


    helm install calico projectcalico/tigera-operator --version v3.25.0 -f values.yaml --namespace tigera-operator

    watch kubectl get pods -n calico-system


 The default encapsulation for Calico is a IP-in-IP protocol, which involves wrapping a layer 3 IP packet 

```


-- Nginx

```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

helm search repo bitnami
helm search repo nginx
helm search repo bitnami/nginx


helm install mywebserver bitnami/nginx
kubectl get deploy,po,svc

kubectl describe deployment mywebserver
kubectl get pods -l app.kubernetes.io/name=nginx
kubectl get service mywebserver-nginx -o wide


```

-- keycloak (Not working yet)

```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm install my-keycloak bitnami/keycloak --version 13.3.0

```

 
