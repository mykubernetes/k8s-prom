# k8s-prom

- prometheus目录：监控服务端，从node-exporter拉数据并存储为时序数据。  
  官方维护 https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/prometheus  
- k8s-prometheus-adapter目录：自定义指标,聚合apiserver,由此可支持任意Prometheus采集到的指标
- podinfo目录：测试使用的podinfo相关的deployment和service对象的资源配置清单。
- node_exporter目录：prometheus的agent端，收集Node级别的监控数据。
- kube-state-metrics：将prometheus中可以用PromQL查询到的指标数据转换成k8s对应的数据格式  
  https://github.com/kubernetes/kube-state-metrics  
  第三方维护 https://github.com/directxman12  
- grafana目录：展示prometheus获取到的metrics
- metrics-server目录： 提供Node和Pod的CPU和内存使用情况

安装步骤：  
1、# git clone https://github.com/mykubernetes/k8s-prom.git  
2、# kubectl create -f metrics-server/  
3、# kubectl create -f namespace.yaml  
4、# kubectl create -f node_exporter/  
5、# kubectl create -f prometheus/  
6、# kubectl create -f kube-state-metrics/  
7、# kubectl create -f k8s-prometheus-adapter/  
8、# kubectl create -f grafana/  
9、配置grafana 数据源 http://prometheus.prom.svc:9090  
10、部署模板  
推荐模板：  
• 集群资源监控：3119  
• 资源状态监控 ：6417  
• Node监控 ：9276  
#### 参考：https://github.com/stefanprodan/k8s-prom-hpa

