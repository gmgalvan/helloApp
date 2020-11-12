
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



tekton
Intall tekton on k8s
kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml
monitor teh isntallation
kubectl get pods --namespace tekton-pipelines --watch
install tekton cli
https://github.com/tektoncd/cli

create task
kubectl apply -f <name-of-task-file.yaml>
see task
tkn task describe echo-hello-world
run task
kubectl apply -f <name-of-taskrun-file.yaml>
see task run 
tkn taskrun describe echo-hello-world-task-run
see more details
tkn taskrun logs echo-hello-world-task-run
