## deploy external-dns

- ExternalDNS is a Kubernetes addon that configures public DNS servers with information about exposed Kubernetes services to make them discoverable.
- ExternalDNS synchronizes exposed Kubernetes Services and Ingresses with DNS providers.


```
    argocd login localhost:8080

    k create ns external-dns

	argocd login <ALB address>

	kubectl create ns external-dns
	helm repo add bitnami https://charts.bitnami.com/bitnami
	helm install my-release bitnami/external-dns


	CLOUDFLARE_EMAIL=<CLOUDFLARE_EMAIL>
	CLOUDFLARE_API_TOKEN=<CLOUDFLARE_API_TOKEN>
	helm upgrade --install external-dns bitnami/external-dns \
	  --namespace external-dns --create-namespace \
	  --set provider=cloudflare \
	  --set cloudflare.apiToken=$CLOUDFLARE_API_TOKEN \
	  --set cloudflare.email=$CLOUDFLARE_EMAIL

    kubectl --namespace=external-dns get pods -l "app.kubernetes.io/name=external-dns,app.kubernetes.io/instance=external-dns"



```