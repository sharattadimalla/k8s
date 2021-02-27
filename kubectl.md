### kubectl commands

```
# check k8s version
kubectl version

# cluster info
kubectl cluster-info

# Get all k8s resources
kubectl get all

# creating pods imperative way
kubectl run my-nginx-standalone --image=nginx-alpine

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

# create or apply deployments
kubectl apply -f file.deployment.yaml
kubectl create -f file.deployment.yaml --save-config

# get deployments
kubectl get deployments

# list all deployments and their labels
kubectl get deployments --show-labels

# get deployment with a specific label
kubectl get deployment -l app=nginx

# delete deployment
kubectl delete deployment deployment-name
kubectl delete -f file.deployment.yaml

# scale deployment pods
kubectl scale deployment deployment-name --replicas=2
kubectl scale -f file.deployment.yaml --replicas=2

# describe deployment
kubectl describe deployment my-nginx

# get deployment by labels
kubectl get deployment -l app=my-nginx

# scale replicasets for a deployment
kubectl scale deployment my-nginx --replicas=4

```
