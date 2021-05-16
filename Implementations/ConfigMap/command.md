# Commands

## Create namespace

kubectl create namespace configmaps

## Set namespace as the default for the current context

kubectl config set-context $(kubectl config current-context) --namespace=configmaps

kubectl create configmap app-config --from-literal=DB_NAME=testdb --from-literal=COLLECTION_NAME=messages

kubectl exec db -it -- ls /config

kubectl exec db -it -- cat /config/DB_NAME && echo
