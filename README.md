# Distributed System学习笔记

这是学习分布式系统设计的学习笔记。主要参考以下资料：
* [MIT 6.824: Distributed Systems](http://nil.csail.mit.edu/6.824/2018/index.html)
* [Distributed systems for fun and profit](http://book.mixu.net/distsys/index.html)
* [Designing Data-Intensive Applications : The Big Ideas Behind Reliable, Scalable, and Maintainable System](https://book.douban.com/subject/27154352/)

## 分布式系统概述

分布式系统是通过水平存储和计算资源达到高吞吐量和低延迟指标的。一般从扩展性（scalability）和性能（performance）来衡量系统的设计。

系统的水平扩展带来了两个问题：故障的发生频率越来越高，保持系统内部的状态越来越困难。通常使用可用性（availability）来衡量系统处理故障的能力，使用一致性来衡量系统保持内部状态同步的能力。

一般来说，当讨论一个分布式系统的时候，一般从可用性、数据一致性和性能三个方面来分析。高可用、高性能、强数据一致性之系统实现的目标。


### 可用性

可用性的衡量指标：`Availability = uptime / (uptime + downtime)`。一般用4个9、5个9等来描述。

```
Availability %	How much downtime is allowed per year?
90% ("one nine")	More than a month
99% ("two nines")	Less than 4 days
99.9% ("three nines")	Less than 9 hours
99.99% ("four nines")	Less than an hour
99.999% ("five nines")	~ 5 minutes
99.9999% ("six nines")	~ 31 seconds
```

### 性能

衡量系统性能有很多方式。比如延迟、吞吐量、QPS和TPS等。

### 数据一致性

数据一致性只多个复本之间数据的同步状况。如果在一次写入之后，所有复本之间的数据是同步的，那么就可以称为**强一致性**。如果在一次写入之后，副本之间的数据不是实时一致的，但是会在未来某一个时间保证一致，那么就为**弱一致性**。

## 笔记目录

* 数据存储和查询
* 复制 —— 提高系统性能和可用性
* 分片 —— 提高系统容量和降低单机负载
* 数据一致性
* 分布式实务
* 批处理
* 流处理
* 案例学习—— 一致性共识算法raft
* 案例学习——Spanner的事务模型和实现
* 案例学习——ZooKeeper

