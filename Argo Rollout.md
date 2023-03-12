
## Why Argo Rollout

- Easy to understand(experiment with)
- Well-documented and maintained
- easy ti add (olug-and-play)
- Highly customisable

Installing Argo Rollouts

There are several ways to install Argo Rollouts: using a Kubernetes controller, via Helm, or using Kustomize, a popular tool for customizing Kubernetes objects.

Controller Installation
```
kubectl create namespace argo-rollouts
kubectl apply -n argo-rollouts -f https://github.com/argoproj/argo-rollouts/releases/latest/download/install.yaml
```

Installing Argo Rollouts with Helm

```
helm repo add argo https://argoproj.github.io/argo-helm
helm install my-release argo/argo-rollouts

```


Argo Rollouts extends the capabilities of the Kubernetes Deployment object, allowing teams to easily implement advanced progressive delivery strategies. We provided a quick tutorial that shows how this happens in three primary steps:

- You deploy a Rollout by applying a Rollout object in your Kubernetes cluster just like you would do with a Deployment. The Rollout manifest defines the specifics of the deployment strategy.

- Update the Rollout to reflect a new version of the application. The Rollout then executes the first phase of the deployment strategy for example, deploying a canary to 20% of the pods. 

- Promote the Rollout by making the new version of the application the primary production version.
We hope this will be useful as you adopt progressive delivery in your Kubernetes clusters. 



