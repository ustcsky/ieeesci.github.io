# Kubernetes学习笔记

参考教程：http://kubernetes.kansea.com/docs/whatisk8s/

Kubernetes [是一个用于容器集群的自动化部署、扩容以及运维的开源平台。](http://www.slideshare.net/BrianGrant11/wso2con-us-2015-kubernetes-a-platform-for-automating-deployment-scaling-and-operations)

使用Kubernetes，你可以快速高效地响应客户需求：

- 快速并且无意外的部署你的应用。
- 动态地对应用进行扩容。
- 无缝地发布新特性。
- 仅使用需要的资源以优化硬件使用。

我们希望培育出一个组件及工具的生态，帮助大家减轻在公有云及私有云上运行应用的负担。

#### Kubernetes 是:

- **可移植的**：公有，私有，混合，多重云（multi-cloud）
- **可扩展的**：模块化, 插件化, 可挂载, 可组合
- **可自愈的**：自动布置, 自动重启, 自动复制, 自动扩容

Kubernetes项目是Google在2014年启动的。Kubernetes构建在[Google公司十几年的大规模高负载运维经验](https://research.google.com/pubs/pub43438.html)之上，同时结合了社区中各项最佳设计和实践。

