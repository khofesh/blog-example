udemy microservices

## ErrImagePull, ErrImageNeverPull and ImagePullBackoff Errors

```shell
kubectl delete -f infra/k8s/
```

```yml
spec:
  containers:
    - name: posts
      image: khofesh/posts:0.0.1
      imagePullPolicy: Never
```

```shell
[fahmad@ryzen blog]$  pwd
/media/xfsfast/study/udemy-microservices/blog

eval $(minikube -p minikube docker-env)

docker build -t khofesh/posts:0.0.1 -f posts/Dockerfile ./posts
```

```shell
kubectl apply -f infra/k8s/
```

## common kubectl commands

```sh
kubectl exec -it posts -- sh
```

`kubectl exec -it posts sh` is deprecated

## access nodePort services

```sh
[fahmad@ryzen blog]$ kubectl describe service posts-srv
Name:                     posts-srv
Namespace:                default
Labels:                   <none>
Annotations:              <none>
Selector:                 app=posts
Type:                     NodePort
IP Family Policy:         SingleStack
IP Families:              IPv4
IP:                       10.96.97.204
IPs:                      10.96.97.204
Port:                     posts  4000/TCP
TargetPort:               4000/TCP
NodePort:                 posts  32442/TCP
Endpoints:                172.17.0.4:4000
Session Affinity:         None
External Traffic Policy:  Cluster
Events:                   <none>

```

```shell
[fahmad@ryzen blog]$  minikube ip
192.168.49.2
```

then, open `http://192.168.49.2:32442/posts` in browser

## skaffold

install

```sh
# For Linux x86_64 (amd64)
curl -Lo skaffold https://storage.googleapis.com/skaffold/releases/latest/skaffold-linux-amd64 && \
sudo install skaffold /usr/local/bin/
```

https://skaffold.dev/docs/quickstart/

```sh
minikube start --profile custom
skaffold config set --global local-cluster true
eval $(minikube -p custom docker-env)
```
