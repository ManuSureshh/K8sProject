

- Hope you have built the front and backend docker images.

<br>

![image](https://github.com/user-attachments/assets/c9881534-affd-45a2-b31e-28a0f6955f9d)

<br>

- Tag the Docker images and push to the DockerHub.

<br>

![image](https://github.com/user-attachments/assets/791f2c65-a38e-46cb-9b3d-aea060a3c0e1)
![image](https://github.com/user-attachments/assets/903e7c1d-eab2-4d1c-9ddd-f6cea167eba4)

<br>

![image](https://github.com/user-attachments/assets/9a818b2b-86d7-44ef-9c66-62bbd1f9517a)

<br>

## Create a Namespace for your project
```
kubectl create namespace 'namespace name'
```

<br>

![image](https://github.com/user-attachments/assets/0e37d31b-a57b-4b06-a38a-45fb67cfeede)

<br>

## Create a secret for DockerHub in order to pull the image from the private repositroy.
```
kubectl create secret docker-registry my-dockerhub-secret \
  --docker-server=https://index.docker.io/v1/ \
  --docker-username=<your-username> \
  --docker-password=<your-password> \
  --docker-email=<your-email> \
  --namespace=my-namespace

```

![image](https://github.com/user-attachments/assets/c47d445e-4ccb-4949-8024-d36496366fdd)

<br>



