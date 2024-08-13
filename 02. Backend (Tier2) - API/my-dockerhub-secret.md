## Once the Database server is ready, we then start deploying the API application.
- If you are having the Docker Image in a private dockerhub repository, we need to create a Secret for it.

```
kubectl create secret docker-registry my-dockerhub-secret \
  --docker-server=https://index.docker.io/v1/ \
  --docker-username=<your-username> \
  --docker-password=<your-password> \
  --docker-email=<your-email> \
  --namespace=my-namespace
```

