# Elastic Memcached
Distributed, Scalable, HA, cache.

## Feature
Elastic Memcached is intergral memcached and mcrouter on kubernetes.
### Mcrouter
Mcrouter is a memcached protocol router for scaling memcached deployments. It's a core component of cache infrastructure at Facebook and Instagram where mcrouter handles almost 5 billion requests per second at peak.
### Memcached
Memcached is simple yet powerful. Its simple design promotes quick deployment, ease of development, and solves many problems facing large data caches. Its API is available for most popular languages.
### kubernetes
Kubernetes provide scalable and HA easily.

## Pre-require
* kubernetes
* docker
* Go

## How to use
### Build Image
First build mcrouter image by yourself.
Notice that you can free to change config.json to setup cache cluster.
```
cd mcrouter
docker build -t daginwu/mcrouter .
docker push daginwu/mcrouter
```
### Apply Elastic Memcached to kubernetes
```
cd deploy
kubectl apply -f memcached-sts.yml
kubectl apply -f memcached-svc.yml
kubectl apply -f mcrouter-deploy.yml
kubectl apply -f mcrouter-svc.yml
```
### Test Elastic Memcached
```
kubectl port-forward svc/mcrouter 5000:5000
telnet localhost 5000
```
## License
Licensed under the MIT License

## Authors
Copyright(c) 2021 daginwu@gmail.com <daginwu@gmail.com>



