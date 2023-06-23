## 23-JUNE-2023

## Day1

## Core Concepts

### Kubernetes Architecture
Node/Minion : 
 1. physical/virtual machine where kubectl is installed
 2. worker machine where containers are launched

Cluster :
 1. Collection of Nodes (incase 1 node fails there is always a backup also helps with load)
 
Master :
 1. Node with kubectl configured as master
 2. Responsible for orchestration and management of the worker nodes

Componets :
Kubernetes installation contains :
 1. Api Server : front end that users and cmd can talk to or use to communicate with the cluster
 2. etcd : key value pairs stores all information of the nodes
 3. Scheduler : distributes work on containers accros  nodes
 4. Kubelet : agent present on each node to ensure it works as expected
 5. Controller : brain of k8s, notices when a node is down , takes desicions to bring up new containers
 6. Container runtime : software that runs containers

 																							   
| **Master**  | **Worker** |
|--|--|
| Api Server | Kubelet |
| etcd |  |
| Scheduler |  |
| Controller | Container Runtime |



### Pods
Abstraction of container
1pod  : 1container
multi container pods are supported eg. helper containers etc
Smallest unit of kubernetes deployment

**Commands**

pods ~ po
1. kubectl get po
2. kubectl run container-name --image imageName
3. kubectl apply -f pod.yaml
4. kubectl get pod <pod-name> -o yaml > pod-definition.yaml
5. kubectl edit pod <pod-name>

Links :
https://kubernetes.io/docs/concepts/workloads/pods/#using-pods
