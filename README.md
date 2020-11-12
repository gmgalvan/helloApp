
docker build -t gmgalvan/hello-app .
docker run -d -p 8080:8080 gmgalvan/hello-app
docker push gmgalvan/hello-app


goolge cloud:
export PROJECT_ID=project-id
docker build -t gcr.io/${PROJECT_ID}/hello-app:v1 .
docker images
docker run --rm -p 8080:8080 gcr.io/${PROJECT_ID}/hello-app:v1
curl http://localhost:8080
gcloud auth configure-docker
docker push gcr.io/${PROJECT_ID}/hello-app:v1