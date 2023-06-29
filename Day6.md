## 29-JUNE-2023

## Day6

## Multi Container Pods

**Multi Container Pods** *Init, Sidecar, Adapter , Ambassador *

### Sidecar
1. The sidecar pattern consists of a main application—i.e. your web application—plus a helper container with a responsibility that is essential to your application, but is not necessarily part of the application itself.
2. Eg. logging container attached that collects logs from main container and forwards to some location
### Adapter 
1. The adapter pattern is used to standardize and normalize application output or monitoring data for aggregation
2. Eg. Processes the logs from main container before forwarding to some location
### Ambassador 
1. The ambassador pattern is a useful way to connect containers with the outside world. An ambassador container is essentially a proxy that allows other containers to connect to a port on localhost while the ambassador container can proxy these connections to different environments depending on the cluster's needs.
2. Eg. One of the best use-cases for the ambassador pattern is for providing access to a database. When developing locally, you probably want to use your local database, while your test and production deployments want different databases again.

   ```yaml
   containers:
    - name: 
      image:
    - name:
      image 
                  

Links :
- https://matthewpalmer.net/kubernetes-app-developer/articles/multi-container-pod-design-patterns.html


Questions :

- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#resource-requests-and-limits
- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#defining-a-pods-resource-requirements


### Init Containers
1. When a POD is first created the Init Container is run, and the process in the Init Container must run to a completion before the real container hosting the application starts.           

```yaml
  initContainers:
  - name: init-myservice
    image: busybox:1.28
```
 Links :
- https://kubernetes.io/docs/concepts/workloads/pods/init-containers/#init-containers-in-use


Questions :

- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#resource-requests-and-limits
- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#defining-a-pods-resource-requirements
