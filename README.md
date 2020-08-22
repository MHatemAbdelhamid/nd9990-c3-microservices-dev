# Udagram Image Filtering Application

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into 4 parts:
1. Frontend - Angular web application built with Ionic Framework
2. Backend USER RESTful API - Node-Express application
3. Backend Feed API - Node Epress application
4. Nginx proxy to isolate the front end from the backend services

Using Images and kubernetes the installation became just a few commands
### Prerequisite
1. The project depends on docker, kubernetes and mini kube
2. First install docker
    https://docs.docker.com/engine/install/ubuntu/
    https://docs.docker.com/desktop/
3. install minikube
    https://minikube.sigs.k8s.io/docs/start/
4. install kubectl: https://kubernetes.io/docs/tasks/tools/install-kubectl/


### installation

1. Go to udaqgram-deployment/k8s: run kubectl apply -f backend-feed-deployment.yaml -f backend-feed-service.yaml -f backend-user-deployment.yaml -f backend-user-service.yaml -f reverseproxy-deployment.yaml -f reverseproxy-service.yaml -f aws-secret.yaml -f env-configmap.yaml -f env-secret.yaml -f frontend-deployment.yaml -f frontend-service.yaml

And you are done

If you want to test it locally you can run 
    kubectl port-forward pod/reverseproxy pod name 8080:8080
    kubectl port-forward service/front end 8100:8100

Then in your browser run localhost:8100