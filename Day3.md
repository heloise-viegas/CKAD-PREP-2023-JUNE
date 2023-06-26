## 26-JUNE-2023

## Day3

## Configuration

**Configuration** *Secrets*

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
