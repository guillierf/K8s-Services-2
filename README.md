# K8s-Services-2
App: ToDo List

## Code from Kubernetes Webinar Series - Understanding Service Discovery
https://www.youtube.com/watch?v=NrzrpyMLWes

## Narrative for this demo
1. BUILD: build image locally on your laptop: docker build . -t <DOCKER_HUB_USER>/todo-app  (then push the image to registry)

2. DEPLOY: run app locally on your laptop: docker-compose up -d 

3. DEPLOY: run app on K8s cluster: kubectl create -f



## Build a Docker image from existing node.js source code and push it to Docker Hub. Replace DOCKER_HUB_USER with your Docker Hub username.
```
cd Build-Docker
docker build . -t <DOCKER_HUB_USER>/todo-app
docker login
docker push <DOCKER_HUB_USER>/todo-app
```

## Launch the app
```
docker-compose up -d
```

## Test the app
```
curl localhost:3000
```

## Deploy the app to Kubernetes
```
cd ../Deploy-Kubernetes
kubectl create -f web-pod.yml
kubectl create -f web-svc.yml
kubectl create -f db-pod.yml
kubectl create -f db-svc.yml
```

## Check that the Pods and Services are created
```
kubectl get pods
kubectl get svc
```


## Test the app by accessing the NodePort of one of the nodes.

```
kubectl get nodes
curl <NODE_IP>:<NODE_PORT>
```



## Useful links

ToDo app:
http://dreamerslab.com/blog/en/write-a-todo-list-with-express-and-mongodb/

Source code page:
https://github.com/dreamerslab/express-todo-example





