### Install
```bash
helm repo add kedacore https://kedacore.github.io/charts
```

### RollOut
#### KedaCore
```bash
helm upgrade --install keda kedacore/keda \
  --create-namespace \
  --namespace keda
```

- Waiting at least 1 min.
#### Install Trigger HttpScaleObject 
```bash
helm install http-add-on kedacore/keda-add-ons-http\
  --create-namespace \
  --namespace keda \
  --set images.tag=canary
```

#### Apply ScaleObj
```bash
cat keda/http_so.yaml | kubectl replace --force -f -

```

### Test scale

```bash
hey -n 200000 -c 1000 \
  -H "Host: webapp.triptolocs.com" \
  http://localhost:8080/docs
```