# Create Simple Pod

## Create Docker file:
```Dockerfile
# Use the official Ubuntu 20.04 image
FROM ubuntu:20.04

# Set the command to keep the container running
CMD ["sleep", "infinity"]
```

## Build image
```bash
docker build -t my-ubuntu-python:v1 .
```

## Add image to minikube
#### Copy image to minikube
```bash
minikube image load my-ubuntu-python:v1
```

#### Or point to the local docker registry
```bash
eval $(minikube docker-env)
```

## Create simple deployment file
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-ubuntu-pod
spec:
  containers:
  - name: my-ubuntu-container
    image: my-ubuntu-python:v1
    command: ["sleep", "infinity"]
```

## Create simple pod
```bash
kubectl apply -f my-ubuntu-pod.yaml
```

## Check pod status
```bash
kubectl get pods
```

## Connect to pod
```bash
kubectl exec -it my-ubuntu-pod -- /bin/bash
```

## Delete pod
```bash
kubectl delete pod my-ubuntu-pod
```