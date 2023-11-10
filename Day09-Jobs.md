## 4-JULY-2023

## Day9

## Pod Design

**Pod Design** *Jobs, CronJobs*

### Jobs
( by default when the task is complete the pod will exit and restart again since restartPolicy is set to Always by default)
1. Runs for short duration
2. Runs instantly and once . Cant be scheduled
3. Set restartPolicy to Never 
4. Completions : makes sure 3 pods execute successfully
5. Parallelism: allows these many or less pods to be created together
eg: parallelism: 3 allows 3 or less pods to be created simultaneously

Links :
- https://kubernetes.io/docs/concepts/workloads/controllers/job/#running-an-example-job


### CronJobs
1. Same as jobs but can be scheduled to run at specific times

Links :
- https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/#example
 
Questions :
- https://github.com/bmuschko/ckad-prep/blob/master/5-pod-design.md
- https://github.com/dgkanatsios/CKAD-exercises/blob/main/c.pod_design.md#jobs
