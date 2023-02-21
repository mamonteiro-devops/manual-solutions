

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



traefik/traefik-helm-chart
    https://github.com/traefik/traefik-helm-chart