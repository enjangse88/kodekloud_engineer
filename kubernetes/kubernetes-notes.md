

#rollback to previous deployment
kubectl rollout undo deployment/deployment-name
#history
kubectl rollout history deployment/deployment-name
#status 
kubectl rollout status deployment/deployment-name

Create a pod named httpd-pod and a container under it named as httpd-container, use httpd image with latest tag only and remember to mention tag i.e httpd:latest and set the following limits:

Requests: Memory: 15Mi, CPU: 100m

Limits: Memory: 20Mi, CPU: 100m

apiVersion: v1
kind: Pod
metadata:
  name: httpd-pod
spec:
  containers:
    - name: httpd-container
      image: httpd:latest
      resources:
        requests:
          memory: "15Mi"
          cpu: "100m"
        limits:
          memory: "20Mi"
          cpu: "100m"



Create a cronjob named datacenter.
Set Its schedule to something like */10 * * * *, you set any schedule for now.
Container name should be cron-datacenter.
Use nginx image with latest tag only and remember to mention the tag i.e nginx:latest.
Run a dummy command echo Welcome to xfusioncorp!.
Ensure restart policy is OnFailure.

apiVersion: batch/v1
kind: CronJob
metadata:
  name: datecenter
spec:
  schedule: "*/10 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
            - name: cron-datacenter
              image: nginx:latest
              command:
                - /bin/sh
                - -c
                - echo 'Welcome to xfusioncorp!'
          restartPolicy: OnFailure
