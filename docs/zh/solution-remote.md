# SQLServer 远程访问

除了远程桌面登录到服务器访问SQLServer之外，也可以通过本地访问SQLServer。  

但需要完成如下两个步骤：

## 服务器端：开启远程连接

本镜像默认完成了SQLServer远程访问的配置，但为了能够顺利访问，SQLServer所在的服务器还需完成如下两个设置：

1. 检查SQLServer数据库服务器中是否允许远程链接  
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-enableremote001-websoft9.jpg)
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-enableremote002-websoft9.png)

2. 为SQLServer服务器（MSSQLServer）配置相应协议。  
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-enableremote003-websoft9.png)
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-enableremote004-websoft9.png)
   
3. 在Windows服务器防火墙设置中开启远程访问：【控制面板】>【系统和安全】>【Windows防火墙】>【允许程序或功能通过Windows防火墙】  
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2014/sqlserver-firewall001-websoft9.png)
    ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2014/sqlserver-firewall002-websoft9.png)

4. 在云控制台中，开启服务器安全组的**1433端口**  

## 客户端：工具设置

设置完成上面的服务器之后，下面以Navicat为例来说明如何在本地电脑访问并管理SQLServer

1. [下载](http://www.navicat.com.cn/download)并安装Navicat

2. 在Windows服务器防火墙设置中开启远程访问（请见上一章）

3. 在Navicat->新建一个SQLServer连接，填写好连接参数（[不知道账号密码](/zh/stack-account.md)）
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver2008express/sqlserver2008-navicat-websoft9.png)

   > 端口1433不能更改，另外请确保云服务器控制台上的安全组打开了TCP:1433）

4.  点击【连接测试】，成功表明参数没有问题。

5.  点击【确认】后，进入数据库管理界面