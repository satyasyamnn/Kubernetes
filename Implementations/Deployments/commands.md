# Commands

## Create namespace

kubectl create namespace deployment

## Set namespace as the default for the current context

kubectl config set-context $(kubectl config current-context) --namespace=deployment

kubectl create deployment --image=httpd:2.4.38 web-server --dry-run=client -o yaml

kubectl get pods

kubectl scale deployment web-server --replicas=6

kubectl rollout history deployment web-server

kubectl edit deployment web-server --record

kubectl rollout status deployment web-server

kubectl rollout history deployment web-server

kubectl rollout undo deployment web-server

kubectl expose deployment web-server --type=LoadBalancer --port=80

watch kubectl get services

The StrategyType is RollingUpdate, which means when you specify a new desired state for the Deployment's Pods, the update will be incrementally rolled out to all of the Pods. The next note explains how quickly updates are allowed to roll out.

RollingUpdateStrategy has two parameters to control rolling updates by creating an upper bound and lower bound on the total number of Pods in the Deployment (for additional information issue kubectl explain deployments.spec.strategy.rollingUpdate):

    max unavailable: The maximum number of Pods that can be unavailable during the update.
    max surge: The maximum number of Pods that can be scheduled above the desired number of Pods.

There are several references to ReplicaSet. A ReplicaSet is a Kubernetes resource that can manage identical copies of Pods. Deployments use ReplicaSets for each version of the Deployment's desired state. You do not really need to know about the ReplicaSets since the Deployment abstracts away the complexity for you.
