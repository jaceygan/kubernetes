# kubernetes
kubernetes revision

minikube doesnt work with virtualbox 7.0.8 for apple silicon. Use podman as workaround

podman machine init --cpus 2 --memory 2048 --rootful 
podman machine start
minikube start --driver=podman


# pod
kubectl create --save-config -f pod.yaml
kubectl apply -f pod.yaml
kubectl get pods
kubectl describe pods
kubectl delete pod <pod name>

# replicaset
kubectl create --save-config -f replicaset.yaml
kubectl apply -f pod.yaml
kubectl get replicaset # can use rs instead of replicaset
kubectl delete replicaset <replicaset name>

