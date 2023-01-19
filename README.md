
# Init K8s experiment

A basic setup for K8s with k3d as a cluster managemnet, ArgoCd for the CD.


### Run current setup
` k3d cluster create -c k3d-k8s-exp.yaml && \
kubectl --context=k3d-k8s-exp apply -f hello-namespace.yaml && \
kubectl apply -f api-deploy.yaml && \
kubectl apply -f api-service.yaml `


### get logs of all running service
` kubectl get pods -n hello-namespace -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}' | while read -r pod; do kubectl logs -f "$pod" -n hello-namespace --all-containers; done ` 