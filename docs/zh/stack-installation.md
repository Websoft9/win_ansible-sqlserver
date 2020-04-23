# 初始化安装

在云服务器上部署 SQLServer 预装包之后，请参考下面的步骤快速入门。

## 准备

1. 在云控制台获取您的 **服务器公网IP地址** 
2. 在云控制台安全组中，检查 **Inbound（入）规则** 下的 **TCP:3389** 端口是否开启
3. 若想用域名访问 SQLServer，请先到 **域名控制台** 完成一个域名解析

## SQLServer 安装向导

1. 使用本地电脑的 **远程桌面**工具，登录到服务器
2. 打开桌面上的 **SQLServer企业管理器**工具，以【Windows】身份登录数据库
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-websoft9.png)
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw1-websoft9.png)

3. 依次展开【安全性】、【登录名】，找到默认登录名【sa】，右键【属性】，在弹出的窗口中点击【状态】，将登录选项选择【已启用】，也可以在【常规】选项卡里设置你的登录密码，点击确认保存.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw2-websoft9.png)

4. 接下来你就可以用 SQL Server 身份验证登录数据库了

> 需要了解更多 SQLServer 的使用，请参考官方文档：[SQL Server 技术文档](https://docs.microsoft.com/zh-cn/sql/sql-server)

## 常见问题

#### 本部署方案数据库默认密码是多少？

为了安全考虑，本部署方案没有创建SQLServer的登录密码

#### SQLServer 服务启动失败？

请检查主机名是否正确