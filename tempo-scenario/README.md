## install tempo
```shell
kubectl create namespace tempo
helm -n tempo install tempo grafana/tempo-distributed -f tempo-scenario/tempo-distributed-values.yml

helm upgrade grafana -n grafana grafana/grafana -f tempo-scenario/all-datasources-values.yml

```

## install OpenTelemetry Operator for Kubernetes
```shell
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.19.1/cert-manager.yaml
kubectl apply -f https://github.com/open-telemetry/opentelemetry-operator/releases/latest/download/opentelemetry-operator.yaml
```

## install Alloy traces
```shell
kubectl create namespace alloy-traces
kubectl apply -f grafana-alloy-resources/alloy-traces-configMap.yml -n alloy-traces
helm install alloy-traces grafana/alloy -n alloy-traces -f tempo-scenario/alloy-traces-values.yml
```