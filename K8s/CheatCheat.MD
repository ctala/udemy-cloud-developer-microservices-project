aws eks --region us-west-2 update-kubeconfig --name Udacity3 --profile ctala  


## APPLY COnfiguration
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

kubectl apply -f load-balancer.yaml

kubectl create -f configmap.yaml

## Interacting
kubectl get all

kubectl get pods
kubectl get pod PODNAME
kubectl logs PODNAME


kubectl exec -it pod/my-app-744cf947bf-tfrxb -- /bin/bash

kubectl describe services - show the services in the cluster
kubectl cluster-info - display information about the cluster