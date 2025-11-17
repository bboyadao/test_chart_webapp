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
kubectl apply -f keda/scale-webapp.yaml

```
