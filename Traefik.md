# Bare Metal

## Description
    Set up Traefik Ingress in Kubernetes Bare Metal


## PoC Traefik
    I will decribe all the steps to deploy Traefik ingress controller in Kubernetes cluster, explaining the pre-requisites. 
    Te steps described here are oriented to a local deployment.
    
## Pre-requisites      
    - Provision a K8s cluster
    - Deploy a load balancing solution - In my case I will use metallb (if you are using managed k8s service in one of the cloud providers you don't need metallb)
    - Verify that metallb is working as espected
    - Setup dynamic storage provisioning - nfs


## Traefik
    - Deploy Traefik as an ingress controller




# AWS

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


