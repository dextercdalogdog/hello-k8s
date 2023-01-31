
# Init K8s experiment

A basic setup for K8s with k3d as a cluster managemnet, ArgoCd for the CD.


### Run current setup
` k3d cluster create -c k8s-exp.yaml && kubectl apply -f api.yaml `


### get logs of all running service
` kubectl get pods -n default -o jsonpath='{range .items[*]}{.metadata.name}{"\n"}' | while read -r pod; do kubectl logs -f "$pod" -n hello-namespace --all-containers; done ` 