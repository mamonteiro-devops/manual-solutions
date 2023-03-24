

## Prerequisites

- Kubernetes cluster
- AWS CLI installed
- Add new context to  ~/.kube/config
    aws eks --region <AWS REGION> update-kubeconfig --name <EKS CLUSTER NAME>



## Install ArgoCD

```
kubectl create ns argocd

kubectl apply -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.4.7/manifests/install.yaml -n argocd

kubectl edit svc argocd-server -n argocd
	Define this service as LoadBalancer

kubectl port-forward service/argocd-server -n argocd 8080:443

```

Get secret

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

## Install ArgoCD
How to Install the Argo-Cd Helm Chart

Add Chart Repository to Helm
```
helm repo add argo https://argoproj.github.io/argo-helm
```

Install Chart

```
kubectl create ns argocd

helm install my-argo-cd argo/argo-cd --version 4.5.8
```

In order to access the server UI you have the following options:

```
kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443

kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```


## Example of a simple deploy

```
argocd login localhost:8080


k create ns external-dns

argocd login <ALB address>

argocd app create external-dns --repo https://charts.bitnami.com/bitnami --helm-chart external-dns --revision 6.14.0 --dest-server https://kubernetes.default.svc --dest-namespace external-dns

```

