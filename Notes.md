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


SQLServer安装遇到的坑

## 1. Windows2019安装sqlserver2016-2019
1. 国内云平台的Windows中文操作系统默认编码是中文编码，ansible 无法识别，因此在安装前修改编码格式，安装后再修改回来：
	~~~
	- name: Set the region format to English United States
	  win_region:
    	unicode_language: en-US
      register: result
      when: sqlserver_language == "CHS"

	- win_reboot:
	  when: result.restart_required
	~~~
2. sqlserver2016-2019的下载工具用命令下载只能下载英文版的sqlserver，默认不处理，使用SSMS中文版管理，影响不大。
3. 不使用配置文件进行安装，先解压再用命令进行安装，此时会出现`XML文件错误`，解决方法：在 powershell 中运行：`Enable-WSManCredSSP -Role "Server" -Force`，或者在开启 WinRM 的脚本末尾添加该命令。


## 2. Windows2008安装sqlserver2008-2012
1. 升级 powershell 版本，脚本运行会持续卡住，实际上已经更新，需要手动重启或系统内关闭服务器并更新，此过程耗时较长，可使用控制台直接服务器查看进度。
2. 在 Windows2008 无法直接运行 powershell 脚本，需要先执行 `set-ExecutionPolicy RemoteSigned`，才能运行脚本。
2. 在 Windows 中，修改英文编码格式后导致中文编码的注册表文件缺失，此时安装sqlserver中文版会报错：**`性能计数器注册表配置单元一致性检查失败`**
	~~~
	由于我们使用的是简体中文版操作系统，所以要保证

	[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib] 中"Last Counter"和"Last Help"这两项的值与
	
	[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib\0804]中"Counter"和"Help"两项保存的最大值相同就可以了
	
	如果我们使用的是英文版操作系统，那就要保证
	
	[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib] 中"Last Counter"和"Last Help"这两项的值与
	
	[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib\009]中保存的最大值相同
	~~~
	**Windows中文版为中文编码时，同时包含0804和099两个注册表文件，更改英文编码格式会将0804文件夹下的注册表文件清空**
	**总结：使用 ansible 安装 sqlserver只能安装 sqlserver英文版数据库引擎 + 中文/英文版 SSMS**
	**在安装好sqlserver英文版数据引擎后，要先修改编码格式，再进行安装 SSMS，否则条件检查通不过**
