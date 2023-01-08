# Kind
A tool for running local kubernetes clusters using Docker containers. 

## Installation
https://kind.sigs.k8s.io/docs/user/quick-start/#installation


### Creating single-node clusters

1. Boostrap a Kubernetes cluster using a pre-built node image.
````
kind create cluster --name single-node-cluster
````

2. Specify another image
````
kind create cluster --image=...
````

3. Create using a config yaml.
````
kind create cluster --config kind/single-node.yaml --name single-node-cluster
````

### List kind clusters
````
kind get clusters
````

### Interact with cluster
To interact with the cluster, specify the cluster name as a context in kubectl.

````
kubectl cluster-info --context kind-single-node-cluster
````
Note: Add <b>"kind-"</b> as prefix to your cluster name.


### Delete cluster or clusters
````
kind delete cluster --name kind-single-node-cluster
````
````
kind delete clusters single-node-cluster
````

### Creating multi-node clusters