# kubernetes
kubernetes revision

minikube doesnt work with virtualbox 7.0.8 for apple silicon. Use podman as workaround

podman machine init --cpus 2 --memory 2048 --rootful 
podman machine start
minikube start --driver=podman
minikube addons enable ingress

# pod
kubectl create --save-config -f pod.yaml
kubectl apply -f pod.yaml
kubectl get pods -o wide
kubectl describe pods
kubectl delete pod <pod name>

# replicaset
kubectl create --save-config -f replicaset.yaml
kubectl get replicaset //can use rs instead of replicaset
kubectl delete replicaset <replicaset name>

# deployment
kubectl create --save-config -f deployment.yaml
kubectl get deployment //can use deploy instead of deployment
kubectl delete deploymment <deployment name>

# storage
kc get pv/ pvc
kc create configmap <whatever name> --from-file=filename.conf
kc get cm
kc describe cm <cm name>

# others
kubectl exec -it <pod name> -c <container name in pod> -- /bash/bin
kubectl logs <pod name> -c <container name in pod>
kc get ingress/ service
kc delete ingress/ service <name>
kc get namespace


# environments
kc config get-contexts  
kc config use-context <context name>
kc get nodes

# maintenance
kc get nodes
kc drain <node name>
-- do whatever on the node
kc uncordon <node name>

# useful repos
UKHomeOffice/vault-sidekick for initContainer to pull down cert from Hashicorp vault
https://github.com/addamstj/kubernetes-course 
