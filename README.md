# k8s

## Pods


## Deployments


## Services

* A `service` provides a single point of entry for accessing pods
* Since pods live and die, can you rely on their IP? This is why we need `services`
  * Pods can scale
  * Pods only get an IP once its scheduled
* A service gets a fixed IP and abstract pod IP addresses from consumers
* Load balances between pods
* Relies on labels to associate services to pods


### Service Types

* ClusterIP (default) - expose the service on a cluster-internal IP
    * Only pods within the cluster can talk to this service
* NodePort - expose the service on each Node's IP at a static port
    * Allocates a port from a range 30000 - 32767
    * Each node proxies the allocated port
    * External call, debugging purposes
* LoadBalancer - provision an external IP to act as a load balancer for the service
* ExternalName - maps a service to a DNS name
    * Allows a service to act as a proxy to external service
    * External service details are hidden from cluster

#### Clusterip Service in Action

* Create a deployment with label `app: my-nginx` assigned to pods
* Create a clusterIp service with `app: my-nginx` label and `my-nginx` as name
* Create a standalone pod without any label
* Exec into standalone pod add curl. Access deployment pods via clusterIp service dns name
    ```
    curl http://nginx-clusterip:8080
    ```

## Storage Options - Volumes

How do you store application state/data and exchange it between pods in k8s?

Volumes

* Pods and their file systems are ephemeral
* Volumes can be used to store sate/data and use it in a Pod
* A Pod can have multiple volumes attached to it
* Containers rely on mountPath to access a volumes
* k8s supports
    * volumes
    * Persistent Volumes
    * Persistent Volume Claims
    * Storage Classes

### Volumes

* volume reference to a storage location
* must have a unique name
* A volume mount refers a volume by name and defines a mountPath

## Volume Type

* emptDir - empty directory for storing transient data. Sharing data within containers in a pod. **Tied to the life of the Pod**
* hostPath - pod mounts to a node's file system.
* nfs - A NFS (Network File System) mounted into the Pod
* configMap - storing key value pairs and secrets are for storing sensitive data
* persistentVolumeClaim - provides Pod with more persistent storage option
* cloud - 

## ConfigMaps and Secrets


## Secrets


## Pulling it all together
