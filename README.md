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
