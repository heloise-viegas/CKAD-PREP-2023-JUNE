## 7-JULY-2023

## Day12

## Services & Networking

**Services & Networking** *Network Policies*

### Network Policies
1. For Networking here consider only Requests not Response
2. Ingress: Incoming to a pod Egress: Outgoing from a pod
3. These policies allow/block access to pods within the cluster
4. needs to be exposed via service 


Links :
- https://kubernetes.io/docs/concepts/services-networking/network-policies/#networkpolicy-resource


## Storage

**Storage** *PV & PVC*

### PV & PVC

 1. Volume needs to be  configured for each pod
 2.  To manage storage at central level PV is used
 3. PV & PVC is bound based on access modes, capacity and storage class name

Links :
- https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/#create-a-persistentvolume

Questions: 
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/g.state.md
- https://github.com/bmuschko/ckad-prep/blob/master/7-state-persistence.md

### Storage Classes
1. Used to create storage or volume blocks dynamically
2. When using Storage Class we dont need to create the PV, since PV will be created automatically when storage class is created 
- Create Storage Class
- Specify Storage Class in PVC
- When PVC is created the specified storage class creates a PV based on the provider mentioned in the storage class file

### Stateful Sets
1. Pods are deployed sequentially , when 1st pod is running then only next 1 is created
2. unique index for each pod i.e 0, 1 etc, First pod will always be 0
3. Even is MAster pod or pod 0 restarts it will have same index i.e 0
4. Same as deployment file except needs headless service and service name
5. Headless Service : each pod gets dns entry
 ### Storage 
 1. When a pod is created its respective Storage, PV and PVC is generated.
 2. If pod restarts it ensures it is connected to same pvc


 
