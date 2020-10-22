#### 版本下载
所有版本的下载地址参考：[https://cloud.tencent.com/developer/article/1581148](https://cloud.tencent.com/developer/article/1581148)<br />
<br />在解压目录下cmd中运行 ```SETUP.exe /UIMODE=Normal /ACTION=INSTALL``` 生成安装配置文件<br />
<br />生成的配置文件中需要修改的地方：<br />
<br />1. 注释 UIMode<br />
<br />2. 增加 IACCEPTSQLSERVERLICENSETERMS="True"<br />
<br />3. 增加 SAPWD="websoft9!"<br />
<br />4. 将 ```QUIET="False"``` 改为 ```QUIET="True"```<br />
<br />
<br />
<br />
<br />
<br />解压后，运行 ```SETUP.exe /UIMODE=Normal /ACTION=INSTALL```,按照正常选择安装参数后，直到准备安装（ready install）这一步，然后再所示目录下可找到对应的 ConfigrationFile.ini<br />

<a name="Kkm4M"></a>
#### 注意

1. 部分CPU核数不是2的n次方的机器安装会报错，2的0次方是1，1次方是2，2次方是4，3次方是8……只有不是2的n次方核数的CPU都会有问题，SqlServer2005 express with sp2/sp3/sp4的版本可以成功安装；另外，即便是CPU核数本来就是2的n次方的机器，比如2的0次方，1核机器，此版本的sqlserver即2005.90.1399版本的sqlserver在＞＝server2012系统上安装时报错，测试sp1/sp2/sp3/sp4版本的均可成功安装。
1. 2016以及以后，官方提供的是安装器（很小），而不是安装包
1. 安装包中最好包括 ssms（企业管理器）
