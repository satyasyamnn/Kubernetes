# Commands

## Create namespace

kubectl create namespace persistence

## Set namespace as the default for the current context

kubectl config set-context $(kubectl config current-context) --namespace=persistence

## To get PVC

kubectl get pvc
