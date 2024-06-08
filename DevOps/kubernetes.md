# Minikube

## Start minikube:
```bash
minikube start —vm-driver=qemu
````
```bash
minikube start --driver=docker --alsologtostderr -v=5
```

## Delete minikube
```bash
minikube delete
```
```bash
minikube delete --all --purge
```
```bash
# Kicbase images have not been deleted. To delete images run:
docker rmi gcr.io/k8s-minikube/kicbase:v0.0.34
```

# Dashboard
```bash
minkube dahboard
```

# Context
```bash
kubectl config current-context  # current context
```
```bash
kubectl config get-contexts     # all contexts
```



kubectl get nodes

minikube status

kubectl -n <namespace> exec postgresql-0 -- df -ah


kubectl config view
kubectl config get-contexts