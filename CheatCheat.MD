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
kubectl exec -it pod/reverse-proxy-6bdcfb6f67-g488q -- sh

kubectl exec -it  pod/my-app-front-5484bdbfdd-9rsv7
kubectl describe services - show the services in the cluster
kubectl cluster-info - display information about the cluster



curl -o aws-iam-authenticator https://amazon-eks.s3.us-west-2.amazonaws.com/1.18.9/2020-11-02/bin/linux/amd64/aws-iam-authenticator


aws eks --region us-west-2 update-kubeconfig --name Udacity2 --profile ctala


kubectl scale deployment.apps/my-app --replicas=2


kubectl autoscale deployment reverse-proxy --cpu-percent=50 --min=2 --max=10