This is your first step.

## Task

We start with one "master" and one "node". Try:\n

`kubeadm init`{{execute}}\n
Switch to your node and tell it to join the cluster\n
`kubeadm join IP --token [TOKEN]`{{execute}}

Try using "kubectl get nodes"
HIDE THIS HERE:
`cp /etc/kubernetes/admin.conf $HOME/
chown $(id -u):$(id -g) $HOME/admin.conf
export KUBECONFIG=$HOME/admin.conf`{{execute}}
Is your cluster ready? Check which parts are installed with running:
`kubectl get pods --all-namespaces`{{execute}}
and
`kubectl get nodes`{{execute}}
Yay! Ready to deploy!\n
Do you miss your network? Try:
`kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"`{{execute}}
\n

EXAMPLE APP for Deployment:
`kubectl run http --image=katacoda/docker-http-server:latest --replicas=1`{{execute}}
