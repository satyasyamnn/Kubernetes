# Deployments Core Concepts

![Deployment and Replica Set](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Deployments.JPG)

A Deployment is a declarative way to manage pods using a replica set. A deployment manages Pods:

  *Pods are managed using replica sets

  *scales replica sets which scale pods

  *supports ZDD updates by creating and destryoing replicasets

  *provides rollback functionality

  *creates unique label that is assigned to the Replicasets and generated pods

  *YAML is very similar to replica sets

## Replica sets

A Replica set is a declarative way to manage Pods.

What happends if a Pod is destroyed? Deployments and replica sets ensure pods stay running and can be used to scale pods

Replica sets acts as a Pod controller
  
  *self Healing mechanism

  *Ensure that requested number of Pods are available

  *Provide fault tolerance

  *can be used to scale pods

  *relies on a POD template

  *No need to create POD directly

  *used by deployments

## Deployment Template

![Deployment YAML](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/DeploymentsYaml.JPG)

## Deployment Template Example

![Deployment YAML](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/DeploymentsYamlExample.JPG)

## Commands

Deployment using YAML file **kubectl create -f [name of the deployment file]**

Apply additional changes to Deployment using YAML file **kubectl apply -f [name of the deployment file]**

To get all deployments **kubectl get deployments**

To get information of all labels in deployment **kubectl get deployment --show-labels**

To get deploytment details of a specific label **kubectl get deployment -l app=nginx**

To delete a deployment **kubectl delete deployment [deployment name]**

Scale deployments **kubectl scale deployment [deployment-name] --replicas=[no of replicas]**

Scale deployment referencing YML file **kubectl scale -f [name of the file] --replicas=[no of replicas]**

Describing deployement **kubectl describe deployment [name of the deployment]**

Ex: spec:
        replicas: 3

## Post deployment

When deployment is done, we can see a deployment object, pods and replica set getting created. Replica set name is tagged with the pod name to differentiate other pods in the node.

Replica sets show the desired and the current state of deployment.

![Deployment YAML](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/DeploymentsOutputs.JPG)

## scaling

### To scale

kubectl scale -f .\yaml\nginx.deployment.yml --replicas=4

![Deployment Scaling](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/scale.JPG)

### To delete deployment using file

kubectl delete -f .\yaml\nginx.deployment.yml

All PODS in the replica set will be marked with status Terminating

![Deployment Delete](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Deployment.Delete.JPG)

## Summary of commands

![Deployment Commands](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Deployment.commands.JPG)