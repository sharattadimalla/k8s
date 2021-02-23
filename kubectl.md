
```
# check k8s version
kubectl version

# cluster info
kubectl cluster-info

# Get all k8s resources
kubectl get all

# creating pods imperative way
kubectl create my-nginx --image=nginx-alpine

# creating pods via yaml
kubectl apply -f nginx_pod.yaml

# deleting pods
kubectl delete -f nginx_pod.yaml

# Allow access from outside the k8s cluster
kubectl port-forward <resource_name> 8080:80

# describe a k8s resource
kubectl describe pod my-nginx

# get a resource in YAML
kubectl get pod my-nginx -o yaml

# run a command inside pod
kubectl exec my-nginx -- ls

# sh into a pod
kubectl exec -it my-nginx sh

# edit the yaml file
kubectl edit -f nginx_pod.yaml
```
