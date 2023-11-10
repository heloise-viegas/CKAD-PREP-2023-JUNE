## 13-JULY-2023

## Day15

## Authentication & Authorization

**Authentication & Authorization** *Admission Controllers*

### Admission Controllers
1. Overcomes RBAC drawbacks
2. There a few which are enabled by default eg. namespace exists
3. Flow: authenticate > authorize > admission controllers 
4. Validating Adm controllers : validate requests and allow/deny it
5. Mutating Adm Controller : mutates the requests
6. Mutating are run first so that they are validated by the validating adm controller
7. Webhooks are custom Admission Controllers
      - deploy webhook server
      - host it 
      - create validating webhook configuration

*Commands:*
- kube-apiserver -h | grep enable-admission-plugins
- kube-apiserver --enable-admission-plugins=NamespaceLifecycle,LimitRanger 
- vi /etc/kubernetes/manifests/kube-apiserver.yaml

- kubectl create  secret  tls  --help
- k apply -f  webhook-deployment.yaml
- k apply -f  webhook-service.yaml
- k apply -f webhook-configuration.yaml


Links :
- https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/
- https://kubernetes.io/docs/reference/access-authn-authz/extensible-admission-controllers/#configure-admission-webhooks-on-the-fly
