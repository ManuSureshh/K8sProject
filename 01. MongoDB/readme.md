


# Check the MongoDB status
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
