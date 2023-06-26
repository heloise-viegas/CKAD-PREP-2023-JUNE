## 26-JUNE-2023

## Day3

## Configuration

**Configuration** *Secrets,Security Context*

### Secret
1. used to store sensitive data in encoded form
   
Single value

    env:
      - name :
        valueFrom: 
          secretKeyRef:
             name: name-of-secret
             key: key-name
          
Volumes 

        volumes:
         - name : vol-name
           secret:
             secretName: name-of-secret

 Multi value

     envFrom:
        - secretRef:
             name: name-of-secret
                     

**Commands**
secret
 1. kubectl get secret
 2. kubectl create secret generic secret-name --from-file=file.txt


Links :
- https://kubernetes.io/docs/tasks/configmap-secret/managing-secret-using-kubectl/
- https://kubernetes.io/docs/concepts/configuration/secret/


### Security Context
1. used to specify pod user and its privileges
   
Pod level

    spec:
      securityContext :
        fsGroup: val
          OR
        runAsUser: val
          OR
        runAsGroup: val
        
        capabilities:
          add: ["NET_ADMIN", "SYS_TIME"]

 Container level

     shift the above snippet under container:
                     

**Commands**
 1. kubectl exec -it podname -- bin/sh
 2. whoami ---gives user
 3. ls -l ---specifies permissions


Links :
- https://kubernetes.io/docs/tasks/configure-pod-container/security-context/

Questions:
- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#configuring-a-pod-to-use-a-secret
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#secrets
- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#creating-a-security-context-for-a-pod
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#securitycontext
