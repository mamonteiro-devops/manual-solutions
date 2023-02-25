


Configure the Helm repository:

```
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
```


helm install \<release> \<chart> --namespace \<namespace> --create-namespace [--set \<other_parameters>]

The variables specified in the command are as follows:

- \<chart> A path to a packaged chart, a path to an unpacked chart directory or a URL.
- \<release> A name to identify and manage the Helm chart once installed.
- \<namespace> The namespace in which the chart is to be installed.

```
kubectl create namespace istio-system
helm install istio-base istio/base -n istio-system
helm ls -n istio-system
helm install istiod istio/istiod -n istio-system --wait
helm ls -n istio-system
helm status istiod -n istio-system
kubectl get deployments -n istio-system --output wide
```



(Optional) Install an ingress gateway:

$ kubectl create namespace istio-ingress
$ kubectl label namespace istio-ingress istio-injection=enabled
$ helm install istio-ingress istio/gateway -n istio-ingress --wait