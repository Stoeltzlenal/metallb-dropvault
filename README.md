# metallb-dropvault
loadbalancer-reverse proxy pour dropvault

# Lancement du metallb

$kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.3/manifests/namespace.yaml
$kubectl apply -f https://raw.githubusercontent.com/metallb/metallb/v0.9.3/manifests/metallb.yaml

# Create a secret for encrypted speaker communications
$kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"

# Apply metallb configmap
$kubectl apply -f metallb-configmap.yaml
 
# Test metallb with a nginx serv
open nginx-webtest folder and launch the follow requests

$ kubectl apply -f nginx-deployment.yaml
$ kubectl apply -f nginx-service.yaml




