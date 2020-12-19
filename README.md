# Udagram Image Filtering Application / Migration from Monolith to Microservices

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. Frontend - Angular web application built with Ionic Framework
2. Backend RESTful USER API - Node-Express application
3. Backend RESTful FEED API - Node-Express application

# Dependencies

## Repositories

The project has been divided into different repositories, each one of them with their own pipeline using TravisCI and DockerHub.

* User :
* * Github Repo : https://github.com/ctala/udagram-api
* * DockerHub : https://hub.docker.com/repository/docker/ctala/udagram-api
* Feed : 
* * https://github.com/ctala/udagram-api-feed
* * https://hub.docker.com/repository/docker/ctala/udagram-api-feed
* Reverse Proxy :
* * https://github.com/ctala/reverse-proxy
* * https://hub.docker.com/repository/docker/ctala/reverse-proxy
* Front-end :
* * https://github.com/ctala/udagram-frontend
* * https://hub.docker.com/repository/docker/ctala/udagram-frontend


## Kubectl

The ScreenSHots are under the screenshots folder.

```
NAME                                 READY   STATUS    RESTARTS   AGE
pod/my-app-8645b64cc5-8wtqt          1/1     Running   0          105s
pod/my-app-8645b64cc5-fmjgb          1/1     Running   0          19h
pod/my-app-feed-fc846fdd8-p7797      1/1     Running   0          28m
pod/my-app-front-5484bdbfdd-6tcp4    1/1     Running   0          20h
pod/reverse-proxy-6bdcfb6f67-zj8f5   1/1     Running   0          24h

NAME                        TYPE           CLUSTER-IP       EXTERNAL-IP                                                              PORT(S)          AGE
service/kubernetes          ClusterIP      10.100.0.1       <none>                                                                   443/TCP          6d16h
service/my-app-feed-svc     ClusterIP      10.100.241.118   <none>                                                                   8888/TCP         2d1h
service/my-app-front-svc    ClusterIP      10.100.153.95    <none>                                                                   80/TCP           24h
service/my-app-svc          ClusterIP      10.100.180.222   <none>                                                                   8888/TCP         2d16h
service/my-app-user-svc     ClusterIP      10.100.175.215   <none>                                                                   8888/TCP         5m53s
service/reverse-proxy-svc   LoadBalancer   10.100.215.50    a82702ff27be04e8bb33c76e5b97490d-474040424.us-west-2.elb.amazonaws.com   8080:31515/TCP   2d4h

NAME                            READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/my-app          2/2     2            2           2d17h
deployment.apps/my-app-feed     1/1     1            1           37m
deployment.apps/my-app-front    1/1     1            1           24h
deployment.apps/reverse-proxy   1/2     2            1           2d4h

NAME                                       DESIRED   CURRENT   READY   AGE
replicaset.apps/my-app-8645b64cc5          2         2         2       19h
replicaset.apps/my-app-feed-fc846fdd8      1         1         1       37m
replicaset.apps/my-app-front-5484bdbfdd    1         1         1       24h
replicaset.apps/reverse-proxy-6bdcfb6f67   2         2         1       2d4h

NAME                                                REFERENCE                  TARGETS         MINPODS   MAXPODS   REPLICAS   AGE
horizontalpodautoscaler.autoscaling/reverse-proxy   Deployment/reverse-proxy   <unknown>/50%   2         10        1          20s
```