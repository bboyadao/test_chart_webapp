### Add repo
```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

```
### Deployment
```bash
helm upgrade --install  nginx ingress-nginx/ingress-nginx --namespace test-project --create-namespace
```