Learn how do deploy a application on a kubernetes-cluster

## CHEATSHEET

We start with one "master" and one "node". Try:

`kubeadm init`{{execute}}\n
Switch to your node and tell it to join the cluster
`kubeadm join IP --token [TOKEN]`{{execute}}

Try using "kubectl get nodes"
`\n`HIDE THIS HERE:
`cp /etc/kubernetes/admin.conf $HOME/
chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}
`\n`Is your cluster ready? Check which parts are installed with running:
`kubectl get pods --all-namespaces`{{execute}}
and
`kubectl get nodes`{{execute}}
Yay! Ready to deploy!
Do you miss your network? Try:
`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`{{execute}}

EXAMPLE APP for Deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}
