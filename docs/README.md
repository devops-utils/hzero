```shell
kubectl create ns storage

cd k8s-deploy/storage
kubectl apply -f mysql-pv.yaml -n storage
kubectl apply -f mysql-deploy.yaml -n storage

kubectl apply -f redis-pv.yaml -n storage
kubectl apply -f redis-deploy.yaml -n storage

kubectl apply -f minio-pv.yaml -n storage
kubectl apply -f minio-deploy.yaml -n storage

kubectl get po -n storage
kubectl get svc -n storage

mysql -h127.0.0.1 -uroot -p -P30001
root
mysql -h10.50.10.27 -uroot -p -P30001
root

cd hzero-resource
sh database-init.sh
# 数据初始化完成后需要进入hzero_platform数据库下面的hpfm_tenant表中，将tenant_id手动置为0
use hzero_platform
select * from hpfm_tenant;
update hpfm_tenant set tenant_id=0 where tenant_id=1;

GRANT ALL PRIVILEGES ON *.* TO 'Rexxar'@'%' IDENTIFIED BY 'Rexxar2022' WITH GRANT OPTION;
FLUSH PRIVILEGES;

kubectl create ns hzero

kubectl apply -f hzero-register.yaml -n hzero
kubectl apply -f hzero-config.yaml -n hzero
kubectl apply -f hzero-iam.yaml -n hzero
kubectl apply -f hzero-admin.yaml -n hzero
kubectl apply -f hzero-gateway.yaml -n hzero
kubectl apply -f hzero-oauth.yaml -n hzero
kubectl apply -f hzero-platform.yaml -n hzero
kubectl apply -f hzero-swagger.yaml -n hzero
kubectl apply -f hzero-file.yaml -n hzero
kubectl apply -f hzero-message.yaml -n hzero
kubectl apply -f hzero-import.yaml -n hzero
kubectl apply -f hzero-scheduler.yaml -n hzero
kubectl apply -f hzero-report.yaml -n hzero

kubectl get po -n hzero
kubectl get service -n hzero
kubectl get ingress -n hzero

http://gateway.7otech.com
http://register.7otech.com
http://gateway.7otech.com/swagger/swagger-ui.html

admin
Admin@123!

BUILD_BASE_PATH: / ,项目基础路径
BUILD_API_HOST: 网关地址
BUILD_CLIENT_ID: Oauth 认证客户端ID
BUILD_WEBSOCKET_HOST: websocket 地址
BUILD_CUSTOMIZE_ICON_NAME: ''，客制化图标名称
BUILD_MULTI_SKIN_ENABLE：true，UED皮肤切换，true为开启
BUILD_TOP_MENU_UNION_LABEL：false，是否按照标签并集查询(即只要存在一个标签即可), 默认否(false)
BUILD_TOP_MENU_LABELS：HZERO_MENU，首页菜单标签
BUILD_ENV_SIGN：''，环境标识
    
kubectl apply -f hzero-front.yaml -n hzero

http://front.7otech.com

kubectl delete -f mysql-deploy.yaml -n storage

sudo docker login --username=test hub.baidubce.com

sudo docker pull hub.baidubce.com/yanqian-tools/mysql:5.7.26
sudo docker pull registry.baidubce.com/yanqian-tools/mysql:5.7.26

sudo docker pull registry.baidubce.com/public/mysql:5.7.26
sudo docker pull mysql:5.7.26
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
