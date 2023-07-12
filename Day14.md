## 12-JULY-2023

## Day14

## Authentication & Authorization

**Authentication & Authorization** *API  Groups*

### API  Groups
1. All resources are grouped into different API  Groups
2. Top level : Core & Named API group
3. Named : Contains Api group for each resource, there are verbs or actions defined for each resource

### Authorization
1. Provide specific access to users
2. Types : Node, ABAC, RBAC, Webhook, Always Allow, Always Deny
3. Node : access within the cluster
4. ABAC :  for every change , kubeapi server needs to be restarted
5.  Always Allow is the default mode
6. multiple modes can be set , they are applied in order in which they are specified

### RBAC
1. create user, create role for user, bind role to user
2. roles and role bindings are namespace scoped by default they are created for the default namespace
3. nodes,PV etc are cluster scoped , use cluste roles and cluster rolebindings for these


*Commands:*
- k auth can-i create deploy
- k auth can-i create deploy --as user-name
- k get pods --as user-name
- k create role developer --verb=list,create,delete --resource=pods
- k create rolebinding dev-user-binding --role=developer --user=dev-user
- k edit role 

Links :
- https://kubernetes.io/docs/reference/access-authn-authz/authorization/#authorization-modules
- https://kubernetes.io/docs/reference/access-authn-authz/rbac/#role-example
