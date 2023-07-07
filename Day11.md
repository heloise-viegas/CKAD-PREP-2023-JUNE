## 6-JULY-2023

## Day11

## Services & Networking

**Services & Networking** *Ingress*

### Ingress
1. Allows services to be exposed externally using urls
2. is a load balancer
3. multiple services can be accessed using different endpoints and same base url
4. needs to be exposed via service 
5. requires controller and rules
6. needs SA & config map
7. resource needs to be in same namespace as services and deployments
8. rewrite Target : used when application doesnt have the path configured that is specified at ingress path
Eg. Ingres.yaml
```rules:
  - http:
      paths:
      - path: /pay
```
Note that the /pay URL path is what we configure on the ingress controller so we can forwarded users to the appropriate application in the backend. The target application is not configured with /pay path.
Without the rewrite-target option, this is what would happen:
```http://<ingress-service>:<ingress-port>/watch --> http://<watch-service>:<port>/watch```
Thus we use rewrite target : this internally replaces the ingress path with the application path
```
annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
```

Links :
- https://kubernetes.io/docs/concepts/services-networking/ingress/
