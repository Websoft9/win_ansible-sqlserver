# 服务启停

使用由Websoft9提供的 SQLServer 部署方案，可能需要用到的服务如下：

## SQLServer

进入Windows的系统管理管理，将mssqlserver服务设置为自动启动或手动启动。参考下图：

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2008express/sqlserver-services-websoft9.png)

也可以使用cmd工具，通过命令的方式启动或关闭数据库

*   快速启动命令：net start mssqlserver
*   关闭服务：net stop mssqlserver
*   SQL Server 管理器打开的命令是：ssms

## IIS