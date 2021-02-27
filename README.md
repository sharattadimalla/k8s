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

## Storage Options


## ConfigMaps and Secrets


## Secrets


## Pulling it all together

 