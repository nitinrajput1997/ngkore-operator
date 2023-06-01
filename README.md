# ngkore-operator

Initalize the operator:
```bash
operator-sdk init --domain ngkore.com --plugins helm
```

Create an API:
```bash
operator-sdk create api --group demo --version v1alpha1 --kind Ngkore --helm-chart <helm-chart> #path to helm chart
```

Install Custom Resource Definition:
```bash
make install
```

Build and push operator docker image:
```bash
export IMG=nitinrajput658/ngkore-operator:0.0.1
make docker-build docker-push IMG=${IMG}
```

Deploy operator:
```bash
make deploy IMG=${IMG}
```

Install Custom Resource:
```bash
kubectl apply -f config/samples/demo_v1alpha1_ngkore.yaml
```

### Uninstall

Delete Custom Resource:
```bash
kubectl delete -f config/samples/demo_v1alpha1_ngkore.yaml
```

Delete operator:
```bash
make undeploy
```
