# FAQ

#### SQLServer Express 是否包含自动备份功能？

不包含，但本部署包提供了一个免费的自动备份软件，参考本文档的 [SQLServer自动备份](/zh/solution-backup.md#sqlserver-express-自动备份)相关章节

#### SQL Server Management Studio 是否支持浏览器访问？

SQL Server Management Studio hosts a version of Microsoft Internet Explorer. This Web browser allows you to browse URLs, and view MSDN Library help topics without leaving SQL Server Management Studio. You can access the Web browser by pointing to Web Browser on the View menu, and then clicking Show Browser. 参考：https://docs.microsoft.com/en-us/sql/ssms/sql-server-management-studio-web-browser?view=sql-server-ver15


#### SQLServer各个发行版有什么功能区别？

以SQLServer2016为例，介绍 SQL Server的各个版本的差异

| 版本 | 定义                                                         |
| :-------------- | :----------------------------------------------------------- |
| Enterprise      | 作为高级版本，SQL Server Enterprise 版提供了全面的高端数据中心功能，性能极为快捷、虚拟化不受限制，还具有端到端的商业智能，可为关键任务工作负荷提供较高服务级别，支持最终用户访问深层数据。 |
| Standard        | SQL Server Standard 版提供了基本数据管理和商业智能数据库，使部门和小型组织能够顺利运行其应用程序并支持将常用开发工具用于内部部署和云部署，有助于以最少的 IT 资源获得高效的数据库管理。 |
| Web             | 对于 Web 主机托管服务提供商和 Web VAP 而言，SQL Server Web 版本是一项总拥有成本较低的选择，它可针对从小规模到大规模 Web 资产等内容提供可伸缩性、经济性和可管理性能力。 |
| 开发人员        | SQL Server Developer 版支持开发人员基于 SQL Server构建任意类型的应用程序。 它包括 Enterprise 版的所有功能，但有许可限制，只能用作开发和测试系统，而不能用作生产服务器。 SQL Server Developer 是构建 SQL Server 和测试应用程序的人员的理想之选。 |
| Express 版本    | Express 版本是入门级的免费数据库，是学习和构建桌面及小型服务器数据驱动应用程序的理想选择。 它是独立软件供应商、开发人员和热衷于构建客户端应用程序的人员的最佳选择。 如果您需要使用更高级的数据库功能，则可以将 SQL ServerExpress 无缝升级到其他更高端的 SQL Server版本。 SQL Server Express LocalDB 是 Express 的一种轻量级版本，它具备 Express 的所有可编程性功能，但在用户模式下运行，还具有零配置快速安装和必备组件要求较少的特点。 |

#### 是否可以关闭SQLServer的账号密码登录模式？

可以，关闭之后保留Windows身份登录模式即可

#### SQLServer Express 版本是否可以升级到 SQLServer 企业版？

可以，参考官方提供的方案：[升级到 SQL Server 的其他版本（安装程序）](https://docs.microsoft.com/zh-cn/sql/database-engine/install-windows/upgrade-to-a-different-edition-of-sql-server-setup?view=sql-server-ver15)

#### 是否可以修改SQLServer的源码路径？

不可以

#### 部署和安装有什么区别？

部署是将一序列软件按照不同顺序，先后安装并配置到服务器的过程，是一个复杂的系统工程。  
安装是将单一的软件拷贝到服务器之后，启动安装向导完成初始化配置的过程。  
安装相对于部署来说更简单一些。 

#### 云平台是什么意思？

云平台指提供云计算服务的平台厂家，例如：Azure,AWS,阿里云,华为云,腾讯云等

#### 实例，云服务器，虚拟机，ECS，EC2，CVM，VM有什么区别？

没有区别，只是不同厂家所采用的专业术语，实际上都是云服务器
