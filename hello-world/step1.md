Learn how to work with a kubernetes-cluster and deploy your first application.

`kubeadm init`{{execute HOST1}}
Switch to your node and tell it to join the cluster
`kubeadm join IP --token [TOKEN]`{{execute HOST2}}

Try using "kubectl get nodes"

Ready for deployments?
## GO FOR IT
EXAMPLE APP for Deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}


**Need help?**
## CHEATSHEET
Did you check if your kubernetes-components are in place?

Try:
`cp /etc/kubernetes/admin.conf $HOME/
chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}

Is your cluster ready?
Check which parts are installed with running:
`kubectl get pods --all-namespaces`{{execute HOST1}}

or try:

`kubectl get nodes`{{execute HOST1}}

Do you miss your network? Try:
`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`{{execute HOST1}}

