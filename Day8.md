## 3-JULY-2023

## Day8

## Pod Design

**Pod Design** *Labels, Selectors, Annotations , Rolling Updates*

### Labels & Selectors
1. Labels give properties to objects
2. They can be used to filter and select certain objects 
3. Selector is the filtering condition that uses the labels
4. `=`,`==`,`!=` are allowed for selectors
```yaml
metadata:
  labels:
     environment: production
     app: nginx
```
```yaml
selector:
  matchLabels:
    label-name: label-value
```

Commands: 
 - kubectl label po nginx2 app=v2 --overwrite
 - k get po --show-labels
 - k run fe --image=nginx --labels=env=prod,team=shiny --annotations=contact='John Doe',commit=api
 -  k get po -l 'team in (shiny,legacy)',env=prod
 -  kubectl label po nginx1 nginx2 nginx3 app-   (to remove label app)
 -  kubectl get pods -o yaml | grep -C 3 'annotations:'
 
### Annotations
1. You can use either labels or annotations to attach metadata to Kubernetes objects
```yaml
metadata:
  name: annotations-demo
  annotations:
    imageregistry: "https://hub.docker.com/"
```
Links :
- https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/

  
Questions :
- https://github.com/bmuschko/ckad-prep/blob/master/5-pod-design.md#defining-and-querying-labels-and-annotations
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/c.pod_design.md#labels-and-annotations

### Rolling Updates
1. Replaces 1 pod at a time , destroy 1 redeploy 1. Zero downtime
2. Is the default strategy 
3. rollout : deploy pods in background          

Command:
 - k get deployment
 - k edit deployment deploy-name
 - kubectl rollout history deploy deploy-name
 - kubectl rollout undo deploy deploy-name
 - kubectl set image deploy deploy-name nginx=nginx:1.91
 - kubectl rollout status deploy deploy-name
 - kubectl rollout undo deploy deploy-name --to-revision=2

 Links :
- https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-intro/

Questions :
- https://github.com/bmuschko/ckad-prep/blob/master/5-pod-design.md#performing-rolling-updates-for-a-deployment
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/c.pod_design.md#deployments
