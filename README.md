# Running the hello-world-app

# Building the Docker image 

$ docker build -t mckafeh/hello-world-app:latest  .


# Test running the Docker container locally

$ docker run --name hello-world-app -d -p 8080:8080 hello-world-app:latest

# Publishing the Docker image to Docker Hub

$ docker login -u mckafeh

$ docker tag hello-world-app:latest mckafeh/hello-world-app:latest 

$ docker push mckafeh/hello-world-app:latest

# Runing the App on Minikube

kubectl create deployment hello-world-app --image=mckafeh/hello-world-app 

kubectl scale deployments hello-world-app --replicas=2

kubectl expose deployment hello-world-app --type=LoadBalancer --port=8080
