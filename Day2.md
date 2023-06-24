## 24-JUNE-2023

## Day2

## Application Design and Build

## Configuration

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
>      env:
>        - name :
>           valueFrom: 
>                configMapKeyRef:
>                      name: name-of-configmap
>                      key:     key-name

Multi env.

> envFrom:
>      - configMapRef:
>             name: name-of-configmap

        volumes:
         - name : vol-name
            configMap:
                     name: name-of-configmap
                     

**Commands**
configpmap~ cm
 1. kubectl get cm
 2. kubectl create cm cm-name --dry-run=client -o yaml > cm.yaml


Links :
https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#define-container-environment-variables-using-configmap-data
