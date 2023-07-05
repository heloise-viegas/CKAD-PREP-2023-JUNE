## 5-JULY-2023

## Day10

## Services & Networking

**Services & Networking** *Services & Networking*

### Services
1. Allows pods to communicate with each other
2. Allows pods to be accessed outside the cluster 
3. NodePort : for external
4. ClusterIp : for internal , default
5. LoadBalancer : for load mgmt
TargetPort : it is the container/pod port
Port : Service port
NodePort : port on cluster that is connected to service port
6. Selector should be used to specify pods
7. 1 service can connect to multiple pods, by default it uses random load balancer algorithm
8. for pods in multiple nodes no additional changes are needed

Links :
- https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types
