```shell
kubectl create ns storage

cd k8s-deploy/storage
kubectl apply -f mysql-pv.yaml -n storage
kubectl apply -f mysql-deploy.yaml -n storage

kubectl delete -f mysql-deploy.yaml -n storage

sudo docker login --username=test hub.baidubce.com

sudo docker pull hub.baidubce.com/yanqian-tools/mysql:5.7.26
sudo docker pull registry.baidubce.com/yanqian-tools/mysql:5.7.26

sudo docker pull registry.baidubce.com/public/mysql:5.7.26
https://hub.baidubce.com
```

```shell
基础环境搭建
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6261&doc_code=6261
中间件安装
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6283&doc_code=6283
数据库初始化
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6290&doc_code=6290
后端应用部署
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6291&doc_code=6291
前端应用部署
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6292&doc_code=6292
环境基础配置
https://open.hand-china.com/document-center/doc/product/10067/10032?doc_id=6383&doc_code=6383

https://cloud.baidu.com/doc/CCE/s/Yjxppt74z
https://cloud.baidu.com/doc/CCR/s/Xkgvy3ixr
```
