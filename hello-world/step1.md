Learn how to work with a kubernetes-cluster and deploy your first application.

`kubeadm init`{{execute HOST1}}

Switch to your node and tell it to join the cluster

`kubeadm join IP --token [TOKEN]`{{execute HOST2}}

Try using "kubectl get nodes"

## READY?
## DEPLOY YOUR FIRST APP
EXAMPLE APP for Deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}

## CHECK IF YOUR DEPLOYMENT WAS SUCCESSFUL:
Use:

`kubectl get pods`{{execute}}

Or use:

`kubectl describe pod`{{execute}}

##TROUBLESHOOTING

List your nodes

`kubectl get nodes`{{execute HOST1}}

Check all your kubernetes components:

`kubectl get pods --all-namespaces`{{execute HOST1}}

Details of your deployment:

`kubectl describe pod [PODNAME]`{{execute HOST1}}

**Need help?**
## CHEATSHEET
Did you check if your kubernetes-components are in place?

Try using:

`cp /etc/kubernetes/admin.conf $HOME/
chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}


Do you need a network? Try:

`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`{{execute HOST1}}

