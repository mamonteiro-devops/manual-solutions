


## external-dns



```
argocd login localhost:8080

k create ns external-dns

argocd app create external-dns --repo https://github.com/lablabs/terraform-aws-eks-external-dns.git --path helm/argocd-application/ --dest-server https://kubernetes.default.svc --dest-namespace external-dns\n

```


