# Username and Password

These accounts are required for SQLServer image installation and configuration

## SQLServer

SQLServer administrator username: `sa`  
SQLServer administrator password: no default password, 参考下面的步骤设置密码  

1. 打开桌面上的 **SQLServer企业管理器**工具，以【Windows】身份登录数据库
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-websoft9.png)
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw1-websoft9.png)

2. 依次展开【安全性】、【登录名】，找到默认登录名【sa】，右键【属性】，在弹出的窗口中点击【状态】，将登录选项选择【已启用】，也可以在【常规】选项卡里设置你的登录密码，点击确认保存.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-winlogin-pw2-websoft9.png)

## Windows

* 主机地址：服务公网IP地址
* 连接方式：云控制台在线管理 或 远程桌面工具
* 管理员密码：创建服务器的时候自行设置，若不记得密码需要通过云控制台重置。
* 管理员账号：不同的云平台有一定的差异
   |  云平台   |  管理员账号   |
   | --- | --- |
   |  Azure   |  创建服务器的时候自行设置   |
   |  AWS，阿里云，华为云，腾讯云   |  administrator   |
   
## Linux

* Host Name: Internet IP or Public IP of your Instance
* Connect by: Online SSH on Cloud Console or SFTP/SSH tools on your local computer
* Password: It was set by yourself when created instance
* Username: Different Cloud Platform has differences
   |  Cloud Platform   |  Administrator Username   | Other |
   | --- | --- | --- |
   |  Azure   |  It was set by yourself when created instance   | [How to enable root access?](https://support.websoft9.com/docs/azure/server-login.html#sample2-enable-the-root-username) |
   |  AWS CentOS   |  centos   | [How to enable root access?](https://support.websoft9.com/docs/aws/server-login.html#sample2-enable-the-root-username) |
   |  AWS Ubuntu   |  ubuntu   | [How to enable root access?](https://support.websoft9.com/docs/aws/server-login.html#sample2-enable-the-root-username) |
   |  Alibaba Cloud, HUAWEI CLOUD, Tencent Cloud |  root   |

If don't remember the password of Linux, you should reset password on Cloud Console