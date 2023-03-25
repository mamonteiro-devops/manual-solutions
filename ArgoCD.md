

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

```
helm repo add argo https://argoproj.github.io/argo-helm
kubectl create ns argocd

helm install my-argo-cd argo/argo-cd --version 4.5.8
kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443
kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

kubectl get secret -n argocd argocd-initial-admin-secret -o yaml
```


## Argocd CLI
```
brew install argocd
```

Download With Curl
Download latest version

```
curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
rm argocd-linux-amd64
```


## ArgoCD application

k apply -f application.yaml
k get application -n argocd 

argocd login localhost:8080 --insecure
argocd app list

### Directory of files 

cd /home/mamonteiro/manuel.monteiro.github/gitops/argocd-apps-definitions/applications and projects

kubectl  apply -f application\ -\ Directory\ options.yaml

