## 30-JUNE-2023

## Day7

## Observability

**Observability** *Readiness/Liveliness probe, Monitoring, Logging*

### Readiness Probe
1. When pod is created it checks if the application in the pod is up and running before changing the state to Ready
2. initialDelaySeconds: specify delay if you are aware the app takes takes to start
3. periodSeconds: specify how often to probe the pod
4. failureThreshold: After a probe fails 3 times in a row, the probe will stop. To increase it specify this value

```yaml
readinessProbe:
  httpGet:
    path: api/ready
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 5
  failureThreshold: 3

```
```yaml
readinessProbe:
  tcpSocket:
    port: 8080
```
```yaml
readinessProbe:
  exec:
    command:
    - cat
    - /tmp/healthy
```

### Liveliness Probe
1. Continuously checks is the application is running, if it fails container is destroyed and recreated
2. Yaml is same as above except for the word **livelinessProbe**

Links :
- https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-a-tcp-liveness-probe

### Logging
1. Prints logs of application in the pod
2. for multi container pods we need to specify the container name          

**Command:**
k logs pod-name -c container-name

 Links :
- https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#logs


Questions :

- https://github.com/bmuschko/ckad-prep/blob/master/4-observability.md
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/e.observability.md
 
 
### Monitoring
1. Used to check metrics of the cluster
2. 1 metrics server = 1 Cluster
3. identifies pods using most/least cpu or memory

**Commands:**
k top nodes  ( node metrics)
k top pods   ( pod metrics)
