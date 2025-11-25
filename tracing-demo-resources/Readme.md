# command
```shell
docker build -t trace-demo:v4 tracing-demo-resources/
kind load docker-image trace-demo:v4
kubectl create namespace trace-demo
kubectl apply -f tracing-demo-resources/deployment.yml
kubectl apply -f tracing-demo-resources/service.yml
kubectl apply -f tracing-demo-resources/instrument.yml
```