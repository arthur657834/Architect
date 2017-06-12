安装zk集群
```sh 
mkdir -p /data/zookeeper-250-2181/
echo 1 > /data/zookeeper-250-2181/myid #一定要是数据存放目录
```
vi zoo.cfg
添加如下配置
maxClientCnxns=0
#数据保存目录
dataDir=/data/zookeeper-250-2181
#快照副本数量，默认为3
autopurge.snapRetainCount=5
#定时1个小时清除快照与事务日务
autopurge.purgeInterval=1
server.1=10.1.50.250:2888:3888
server.2=10.1.50.186:2889:3889
server.3=10.1.50.174:2890:3890

bin/zkServer.sh start/stop/status

安装3台

安装dubbo
```sh 
git clone https://github.com/alibaba/dubbo
mvn clean install package

tar zxvf dubbo-monitor-simple-2.5.4-SNAPSHOT-assembly.tar.gz
vi conf/dubbo.properties
dubbo.registry.address=zookeeper://10.1.50.250:2181?backup=10.1.50.186:2181,10.1.50.174:2181
./bin/start.sh
```

安装tomcat
将dubbo-admin-2.5.4-SNAPSHOT.war放到webapps
启动tomcat

访问地址:http://10.1.50.250:8080/dubbo-admin-2.5.4-SNAPSHOT/
