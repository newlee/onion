IaaS : Bounded Context & Context Map
============


User Case
---------

根据问题域业务规则，考虑以下场景：
* 创建Server时需要检查Image、Port是否可用
* 将Port attach到Server（动态添加网卡）时需要检查Port是否可用
* 销毁Server（包括异常销毁）时需要释放Port
* 删除Netplane/Subnet时需要检查Port是否被使用
* 删除Image时需要检查Image是否被使用
* Host检测到硬件故障时需要将Host上所有Server状态改变为异常销毁

Solution 1
---------
Single Bounded Context.

Solution 2
---------

![](https://rawgit.com/newlee/onion/master/iaas_bc.svg)

这里只展现Server和Network关系。

优点：
* Server和Network事实上相当复杂，而且会独立变化，比如考虑Server实现有虚拟机和容器；网络实现有OVS或者其他实现。分离两个上下文有助于独立变化。
* 在Server上下文建立Mapping，可以使得Server上下文不依赖外部其他上下文。
* 单向依赖

缺点
* Network信息重复在两个上下文，冗余而且需要同步。
* **值得注意的是，当前IaaS问题域在Server子域有NIC的概念，这个概念是否应该在Server子域存在？如果Server关注的不是网卡而是网络连接组（需要和其他哪里Server连接），我们会得到一个完全不同的解决方案**


