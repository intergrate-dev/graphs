# quartz定时任务

## 概述

Quartz 是一个完全由 Java 编写的开源作业调度框架，为我们提供一种按照周期进行调度作业的机制。

## 使用场景

典型的使用场景，主要用来执行定时任务，比如说定时备份数据,订单超时自动取消,按时间段统计信息，定时发送信息，定时生成报表，自动更新静态数据，自动结账等等。随着业务数据量的逐渐增大，无论是大公司还是小公司分布式定时任务都是必不可少的。

例如：



## 原理分析

## 实践运用

### 单节点任务

#### 缺陷

### 分布式集群任务

#### quartz方案

quartz集群通过故障切换和负载平衡的功能，能给调度器带来高可用性和伸缩性。(伪分布式说法)
https://www.w3cschool.cn/quartz_doc/
https://www.cnblogs.com/liuyongzhi/p/12833088.html

https://blog.csdn.net/paditang/article/details/63250361

https://blog.csdn.net/aslan16/article/details/78413289
https://www.wandouip.com/t5i132986/


#### xxl-job

支持弹性扩容。但是xxl-job是基于数据库的，而elastic-job是基于zookeeper的。由于xxl-job是基于数据库的，所以在任务数量比较大的情况下，会增加数据库的压力。

#### elastic-job

### 分布式

见leanote

#### 原理

#### 分布式方案

