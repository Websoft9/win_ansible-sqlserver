# Initial Installation

If you have completed the SQLServer deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:8161 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for SQLServer

## SQLServer Installation Wizard

1. 使用本地电脑的 **远程桌面**工具，登录到服务器
2. 打开桌面上的 **SQLServer企业管理器**工具，以【Windows】身份登录数据库
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-websoft9.png)
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw1-websoft9.png)

3. 依次展开【安全性】、【登录名】，找到默认登录名【sa】，右键【属性】，在弹出的窗口中点击【状态】，将登录选项选择【已启用】，也可以在【常规】选项卡里设置你的登录密码，点击确认保存.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw2-websoft9.png)

4. 接下来你就可以用 SQL Server 身份验证登录数据库了


> More useful SQLServer guide, please refer to [SQL Server Documentation](https://docs.microsoft.com/zh-cn/sql/sql-server)

## Q&A

#### 本部署方案数据库默认密码是多少？

为了安全考虑，本部署方案没有创建SQLServer的登录密码

#### SQLServer 服务启动失败？

请检查主机名是否正确