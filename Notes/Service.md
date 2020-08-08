# Services core concepts

A service provides a single point of entry for accessing one or more pods.

## Why we need services

- Pods are "mortal" and they live for short time

- You cant rely on a pod IP address staying the same

- Pods can be scaled horizontally so each pod get its own ip

- Pod gets an ip address after it has been scheduled (no way for clients to know schedule ahead of time)

## Role of services

![Services](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/RoleOfServices.JPG)

- Services abstract Pod IP Address from consumers

- Labels are used to associated pods with services

- Load balance between Pods

- Nodes kube proxy creates virtual IP for services

- Layer 4 TCP/IP

- Services are not ephemeral

- Create endpoints which is between the service and pods

![Calling Services](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/CallingServices.JPG)

## Types of Services

- Cluster IP - Expose the service on a cluster internal IP. Service IP is exposed internally in the cluster and only Pods can talk to the cluster.

![Cluster IP](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/ClusterIp.JPG)

- NodePort - Expose the service on each Node's (worker node) IP at static Port. External caller can now reach to the pods

![Node Port](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/NodePort.JPG)

- Load Balancer - Provision an external IP to act as a load balancer for the service. This is also useful when combined with cloud providers load balancer. Behing the scenes we have a node port and cluster IP services created. Each node proxies the allocated port

![Load Balancer](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/LoadBalancer.JPG)

- ExternalName - Maps a service to DNS name

![External Name](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/ExternalName.JPG)

## Port Forwarding

How can we access a Pod from out of kubernetes? it is through port forwarding

Commands

Expose a Pod port: By default pods and containers are only accessible with in the cluster by default. To expose use the following command **kubectl port-forward Pod/[name of thepod] [external port]:[internal port]**

Port forward for a deployment **kubectl port-forward deployment/[name of the deployment] [internal port]**

Port forward for a service **kubectl port-forward Service/[name of the service] [internal port]**

## Define Service

![Define Services](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/DefineServices.JPG)

![Service Definition](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/ServiceYaml.JPG)

![Service Definition](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/ServiceDns.JPG)

When load balance service type is applied, external ip is assigned

![When Load Balancer is defined](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Services/ApplyLoadBalancer.JPG)

## Commands

To create **kubectl create -f .\nginx.loadbalancer.yml --save-config**

To modify **kubectl apply -f .\nginx.loadbalancer.yml --save-config**

To Delete  **kubectl delete -f .\nginx.loadbalancer.yml --save-config**
To Delete  **kubectl delete service [name of the service]**
