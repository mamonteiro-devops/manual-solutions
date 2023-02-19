
## Create a cluster with k3d 


- [] [example taken from the following page] https://learnk8s.io/kafka-ha-kubernetes

```
k3d cluster create kube-cluster \
  --agents 3 \
  --k3s-node-label topology.kubernetes.io/zone=zone-a@agent:0 \
  --k3s-node-label topology.kubernetes.io/zone=zone-b@agent:1 \
  --k3s-node-label topology.kubernetes.io/zone=zone-c@agent:2
```

## Create a cluster with k3d 
### Control-plane HA (a cluster with 3 control-plane nodes and 3 workers) 

  create a file called k8s-example-config.yaml with the following content

```
    kind: Cluster
    apiVersion: kind.x-k8s.io/v1alpha4
    nodes:
    - role: control-plane
    - role: control-plane
    - role: control-plane
    - role: worker
    - role: worker
    - role: worker
```

  Now execute the command:

```
    kind create cluster --config k8s-example-config.yaml
```
