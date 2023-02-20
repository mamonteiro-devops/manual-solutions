## PoC Traefik


### Description
Set up Traefik Ingress in Kubernetes (cloud AWS)
<br/>
<br/>

### Pre-requisites      
Provision a K8s cluster
<br/>
<br/>

### Traefik
Deploy Traefik as an ingress controller


<br/>

### Install with ArgoCD

```
kubectl create ns traefik

argocd app create traefik-api-gateway --repo https://github.com/traefik/traefik-helm-chart.git --path traefik/ --dest-server https://kubernetes.default.svc --dest-namespace traefik

```