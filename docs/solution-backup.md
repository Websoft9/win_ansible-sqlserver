---
sidebarDepth: 3
---

# Backup & Restore

## Why

Users with experience in Cloud Server operation and maintenance understand the truth: "IT systems can't maintain 100% stability for a long time. Any system may fail, but the probability of failure is different and the degree of harm is different."

When system failure, we first seek the help of a professional to quickly repair and recovery it, but unfortunately, some failure cannot be solved smoothly or even in the expected time period.

Obviously, there is a backup is so important, it can guarantee that the system can be restored to the normal state through the existing backup file when the failure occurs, which means that the huge loss due to the unrecoverable can be avoided.

> Must develop the habit of backup, there is no luck

## How

From the specific backup object, due to the existence of four backup objects on the server: **operating system, environment software, database and application**, each object may have unpredictable failures that cannot be solved as expected.

Based on the backup object, we believe that the following two backup measures are necessary:

### Automation Backup for Instance

Automation Backups for Instance is using the **Snapshot** or **Cloud Server Backup Service** on your Cloud Platform, A snapshot is a full, read-only copy of a disk. You can take a snapshot of an OS or data disk to use as a backup, or to troubleshoot instance issues.

```
- Backup scope: All data on a Disk
- Backup effect: Very Good
- Backup frequency: Automatic backup per hour if you need
- Recovery methond: One key recovery on Cloud platform
- Skill requirement: Very easy 
- Automation or Manual: Fully automated on backup strategy
```

Different Cloud Platform's snapshot settings slightly different, refer to [Cloud platform backup solution](https://support.websoft9.com/docs/faq/tech-instance.html)

### Manual backup for application

Manual backup for application is based on the **Exporting source code and database of application** to achieve a minimized backup scheme.

```
- Backup scope: Source code and database of application
- Backup effect: Good
- Backup frequency: You can operate when you need
- Recovery methond: Import
- Skill requirement: Easy 
- Automation: manual
```
The general manual backup operation steps are as follows:

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