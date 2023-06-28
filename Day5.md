## 28-JUNE-2023

## Day5

## Configuration

**Configuration** *Taints, Tolerations,Node Selectors, Node Affinity*

### Taints, Tolerations
1. Taints are for node & Tolerations are for pods
2. Pods which are tolerant will be scheduled on the node with the taint
3.  Doesn't instruct pod where to go but instructs Node which pod to accept

Taint effects: NoSchedule- wont schedule pods that are not tolerant
                       PreferNoSchedule- tries not to schedule pods that are not tolerant
                       NoExecute- wont schedule new  pods & removes existing pods that are                  			not tolerant

**Commands**

 1. k taint nodes node-name key=val:effect

                     

Links :
- https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/#concepts


Questions :

- 


### Node Selectors
1. Instructs pod where to go i.e opposite of Taints/Tolerants
2. Nodes should be created with label first then we can add Node selector to the pod
3. Limitation: Cant use Or / And etc as a selector

**Commands**

 1. k label nodes node-name key=val
Then in pod.yaml file add 

        nodeSelector:
           key: val 

                  

Links :
- https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#nodeselector


Questions :

- 
- 

### Node Affinity
1. Same as Node Selector but can use Or / And i.e. In/NotIn/Exists
2. Node affinity type specifies when the condition will be applied i.e. during scheduling/execution

 ```yaml
affinity:
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
        - matchExpressions:
          - key: keyname
            operator: In
            values:
            - antarctica-east1
            - antarctica-west1
```

Links :
- https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#node-affinity


Questions :

- 
- 
