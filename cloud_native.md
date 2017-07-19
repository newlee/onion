# Cloud Native

---

### 问题
软件不仅仅是代码或者二进制包，还有：

* 硬件、操作系统、网络...
* 主机失败、操作系统crash、网络中断...
* 硬件升级、操作系统升级...
* 分布式、高并发、高可用、高性能、可扩展
* ...

同时：

* 大多数开发人员不知道生产环境
* 大多数开发人员不具备运维技能（也不可能）
* 两种不同的性格，运维：稳定；开发：创新

### 怎么办？
DevOps！

但是：

* 很多技能不可能短时间改善
* 硬件部署周期
* ...

如果有了IaaS：

* Infrastructure Independency
* 开发人员不在关心基础设施实现，仅仅关心基础设施抽象
* 依然有独立的Ops team，但是是IaaS的Ops team
* 应用开发不在需要Ops team，ops role in development team

### 新的问题

基础设施只依赖抽象了，还有部署：

* puppet、chef、ansible
* 数据库、消息队列、ES、日志分析、Hadoop
* 还要考虑升级维护
* 还要考虑性能、高可用
* ...

同时：

* 大多少开发人员不具备第三方组件（如Hadoop）的安装、维护、优化技能
* 部署脚本难以测试
* ...

### 怎么办？

如果有了PaaS：

* Platform ？
* 开发人员不在关心第三方组件实现，仅仅关心第三方组件抽象
    * 我要一个MySql，于是就有了一个MySql！
* 应用不再需要部署脚本，仅仅需要一个Dockerfile
    * 开发环境、持续集成环境、生产环境使用相同的部署方式
* 部署前编排，作为开发过程的一部分
* 依然有独立的Ops team，但是是PaaS的Ops team

### 更近一步

现在我们走到哪了？

* Infrastructure/Platform Independency
* Immutable Container
* Version control everything
* No DevOps,dev is ops

然后我们可以：

* feature的全生命周期追踪和价值度量
* 弹性伸缩
* 业务、运维、运营数据的聚合与分析
* ...
