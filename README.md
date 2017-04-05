Onion
============

Onion尝试对IaaS和PaaS进行DDD领域模型的战略设计.包括问题域(Core Domain,Support Domain,Generic Domain)和解决方案域（Bounded Context,Context Map).

出于简化模型的考虑，模型有意忽略了硬件管理和Storage，以及网络部分忽略了Public Network.

Vision Statement
---------
作为IaaS，为用户提供Infrastructure（Server/Storage/Network）抽象，使得用户在不必关注底层物理硬件实现（Host/Switch/RAID)的情况下使用Infrastructure Resource.

作为PaaS，为用户提供Deployment Platform，使得用户在不必关注应用依赖（运行时如JVM/RVM，数据库，消息队列）的安装部署的情况下，编排和部署自己的应用/代码.

Problem Domain
---------

[IaaS](iaas.md)


Solution Domain
---------

[IaaS](iaas2.md)
