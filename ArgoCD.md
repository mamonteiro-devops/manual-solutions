

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
helm install my-argo-cd argo/argo-cd --version 4.5.8
```

In order to access the server UI you have the following options:

```
kubectl port-forward service/my-argo-cd-argocd-server -n default 8080:443
```

and then open the browser on http://localhost:8080 and accept the certificate

Enable ingress in the values file `server.ingress.enabled` and either

- Add the annotation for ssl passthrough: https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/ingress.md#option-1-ssl-passthrough
\

- Add the `--insecure` flag to `server.extraArgs` in the values file and terminate SSL at your ingress: https://github.com/argoproj/argo-cd/blob/master/docs/operator-manual/ingress.md#option-2-multiple-ingress-objects-and-hosts


After reaching the UI the first time you can login with username: admin and the random password generated during the installation. You can find the password by 
running:

```
kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```


## Example of a simple deploy

```
argocd login localhost:8080


k create ns external-dns

argocd login <ALB address>

argocd app create external-dns --repo https://charts.bitnami.com/bitnami --helm-chart external-dns --revision 6.14.0 --dest-server https://kubernetes.default.svc --dest-namespace external-dns

```




