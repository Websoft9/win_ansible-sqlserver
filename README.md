已完成：

* SQLServer2017Express

- SQLServer2016Express SP2

- SQLServer2014Express SP3

- SQLServer2012Express SP4



在解压目录下cmd中运行 ```SETUP.exe /UIMODE=Normal /ACTION=INSTALL``` 生成安装配置文件

生成的配置文件中需要修改的地方：

1. 注释 UIMode

2. 增加 IACCEPTSQLSERVERLICENSETERMS="True"

3. 增加 SAPWD="websoft9!"

4. 将 ```QUIET="False"``` 改为 ```QUIET="True"```





解压后，运行 ```SETUP.exe /UIMODE=Normal /ACTION=INSTALL```,按照正常选择安装参数后，直到准备安装（ready install）这一步，然后再所示目录下可找到对应的 ConfigrationFile.ini



版本对应关系：

| SQLServer版本            | Windows2008R2SP1 | Windows2012R2 | Windows2016 | Windows2019 | 测试平台    |
| ------------------------ | :--------------: | :-----------: | :---------: | :---------: | ----------- |
| SQLServer2012Express SP4 |        ✔         |       ✔       |      ✔      |      ✖      | windows2016 |
| SQLServer2014Express SP3 |        ✔         |       ✔       |      ✖      |      ✖      | windows2012 |
| SQLServer2016Express SP2 |        ✔         |       ✔       |      ✔      |      ✖      | windows2019 |
| SQLServer2017Express     |        ✖         |       ✔       |      ✔      |      ✖      | windows2019 |

