

# ------------------------ WIP


## Prerequsites 
    - Kubernetes cluster
    - argoCD cli installed 
    - Helm3 installed




## Installing the Helm Chart  


Add the Strimzi Helm Chart repository:
```
helm repo add strimzi https://strimzi.io/charts/
```

To install the chart with the release name my-release:

```
helm install my-strimzi-kafka-operator strimzi/strimzi-kafka-operator --version 0.33.2
```




## Installing ArgoCD application 

\
Login to Argo CD using a username and password
\
&nbsp;&nbsp;&nbsp;&nbsp;argocd login SERVER [flags]


```
In my local environment I use:
    argoCD login localhost:8008

Username to use: admin
Password       : kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

Create an application


```
argocd app create strimzi --repo https://github.com/strimzi/strimzi-kafka-operator.git --path helm-charts/helm3/strimzi-kafka-operator/ --dest-server https://kubernetes.default.svc --dest-namespace strimzi

```




