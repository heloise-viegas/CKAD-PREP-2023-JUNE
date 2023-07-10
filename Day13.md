## 10-JULY-2023

## Day13

## Authentication & Authorization

**Authentication & Authorization** *Kubeconfig*

### Kubeconfig
1. Contains credentials to access the cluster
2. Default path at $HOME/.kube/config
3. Contains: Clusters, Users, Contexts
4. Contexts map Users to Clusters
5. ADV: with Kubeconfig we don't need to specify certificate and credentials with every kubectl command
6. server details go in cluster section, user details/certificates go in users section
7. we can specify namespace in the context section
8. we don't need to create an object of this file, it is directly read by kube control command
9. we can also set default context in the file
10. certificate can be mentioned as data instead of file path
```yaml 
certificate-authority-data: base64 encoded data value
or
certificate-authority: /etc/kubernetes/pki/ca.crt 
```

*Commands:*
- k config view
- k config get-contexts
- k config use-context context-name
- k config view --kubeconfig=path to kubeconfigfile


Links :
- https://kubernetes.io/docs/tasks/access-application-cluster/configure-access-multiple-clusters/

