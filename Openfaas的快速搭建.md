### 

# OpenFaas基于K8s的部署以及faas使用的案例演示

#### 

#### Faas 和无服务器架构

```
从IaaS、PaaS、SaaS到CaaS，再到火热的微服务架构，人们孜孜不倦的追求着将硬件资源抽象化，从虚拟机到容器，
再到现在的无服务器架构，FaaS是Functions as a Service的简称，代表业务方视角，而Serverless更多是
从部署的视角，其实描述的是类似的事情。
```

```
目前AWS的Lambda是无服务架构的代表，你可以很轻易的尝试.
```

#### `准备环境`

它可以部署在swarm集群或者k8s集群上，所以前提是你要有一个K8s集群，关于k8s集群的搭建，请参照 kubernetes 1.9.6 集群搭建。如果是用把k8s的各个组件，一个个作为服务去部署的化，你可能会踩无数的坑，但是对你理解k8s会有很大帮助。省事的话就用kubeadm。

 Deploy OpenFaaS  在master节点上执行：

开始gitclone项目:

```
$git clone https://github.com/openfaas/faas-netes
```

faas-nets是一个将faas组件部署在k8s集群的项目，内含一些yaml文件的定义。

权限、网关、prometheus等。

```
$cd faas-netes 
$kubectl apply -f ./namespaces.yml,./yaml
```

![5c81cff6eb77f](https://i.loli.net/2019/03/08/5c81cff6eb77f.png)

会创建出2个命名空间：**openfaas**和**openfaas-fn**



还有其他和faas有关的pod出来。

![5c81d03984830](https://i.loli.net/2019/03/08/5c81d03984830.png)



![5c81d52add941](https://i.loli.net/2019/03/08/5c81d52add941.png)



至此，所有的pod已经完全正常，平台已经完全加载出来到页面。

![5c81d9c4aad42](https://i.loli.net/2019/03/08/5c81d9c4aad42.png)



参考使用部署链接:https://www.2cto.com/net/201804/734810.html






