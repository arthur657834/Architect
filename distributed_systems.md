分布式系统:
* 异构性: 不同语言，网络，系统等，一般由中间件
* 缺乏全球时钟
* 一致性
* 故障独立性
* 并发
* 透明性
* 安全性
* 可扩展性

阻塞I/O
非阻塞I/O
I/O复用
信号驱动I/O
异步I/O


IPC: inter-process communication 进程间通信
RPC: remote procedure call

数据中心:
* 严格一致性
* 持续一致性
* 顺序一致性
* 因果一致性
* 入口一致性

客户中心:
* 单调读一致
* 单调写一致
* 读写一致
* 写读一致

* 可用性
* 可靠性
* 安全性
* 可维护性

故障类型:
* 暂时
* 间歇
* 持久
* 崩溃
* 遗漏
* 定时
* 响应
* 任意

分布式提交:
### 两阶段提交
1.1 准备提交
1.2 提交阶段

### 三阶段提交
2.1 cancommit
2.2 percommit
2.3 docommit

### paxos
* proposer
* acceptor
* client
* learner

CAP:
* 一致性(consistency)
* 可用性(availability)
* 分区容错性(partition tolerance)

CA:
LDAP
集群数据库
单点数据库

实现方式:
2PC
缓存验证协议

CP:
1. 分布式数据库
2. 分布式锁

AP:
web缓存
DNS

实现方式:
到期/租赁
解决冲突
乐观

BASE: basicallu availability, soft state, eventual consistency

并发:
1. 资源利用率
2. 公平性
3. 便利性

缺点:
1. 安全性
线程间通信是通过共享访问字段及字段引用的对象，可能会导致
1. 线程干扰
2. 内存一致性错误

活跃度: 应用程序的及时执行能力
死锁: 
饥饿: 能访问到资源但不能执行对象
活锁: 

性能: context switch
上下文切换 上下文保存


解决方法:
同步
1. 同步方法
2. 同步状态

CORBA（Common Object Request Broker Architecture）通用对象请求代理架构是软件构建的一个标准。
1. 对象请求代理 （Object Request Broker，ORB）
2. 对象服务（Object Services）
3. 公共设施（Common Facilitites）
4. 应用接口（Application Interfaces）
5. 领域接口（Domain Interfaces）

SOA (Service Oriented Architecture)
面向服务架构，它可以根据需求通过网络对松散耦合的粗粒度应用组件进行分布式部署、组合和使用。服务层是SOA的基础，可以直接被应用调用，从而有效控制系统中与软件代理交互的人为依赖性。


