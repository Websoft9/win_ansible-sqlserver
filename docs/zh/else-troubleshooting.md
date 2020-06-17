# 故障处理

此处收集使用 SQLServer 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### 应用程序无法连接SQLServer数据库？

当您在安装应用程序的时候，首先保证数据库密码和用户名没有错，请确保登录界面服务器名称需要填写成您的`云服务器名称或(local)`。

服务器名称获取方法：“这台电脑”右键>“属性”中的“计算机名”。

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2008express/sqlserver-servnames-websoft9.png)

#### 错误：媒体集有 2 个媒体簇，但只提供了 1 个？

![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-backuperror001-websoft9.png)

问题原因：这个不是数据库自身的故障，而是备份的用法有问题。  
解决办法：去掉一个备份文件，每次备份在已有备份中覆盖即可
