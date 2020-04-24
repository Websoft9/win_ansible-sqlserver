# Parameters

The SQLServer deployment package contains a sequence software (referred to as "components") required for SQLServer to run. The important information such as the component name, installation directory path, configuration file path, port, version, etc. are listed below.

## Path

### SQLServer

以SQL Server 2014为例，集成包中包括 SQL Server 2014 数据库引擎和 SQL Server Management Studio Express，具体包括：

* 操作系统： Windows Server系统
* 软件版本： SQL Server2014 R2 SP2 Express Edition,SQL Server Management Studio, Microsoft .Net Framework 4.6,IIS7
* 软件目录： C:\Program Files\Microsoft SQL Server
* 数据库引擎数据目录：C:\Program Files (x86)\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2014/sqlserver2014-install-websoft9.png)

### 其他

除了 SQLServer Management Studio 之外，目前没有安装其他核心组件

## Ports

You can control(open or shut down) ports by **[Security Group Setting](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** of your Cloud Server whether the port can be accessed from Internet.

The following list ports maybe most useful for you:

| Name | Number | Use |  Necessity |
| --- | --- | --- | --- |
| TCP | 80/443 | HTTP/HTTPS to visit website | Optional |
| TCP | 1433 | Remote connect SQLServer | Optional |


## Version

You can see the version from product page of Marketplace. However, after being deployed to your server, the components will be automatically updated, resulting in a certain change in the version number. Therefore, the exact version number should be viewed by remote connection to your Server