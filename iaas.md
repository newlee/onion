IaaS : Domain Model
============

UBIQUITOUS LANGUAGE
---------
* Server
* Network
* Image
* Host


Subdomain
---------
![](https://rawgit.com/newlee/onion/master/iaas_subdomain.svg)


Core Domain
---------
![](https://rawgit.com/newlee/onion/master/iaas_core.svg)

Feature
---------
对Server，Network，Image的全生命周期管理（创建、使用／状态改变，删除），对Host状态监控（忽略硬件管理域）。

业务规则：

* 一个Nic一定有一个Port（否则无效网卡），Port可以单独存在。
* 一个Port只能同时被一个Server使用（即同一虚拟网卡不能同时在两个虚机上）
* 删除Server后，所使用的Port可以被其他虚拟机使用
* 当有Server使用Image时，Image不能被删除，否则Server无法重建
* Host发生硬件故障时，其上所有Server状态为异常销毁

暂不考虑规则：

* Host上是否能承载Server受该Host上所有Server占用资源限制
* 其他...

