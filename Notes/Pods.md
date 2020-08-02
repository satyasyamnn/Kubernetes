# Concepts of Pods

![PODS](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Pods.JPG)

Basic execution unit of a kubernets application. This is what is created and deployed. Containers are hosted in pod. Applications can be deployed to multiple containers in a pod. They can never span nodes.

Each Pod has IP Address in a Node.

    *Pod containers share the same network namespace (share IP/Port)

    *Pod containers have the same loopback network interface

    *Container with in Pod have unique port.

    *Container process need to bind to different ports with in a Pod

    *Ports can be reused by containers in seperate pods

Pods can be scaled horizontally by adding Pod replicas.

    *Replicas are copies of the Pod, kubernets can load balance between Pods.

    *Unhealthy Pod is removed and new healthy pod is added.

    *Pods have a life cycle. They live and die but never come back.

Volumes, memory which are shared across containers.

## Commands

*Command that helps in running an image in pod: **kubectl run myapp-nginx --image=[name of docker image]** - this is deprecated

*List all Pods: **kubectl get pods**

*List all resources: **kubectl get all**

*Expose a Pod port: By default pods and containers are only accessible with in the cluster by default. To expose use the following command **kubectl port-forward [name of thepod] [external port]:[internal port]**

*Delete a Pod **kubectl delete pod [name of the pod]**. If pods need to be completely deleted the corresponding deployment also has to be deleted.

*Delete a deployment **kubectl delete deployment [name of the deployment]**

*Interaction to container in POD **kubectl exec [name of the pod] -it sh**

## POD Health

Kubernetes relies of probes to determine health of a POD.

Types of probles

Liveness - used to determine if a pod is healthy and running as expected
Readiness - used to determine if a pod is ready to receive requests

How to check with in a container

Exec Action
TCP Socket Action
Http Get Action

Probes can have the following output

Success
Failure
Unknown

