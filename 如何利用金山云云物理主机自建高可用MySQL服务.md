
# 如何利用金山云云物理主机自建高可用MySQL服务
在企业应用上云的过程中，关系数据库(主要是MySQL)是非常重要的服务。金山云提供了基于MySQL的关系型数据库(KRDS)，最大规格支持2000G SSD存储，48G内存。用户只需通过金山云控制台在数分钟之内就能快速创建和使用MySQL关系数据库服务，并可根据需要通过增加配置或者创建只读副本提升数据库服务处理能力。金山云提供数据库服务的高可用、数据备份和恢复、性能监控等能力。
但如果客户希望MySQL数据库服务具有更高的存储空间和处理能力时，可通过金山云提供的云物理机自建MySQL Master和Salve节点，并通过在云服务器上部署MySQL Router实现请求分发。此外，为了实现MySQL Router的高可用，可以利用Keepalived实现两个MySQL Router实例之间的启动切换（详细信息参考[通过Keepalived实现金山云自建服务高可用](https://blog.csdn.net/mqyang/article/details/102514372)。

本方案的架构示意图参考如下：
![金山云云物理主机自建高可用MySQL服务](https://raw.githubusercontent.com/ksc-sbt/ha-mysql/master/ha-mysql-architecture.png)

本文包括如下内容：
* 金山云网络规划
* 创建金山云云物理主机
* 配置MySQL主从服务
* 配置MySQL Router

# 1 金山云网络规划


