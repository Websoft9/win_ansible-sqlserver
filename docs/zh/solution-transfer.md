# SQLServer 迁移

SQLServer 数据库存储目录更改:

1. 打开服务列表，先将 SQL Server (MSSQLSERVER) 服务停止；

	![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-1-websoft9.png)

2. 将默认的数据库文件拷贝到新的存放位置；
	```默认存放目录为：C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL```
    
3. 再次启动服务，打开SQL客户端，找到实例，右键实例选择属性；

	![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-2-websoft9.png)
    
4. 在属性中选择 数据库设置，修改数据的存放目录；

	![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/sqlserver/sqlserver-3-websoft9.png)
    
5. 最后重启 SQL Server (MSSQLSERVER) 服务，新建一个数据库测试是否在新的存放目录下生成该数据库；
6. 确保新目录生效后，再将原来的目录下的数据库文件删除。