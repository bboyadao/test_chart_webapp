### Deployment
```bash
kubectl -n test-project create secret generic webapp-sec\
  --from-env-file=webapp-sec.env\
  --dry-run=client\
  --save-config\
  -o yaml | kubectl apply -f -
```

```bash
helm upgrade --install  webapp webapp/ -f webapp/values.yaml  --namespace test-project --create-namespace
```