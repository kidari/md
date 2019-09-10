# 1. RabbitMQ

## 1.1. 运行机制

![1560820698072](springboot_res/1560820698072.png)

exchange

- direct 直连型  点对点

- fanout 分发 广播 速度最快

  ![1560820839025](springboot_res/1560820839025.png)

- topic  有选择性的模式匹配

  模式匹配分配消息的路由键属性，将路由键和某个模式进行匹配，此时队列需要绑定到一个模式上。它将路由键和绑定键的字符串切分成单词，这些单词之间用点隔开。



## 1.2. RabbitMQ架构

RabbitMQ是一个分布式系统，这里面有几个抽象概念。

- broker：每个节点运行的服务程序，功能为维护该节点的队列的增删以及转发队列操作请求。
- master queue：每个队列都分为一个主队列和若干个镜像队列。
- mirror queue：镜像队列，作为master queue的备份。在master queue所在节点挂掉之后，系统把mirror queue提升为master queue，负责处理客户端队列操作请求。注意，mirror queue只做镜像，设计目的不是为了承担客户端读写压力。

![img](springboot_res/261319-20180912085847258-1555753723.png)

如上图所示，集群中有两个节点，每个节点上有一个broker，每个broker负责本机上队列的维护，并且borker之间可以互相通信。集群中有两个队列A和B，每个队列都分为master queue和mirror queue（备份）。那么队列上的生产消费怎么实现的呢？

### 1.2.1. 队列消费

![img](springboot_res/261319-20180912090110893-417617785.png)

如上图有两个consumer消费队列A，这两个consumer连在了集群的不同机器上。RabbitMQ集群中的任何一个节点都拥有集群上所有队列的元信息，所以连接到集群中的任何一个节点都可以，主要区别在于有的consumer连在master queue所在节点，有的连在非master queue节点上。

因为mirror queue要和master queue保持一致，故需要同步机制，正因为一致性的限制，导致所有的读写操作都必须都操作在master queue上（想想，为啥读也要从master queue中读？和数据库读写分离是不一样的。），然后由master节点同步操作到mirror queue所在的节点。即使consumer连接到了非master queue节点，该consumer的操作也会被路由到master queue所在的节点上，这样才能进行消费。

### 1.2.2. 队列生产

![img](springboot_res/261319-20180912090830511-1702198991.png)

原理和消费一样，如果连接到非 master queue 节点，则路由过去。

docker run -d -p 5672:5672 -p 15672:15672 --name myrabbitmq container_id

15672管理界面

guest guest

```java
@Configuration

@Bean
new Jackson2JsonMessageConvert
/**
 *自动配置原理
 * RabbitAutoConfiguration
 * 2.自动配置了连接工厂
 * 3.RabbitProperties
 * spring
 * 4.RabbitTemplate给RabbitMQ发送接受消息
 * 5.AmqpAdmin RabbitMQ系统管理功能组件
 *   AmqpAdmin:创建和删除Queue,Exchange,Binding
 * 6.@EnableRabbit + @RabbitListener监听消息队列的内容
 */
@EnableRabbit //开启基于注解的RabbitMQ模式

@RabbitListener(queues = "atguigu.news")

@Autowired
    AmqpAdmin amqpAdmin
    amqpAdmin.declareQueue(new Queue());
```

```properties
springboot.rabbitmq.host=
springboot.rabbitmq.username
springboot.rabbitmqpassword

```

将数据自动转为json发出去
