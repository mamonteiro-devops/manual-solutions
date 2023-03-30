

wget <url-for-yaml-file>

kubectl apply -f <install-....yaml>

kubectl -n <namespace> get secret <secret-name> -o jsonpath="{.data.password}" | base64 -d 

kubectl port-forward service/argocd-server -n <namespace> 8080:443

cd /home/mamonteiro/manuel.monteiro.github/kafka
k apply -f kafka-argocd.yaml

k get application -n argocd
k get application -n argocd -o yaml


argocd login localhost:8080 --insecure

get bootstrap-server from confluent kafka cluster 
