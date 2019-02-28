# k8s-prom

- prometheus目录：部署Promethues Metrics API Server所需要的各资源配置清单。
- k8s-prometheus-adapter目录：部署基于prometheus的自定义指标API服务器所需要的各资源配置清单。
- podinfo目录：测试使用的podinfo相关的deployment和service对象的资源配置清单。
- node_exporter目录：于kubernetes集群各节点部署node_exporter。
- kube-state-metrics：聚合kubernetes资源对象，提供指标数据。
- grafana目录： 部署grafana,提供美观展示。

安装步骤：
1、先安装metrics-server
2、# git clone https://github.com/mykubernetes/k8s-prom.git
3、# kubectl create -f namespace.yaml
4、# kubectl create -f node_exporter/.
5、# kubectl create -f prometheus/.
6、# kubectl create -f kube-state-metrics/.
7、# kubectl create -f k8s-prometheus-adapter/.
8、# kubectl create -f grafana/.

#### 参考：https://github.com/stefanprodan/k8s-prom-hpa

