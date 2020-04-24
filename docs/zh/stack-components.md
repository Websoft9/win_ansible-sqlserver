---
sidebarDepth: 3
---

# 参数

SQLServer 预装包包含 SQLServer 运行所需一序列支撑软件（简称为“组件”），下面列出主要组件名称、安装路径、配置文件地址、端口、版本等重要的信息。

## 路径

### SQLServer

以SQL Server 2014为例，集成包中包括 SQL Server 2014 数据库引擎和 SQL Server Management Studio Express，具体包括：

* 操作系统： Windows Server系统
* 软件版本： SQL Server2014 R2 SP2 Express Edition,SQL Server Management Studio, Microsoft .Net Framework 4.6,IIS7
* 软件目录： C:\Program Files\Microsoft SQL Server
* 数据库引擎数据目录：C:\Program Files (x86)\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\DATA

![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2014/sqlserver2014-install-websoft9.png)

### 其他

除了 SQLServer Management Studio 之外，目前没有安装其他核心组件

## 端口号

在云服务器中，通过 **[安全组设置](https://support.websoft9.com/docs/faq/zh/tech-instance.html)** 来控制（开启或关闭）端口是否可以被外部访问。 

本环境可能需要开启的端口如下：

| 类型 | 端口号 | 用途 |  必要性 |
| --- | --- | --- | --- |
| TCP | 80/443 | 通过 HTTP/HTTPS 访问网站 | 可选 |
| TCP | 1433 | 远程访问 SQLServer | 可选 |

## 版本号

组件版本号可以通过云市场商品页面查看。但部署到您的服务器之后，组件会自动进行更新导致版本号有一定的变化，故精准的版本请登录云服务器查看