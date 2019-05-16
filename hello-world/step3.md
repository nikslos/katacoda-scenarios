Learn how to work with a kubernetes-cluster and deploy your first application.

We want to deploy a workpress application. 
We will need two pods, one with a container running wordpress on an apache webserver and one with a container running a mysql database. 

## Deploy wordpress

Start with deploying the wordpress application

kubectl apply -f <deployment.yaml>`{{execute}}

Check your successful deployment with 
kubectl get deployments`{{execute}}	

## Deploy mysql

Deploy a mysql database 
`kubectl apply -f <deployment.yaml>`{{execute}}

## Connect the database with a service

Create a service to allow internal connections to the database.