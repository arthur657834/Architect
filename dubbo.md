![dubbo](dubbo)

![dubbo_cluster](dubbo_cluster)

![dubbo_blance](dubbo_blance)

### 多注册中心
多注册中心是指同一个服务消费者，可以连接两个不同的服务注册中心，不同的服务注册中心中可以提供同一个服务的不同实现版本

### 服务降级
通过mock的配置，可以很好的实现dubbo服务降级。但是，仔细查看上面的例子会发现，IUser本身定义了两个接口，一个是新增用户，一个是根据id查询用户信息。对于根据id查询用户信息，在调用失败的时候返回null很好理解，可能是由于验证失败或者记录删除了，但是对于新增用户，可能就需要抛出具体的业务信息，否则程序无法处理后续的业务，包括页面弹出”添加成功“或者列表刷新的时候无法查看到最新的记录，这样体验将会非常不好。

SCA编程模式提供了三种方式的异步调用，它们分别是:
1. 单向调用方式。

2. 延迟响应方式。
> 延迟响应方式是指客户端在发出调用请求之后继续执行，但是经过一段时间之后，客户端再调用相应的方法去检索返回结果，并通过参数指定如何根据 调用的 结果而执行进一步动作。由于是异步调用方式，因此，在第一次发出调用请求的时候，服务端需要返回一个称为票据（Ticket）的对象。这个对象会作为第二 次发出检索结果请求时的一个参数。

3. 请求回调方式。

Dubbo中缓存策略:
1. lru 基于最近最少使用原则删除多余缓存，保持最热的数据被缓存。
2. threadlocal 当前线程缓存，比如一个页面渲染，用到很多portal，每个portal都要去查用户信息，通过线程缓存，可以减少这种多余访问。
3. jcache 与JSR107集成，可以桥接各种缓存实现。

