## 24-JUNE-2023

## Day2

## Configuration

**Configuration**
*Understand ConfigMaps*

### Commands & Arguments
 1. Docker : cmd is replaced by arguments passed in docker run. entrypoint appends the docker run argument. 
 2.  Use cmd  and entrypoint in json to setup default value.
 
|Docker|K8s  |
|--|--|
|Entrypoint  | command: [""] |
| CMD | args: [""] |

command: [""] overwrites Entrypoint  
args: [""] overwrites CMD

ENV :
 1. Is an array
 2. ConfigMap and Secrest can be used here


### ConfigMap
1. can be accessed using envFrom ; or env: or volumes: 

   
Single env.

    env:
      - name :
        valueFrom: 
          configMapKeyRef:
             name: name-of-configmap
             key: key-name
          


Volumes 

        volumes:
         - name : vol-name
           configMap:
             name: name-of-configmap

 Multi env.

     envFrom:
        - configMapRef:
             name: name-of-configmap
                     

**Commands**

configpmap~ cm
 1. kubectl get cm
 2. kubectl create cm cm-name --dry-run=client -o yaml > cm.yaml


Links :
https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#define-container-environment-variables-using-configmap-data

Questions :
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/d.configuration.md#configmaps
  ![image](https://github.com/heloise-viegas/CKAD-PREP-2023-JUNE/assets/37453877/8d4d2361-cdeb-4136-a41e-1ae9917a8bbc)
- https://github.com/bmuschko/ckad-prep/blob/master/2-configuration.md#configuring-a-pod-to-use-a-configmap
  ![image](https://github.com/heloise-viegas/CKAD-PREP-2023-JUNE/assets/37453877/e00080c1-6923-4760-b9cd-c124a63f37d1)

