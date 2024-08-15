
-------------------------------------------------
# what is this project all about:


-------------------------------------------------
## what problems it solves:
1- simplifies the design and reduce complexity through using less tools 
2- uses Gateway API instead of legacy Ingress

-------------------------------------------------
## utilized tools: 
1- kube vip as cloud provider
2- KIC(kong ingress controller)


-------------------------------------------------
## steps: 

### A- install and setup kube vip cloud provider

1- Install the kube-vip Cloud Provider

    kubectl apply -f https://raw.githubusercontent.com/kube-vip/kube-vip-cloud-provider/main/manifest/kube-vip-cloud-controller.yaml

2- Create a global CIDR or IP Range, for more info about how to define IP ranges check out KubeVIP official docs
    
    kubectl create configmap -n kube-system kubevip --from-literal cidr-global=192.168.0.220/29

instead of a local ip or local ip ranges, you can use your publicly available IP's as well , 

    kubectl create configmap -n kube-system kubevip --from-literal cidr-global=5.48.33.345/32,77,224,136,486/32

now when creating a service of type load balancer, the service will be assigned an IP from defined pools 



### B- install kong ingress controller

### C- define routes

### D- enjoy :)
