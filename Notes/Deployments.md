# Deployments Core Concepts

![Deployment and Replica Set](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Deployments.JPG)

A Deployment is a declarative way to manage pods using a replica set. A deployment manages Pods:

  *Pods are managed using replica sets

  *scales replica sets which scale pods

  *supports ZDD updates by creating and destryoing replicasets

  *provides rollback functionality

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
