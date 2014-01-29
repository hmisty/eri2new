title: 数据库选型要考虑的若干问题
date: 2014-01-26 10:42:10
tags: 数据库工程
---

数据库选型是启动一个项目所需要重点考虑的事情之一。这里是High Scalability 2011年6月的一篇关于选择NoSQL的文章，列出了一系列很好的问题。其实这些问题不仅可用于选择NoSQL而且对于选择传统数据库和其他数据库也都是有参考价值的。

## 你从哪里开始？
- 是毫无历史包袱拖累的一个全新开始吗？
- 还是处于项目中段，而你正担心系统瓶颈？
- 或者你担心一旦部署就会遭遇扩展性问题？
- 抑或你正要将一个松耦合的服务添加到现存系统中去？
- 你有什么样子的资源、专业知识和预算呢？
- 你的痛点在哪里？为什么数据库不能挂掉对你是如此重要？是什么力量推动你要去做好这件事情？
- 你的优先级是什么？排好优先级。什么对你是至关重要的，什么务必要搞定？
- 你的风险有哪些？排列一下。不可用风险会比不一致更严重吗？

## 你正试图达成什么目的？
- 目的？
- 交付计划？
- 进行一些研究来明确一下，就像Facebook在他们为他们的站内消息系统做技术选型时所做的：

_Facebook选择了HBase因为他们监控了使用情况的数据并据此刻画出具体的需求：一个能够处理两类数据模式的系统。_

## 需要考虑的事情。。。你的问题
- 你需要构建一个客户系统吗？
- 访问模式：1) 为数不多的但随时间变化而多变的数据 2) 持续增加的但很少被使用到的数据 3) 大量的写 4) 高吞吐量 5) 顺序访问 6) 随机访问
- 需要扩展性吗？
- 可用性比一致性更重要吗？比延迟、事务、持久性、性能甚或易用性呢？
- 采用云计算还是租用机房？托管服务呢？诸如存储空间等资源的情况如何？
- 你能招到合适的人吗？
- 已经对于ORM的枯燥乏味备感厌倦？
- 需要存储那些需要快速并且频繁访问的数据？
- 会考虑采用更高级的抽象接口比如PaaS吗？

## 需要考虑的事情。。。钱
- 成本？有钱和没钱会关系到你的选择。你也许可以采用你所知的最佳技术。
- 廉价的扩展方法？
- 低运维成本？
- 无需系统管理员？
- 什么类型的许可证？
- 技术支持的费用？

## 需要考虑的事情。。。编程
- 灵活可变的数据类型和schema？
- 支持那些语言绑定？
- Web支持：JSON, REST, HTTP, JSON-RPC
- 内建存储过程支持？Javascript呢？
- 平台支持：移动端，工作站，云
- 事务支持：键值对，分布式，ACID，BASE，最终一致性，多对象ACID事务
- 数据类型支持：图，键值对，行，列，JSON, 文档，引用，关系，高级数据结构，巨型BLOB
- 喜欢简单的事务模型，只管更新就好了？全部放在内存里让它更快，而且大型系统可以由几个节点容纳

## 需要考虑的事情。。。性能
- 性能衡量：每秒IOPS，读，写，流式？
- 对于你的访问模式的支持：随机读/写；顺序读/写；大的、小的或者任意大小的块(chunk)
- 你正在存储频繁更新的数据吗？
- 高并发 还是 高性能？
- 限制了你所关心的负荷类型的问题在哪里？
- 在高并发负荷情况下高峰期QPS？
- 测试一下你独特的场景？

## 需要考虑的事情。。。特性
- 长程扩展性：支持跨多个数据中心吗？
- 安装、配置、运维、开发、部署、支持、管理、升级等等方面的简便程度
- 数据完整性：在DDL、存储过程、或者App中的情况
- 持久化(persistence)方案：Memtable/SSTable，Append-only B-tree, B-tree, On-disk linked lists, In-memory replicated, In-memory snapshots, In-memory only, Hash, Pluggable
- Schema支持：无schema，严格的，可选的，混合的
- 存储模型：嵌入式的，客户端/服务器模型，分布式的，in-memory的
- 支持搜索、第二索引、区间查询、adhoc查询、MapReduce吗？
- 热升级(hitless upgrades)？

## 需要考虑的事情。。。更多特性
- 可以调优的一致性模型？
- 可用的工具，产品成熟度？
- 快速扩展？快速开发？快速修改？
- 持久性(durability)？电源故障的情况下呢？
- 批量导入？导出？
- 热升级？
- 物化视图？
- 内建web服务器支持？
- 鉴权，授权，校验？
- 系统同步所需的持续后写？
- 可用性、防止数据丢失、备份及恢复的这些情况呢？
- 自动负载均衡、分区、重分区？
- 在线增删机器？

## 需要考虑的问题。。。供应商
- 公司长久么？
- 未来方向？
- 社区和支持列表的质量？
- 技术支持的及时响应？
- 他们如何处理故障？
- 合作关系发展的质量和数量？
- 客户支持：企业级SLA，付费支持，无


原文：[考虑NoSQL数据库时要思考的101个问题](http://highscalability.com/blog/2011/6/15/101-questions-to-ask-when-considering-a-nosql-database.html)