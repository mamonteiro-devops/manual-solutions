
## Create a cluster with k3d 


- [] [example taken from the following page] https://learnk8s.io/kafka-ha-kubernetes

```
k3d cluster create kube-cluster \
  --agents 4 \
  --k3s-node-label topology.kubernetes.io/zone=zone-a@agent:0 \
  --k3s-node-label topology.kubernetes.io/zone=zone-b@agent:1 \
  --k3s-node-label topology.kubernetes.io/zone=zone-c@agent:2 \
  --k3s-node-label topology.kubernetes.io/zone=zone-c@agent:3

  kubectx  k3d-kube-cluster

  k3d cluster kist
  k3d cluster delete kube-cluster
f

```


## Create a cluster with k3d 
### Control-plane HA (a cluster with 3 control-plane nodes and 3 workers) 

  create a file called k8s-example-config.yaml with the following content

```
    kind: Cluster
    apiVersion: kind.x-k8s.io/v1alpha4
    nodes:
    - role: control-plane
    - role: worker
    - role: worker
    - role: worker
```

  Now execute the command:

```
    kind create cluster --config k8s-example-config.yaml
    kind get clusters

```

  Cluster Status 

```
{ clear && \
  echo -e "\n=== Kubernetes Status ===\n" && \
  kubectl get --raw '/healthz?verbose' && \
  kubectl version --short && \
  kubectl get nodes && \
  kubectl cluster-info; 
} | grep -z 'Ready\| ok\|passed\|running'

```

