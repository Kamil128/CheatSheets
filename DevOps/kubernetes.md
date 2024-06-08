# Minikube

## Start minikube:
```bash
minikube start --vm-driver=qemu
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

## Dashboard
```bash
minkube dahboard
```

## Context
```bash
kubectl config current-context  # current context
```
```bash
kubectl config get-contexts     # all contexts
```
```bash
kubectl config use-context <context-name>
```
```bash
kubectl config set-context <context-name> --namespace=<namespace>
```
```bash
# Example
kubectl config set-context <contest-name> \
  --namespace=<namespace> \
  --cluster=<cluster-name> \
  --user=<user>
```

## Port Forward
```bash
kubectl port-forward service/<service-name> <local-port>:<remote-port>
```
```bash
# Example
kubectl port-forward postgresql-0 5430:5432
kubectl port-forward postgresql-0 5430:5432 --context=context-name
```

## Node
```bash
kubectl get nodes
```

## Pod
```bash
kubectl apply -f simple-pod.yaml  # create simple pod from simple-pod.yaml file
```
```bash
kubectl get pods  # get all pods
```

```bash
kubectl -n <namespace> exec postgresql-0 -- df -ah
```
### interactive shell
```bash
kubectl exec --stdin --tty <pod-name> -- /bin/bash
```
```bash
kubectl exec -it <pod-name> -- /bin/bash
```


# Config
```bash
kubectl config view
```

