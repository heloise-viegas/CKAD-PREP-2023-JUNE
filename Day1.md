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
1. Abstraction of container
2. 1pod  : 1container
3. multi container pods are supported eg. helper containers etc
4. Smallest unit of kubernetes deployment

**Commands**

pods ~ po
1. kubectl get po
2. kubectl run container-name --image imageName
3. kubectl apply -f pod.yaml
4. kubectl get pod <pod-name> -o yaml > pod-definition.yaml
5. kubectl edit pod <pod-name>

Links :
https://kubernetes.io/docs/concepts/workloads/pods/#using-pods


### Replica sets
 1. Manages node failure
 2. Balances load
 3. Spread across multiple nodes in the cluster
 4. Has selector label unlike Replication Controller. Selector label allows Replica Set to manage pods which were not created as part of the replica definition file. 
 5. It ensures that at all times specified number of pods are available.

Labels and Selectors :
 1. Used to filter or select pods with specific labels. Basically an identifier for pods.

**Commands**

replicasets ~ rs
 1. kubectl get rs
 2. kubectl apply -f rs.yaml
 3. kubectl  replace -f rs.yaml (if count is edited in file)
 4. kubectl  scale --replicas=n -f rs.yaml
 5. kubectl  delete replicaset rs-name

Links :
https://kubernetes.io/docs/concepts/workloads/controllers/replicaset/#example



### Deployments
 1. Encapsulates pod and replica sets. Is used to apply various deployment strategies like rolling updates,  blue-green etc.
 2. Very similar to Replica Sets
 
 **Commands**
  1.  kubectl get all
  2. kubectl get deploy
  3. kubectl apply -f deploy.yaml

Links:
https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#creating-a-deployment


### Namespaces
 1. Separates resources eg. Environments
 2. Resources limits like CPU can be set for each namespace
 3. Within Namespace objects are referred directly using the object names
 4. Outside Namespace : svc-name.Namespace.svc.cluster.local

Resource Quota :
 1. Used to specify cpu limit and storage to namespace.

**Commands**
namespace ~ ns
 1. kubectl get ns
 2. kubectl config set-context $(k config current-context) --namespace=name


Links :
https://kubernetes.io/docs/tasks/administer-cluster/namespaces/#creating-a-new-namespace


Bonus :

kubectl expose pod redis --port=6379 --name redis-service --dry-run=client -o yaml


![image](https://github.com/heloise-viegas/CKAD-PREP-2023-JUNE/assets/37453877/c6c1dd62-8c64-4ef2-8b84-b4704c28d984)

