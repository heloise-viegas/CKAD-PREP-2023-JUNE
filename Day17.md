## 17-JULY-2023

## Day17

## Deployments/ Helm
**Blue Green/ Canary** 

### Blue Green Deployment
1. These cant be specified but can be implemented
2. New deployment is created along side old one
3. Old = Blue , New = Green
4. Initialy all traffic is routed to old/blue deployment , while test are run on new/green one
5. Once test are successful on green one then all traffic is routed to new one
6. best implemented with Istio
Steps:
7. deploy new /green & perform tests
8. route traffic to green/ new deployment by changing label on the service resource


### Canary Deployment
1. Small part is deployed as new 
2. Traffic is routed to both
3. Once test are successful on the canary then all old pods ae replaced with new ones 
Steps:
4. deploy new /green & perform tests
5. route some of the  traffic to green/ new deployment by changing label on the service resource
6. reduce traffic on canary by reducing pods to 1on canary
Drawbacks:
Cant define % of traffic to be distributed on pods, solution is to use Istio

Commands: 
- k scale deployment --replicas=1 deploy-name
- k delete deploy deploy-name

### Helm

1. is a package manager for kubernetes
2. specific data or versions can be updated in values.yaml file
3. helm cart = templates.yaml + values.yaml
4. chart.yaml stores information about the chart itself
5. each installation of the chart is called a Release

Commands :
6. helm list
7. helm uninstall release-name
8. helm pull
9. helm repo
10.helm search repo
 
