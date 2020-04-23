---
sidebarDepth: 3
---

# 备份恢复

## 为什么？

有服务器运维经验的用户都明白一个道理：“信息系统根本无法长时间保持100%稳定的状态，任何系统都可能会出现故障，只是故障出现的概率不同、危害程度不同而已”。

1. 工作几天的成果被误删了，怎么恢复？
2. 网站被黑客攻击面目全非，能复原吗？
3. 网站内容被改得乱七八糟，想要恢复到一个正常状态？ 

当故障发生之时，我们首先是寻求专业人士的帮助，快速诊断并处理故障，但不幸的是，有些故障无法在期望的时间周期内顺利的解决，甚至是无法解决。

显然，有一个备份及其重要，它可以保证出现故障之时可以通过已有的备份文件将系统恢复到正常的状态，意味着可以避免由于无法恢复而造成的巨大损失。

> 一定要养成备份的习惯，切莫存在侥幸心理

## 怎样做？

从具体的备份对象上看，由于服务器上存在：**操作系统、运行环境、数据库和应用程序**四个备份对象，每个对象都有可能出现不可预期、不可如期解决的故障。  

基于备份对象的性质，我们认为如下两种备份措施是必要的：

### 全局自动备份

所有的云平台都提供了全局自动备份功能，基本原理是基于**磁盘快照**：快照是针对于服务器的磁盘来说的，它可以记录磁盘在指定时间点的数据，将其全部备份起来，并可以实现一键恢复。

```
- 备份范围: 将操作系统、运行环境、数据库和应用程序
- 备份效果: 非常好
- 备份频率: 按小时、天、周备份均可
- 恢复方式: 云平台一键恢复
- 技能要求：非常容易
- 自动化：设置策略后全自动备份
```

不同云平台的自动备份方案有一定的差异，详情参考 [云平台备份方案](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

### 程序手工备份

程序手工本地备份是通过**下载应用程序源码和导出数据库文件**实现最小化的备份方案。

下面以列表的方式介绍这种备份：
```
- 备份范围: 数据库和应用程序
- 备份效果: 一般
- 备份频率: 一周最低1次，备份保留30天
- 恢复方式: 重新导入
- 技能要求：非常容易
- 自动化：无
```
通用的手动备份操作步骤如下：

1. 访问SQLServer企业管理器，在需要备份的数据库上点右键，选择任务->备份，弹出备份数据库窗口。 
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-backup-websoft9.png)
2. 根据备份向导逐步完成备份工作

### SQLServer Express 自动备份

SQL Server Express的数据库由于没有SQL Server Agent服务，所以也就不支持维护计划功能，自动备份数据库就成了一个十分麻烦的问题。

#### 如何实现SQLServer Express自动备份？

经过研究，我们建议采用第三方工具 [SQL Backup Master](https://www.sqlbackupmaster.com/)  实现自动备份。SQL Backup Master 是一款免费可靠的 SQL Server 数据库备份工具，主要特性:

* 支持完整备份,差异备份,事务日志备份
* 简单强大的计划任务
* 内置邮件通知
* 支持备份到本地/网络文件夹/网络存储
* 支持备份到FTP/SFTP/FTPS服务器
* 支持备份到Dropbox，Google Drive，Box，Amazon S3，OneDrive和Azure
* 支持操作系统: Windows 10, 8, 7, Vista 和 Windows Server 2008/2012/2016
* 支持SQL Server版本 : SQL Server 2017, 2016, 2014, 2012, 2008, 2005


#### SQL Backup Master使用教程

1. 从官网下载安装好 SQL Server Master ,双击运行程序.
2. 创建数据库备份任务
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak-websoft9.png)
3. 选择数据库,并连接数据库 
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak2-websoft9.png.png)
4. 选择需要备份的数据库,并进行设置
	![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak3-websoft9.png)
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak4-websoft9.png)
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak5-websoft9.png.png)
 5. 设置计划任务
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak6-websoft9.png)
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak7-websoft9.png)
    
 6. 保存设置
 	![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak8-websoft9.png)
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-bak9-websoft9.png)
    
####  备选方案

除了使用SQL Backup Master这个工具之外，也可以采用服务器系统的任务计划和备份数据库的存储过程来实现，参考下面三篇文章：

* [How to schedule and automate backups of SQL Server databases in SQL Server Express](https://support.microsoft.com/en-us/kb/2019698)
* [创建 SQL Server Express自动备份数据库功能](http://shiyousan.com/post/635612483753095970)
* [在windows server 2012中实现SQL SERVER EXPRESS自动备份数据库](http://shiyousan.com/post/635615192184858364)