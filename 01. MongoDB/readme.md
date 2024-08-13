
## Use the manifests to deploy the MongoDB onto the K8s cluster
```
kubectl apply -f  mongo-secret.yaml
```
```
kubectl apply -f mongo-pvc.yaml
```
```
kubectl apply -f mongo-storageclass.yaml
```
```
kubectl apply -f mongo-deployment.yaml
```
```
kubectl apply -f mongo-service.yaml
```

## Check the MongoDB status
```
kubectl get pods -n k8s
```
```
kubectl exec -it mongodb-584d7dc6d5-z747q -n k8s -- /bin/bash
```
- Check the DB connection,
  ```
  mongo mongodb-service:27017
  ```
  ```
  jobs
  ```
  ```
  fg %1
  ```
  ```
  exit
  ```


<br>

![image](https://github.com/user-attachments/assets/90a5285b-cf61-4586-8ce9-f99a617c32f2)
