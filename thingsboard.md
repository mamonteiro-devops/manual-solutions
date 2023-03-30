

k3d cluster create multiserver --servers 1 --agents 9

helm repo add thingsboard https://midokura.github.io/thingsboard-ce-k8s

helm repo update                                                       
helm dep up

k create ns thingsboard

helm repo add thingsboard https://midokura.github.io/thingsboard-ce-k8s
helm install my-thingsboard thingsboard/thingsboard --version 0.1.4-rc.5 \
--namespace thingsboard \
--set cassandra.enabled=true

helm inspect values thingsboard/thingsboard

