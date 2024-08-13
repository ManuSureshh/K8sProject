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


[or]

- First you get the encoded values of username and password
  ```
  echo -n '{"auths":{"https://index.docker.io/v1/":{"username":"<your-username>","password":"<your-password>","email":"<your-email>","auth":"<base64-encoded-auth>"}}}' | base64 -w 0
  ```
  example: -
  ```
  echo -n '{"auths":{"https://index.docker.io/v1/":{"username":"sureshmanu126@gmail.com","password":"*******","email":"sureshmanu126@gmail.com","auth":"<base64-encoded-auth>"}}}' | base64 -w 0
  ```
```
eyJhdXRocyI6eyJodHRwczovL2luZGV4LmRvY2tlci5pby92MS8iOnsidXNlcm5hbWUiOiJzdXJlc2htYW51MTI2QGdtYWlsLmNvbSIsInBhc3N3b3JkIjoiQXZheWFAMTIzIiwiZW1haWwiOiJzdXJlc2htYW51MTI2QGdtYWlsLmNvbSIsImF1dGgiOiI8YmFzZTY0LWVuY29kZWQtYXV0aD4ifX19
```

- Use this encoded value into yaml file
```
apiVersion: v1
kind: Secret
metadata:
  name: my-dockerhub-secret
  namespace: k8s
type: kubernetes.io/dockerconfigjson
data:
  .dockerconfigjson: 
