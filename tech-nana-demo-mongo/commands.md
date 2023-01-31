
### Run current setup
`k3d cluster create --api-port 6550 -p "<HOST _PORT>:<APP_PORT>@loadbalancer" --agents 2 `
### RUN APP
` kubectl apply -f mongo-configmap.yaml && \
kubectl apply -f mongo-secret.yaml && \
kubectl apply -f mongo.yaml && \
kubectl apply -f mongo-express.yaml && \
kubectl apply -f ingress.yaml `