# Build and Push Intent Classifier Model Container

This document provides the commands to build the Docker image for the Intent Classifier model and push it to Docker Hub.

### Login to Docker Hub

`docker login`

### Build the Docker Image

Replace <dockerhub-username> with your Docker Hub username.

`docker build -t <dockerhub-username>/intent-classifier:latest .`

### Tag the Image (Optional Version Tag)

`docker tag <dockerhub-username>/intent-classifier:latest <dockerhub-username>/intent-classifier:v1`

### Push the Image to Docker Hub

Push the latest tag:

`docker push <dockerhub-username>/intent-classifier:latest`

Push the versioned tag:

`docker push <dockerhub-username>/intent-classifier:v1`

5. Verify the Image



Example request: curl -X POST http://localhost:6000/predict -H "Content-Type: application/json" -d '{"text":"I want to cancel my subscription"}'
docker pull <dockerhub-username>/intent-classifier:latest
