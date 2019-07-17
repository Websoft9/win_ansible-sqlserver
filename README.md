# ansible 操作 Windows 的前置工作：
## 受控端设置
1. Windows2008 以下的操作系统需要先升级 Powershell;
   远程连接到 Windows 服务器，以管理员权限运行 Powershell，执行以下命令：
   ~~~
    $url = "https://raw.githubusercontent.com/jborean93/ansible-windows/master/scripts/Upgrade-PowerShell.ps1"
    $file = "$env:temp\Upgrade-PowerShell.ps1"
    $username = "Administrator"
    $password = "Password"

    (New-Object -TypeName System.Net.WebClient).DownloadFile($url, $file)
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force

    # Version can be 3.0, 4.0 or 5.1
    &$file -Version 5.1 -Username $username -Password $password -Verbose
    ~~~
2. 完成升级后，还需要删除自动登录并将执行策略设置回默认值 Restricted：
    ~~~
    # This isn't needed but is a good security practice to complete
    Set-ExecutionPolicy -ExecutionPolicy Restricted -Force

    $reg_winlogon_path = "HKLM:\Software\Microsoft\Windows NT\CurrentVersion\Winlogon"
    Set-ItemProperty -Path $reg_winlogon_path -Name AutoAdminLogon -Value 0
    Remove-ItemProperty -Path $reg_winlogon_path -Name DefaultUserName -ErrorAction SilentlyContinue
    Remove-ItemProperty -Path $reg_winlogon_path -Name DefaultPassword -ErrorAction SilentlyContinue
    ~~~
3. WinRM 设置
   ~~~
    $url = "https://raw.githubusercontent.com/ansible/ansible/devel/examples/scripts/ConfigureRemotingForAnsible.ps1"
    $file = "$env:temp\ConfigureRemotingForAnsible.ps1"

    (New-Object -TypeName System.Net.WebClient).DownloadFile($url, $file)

    powershell.exe -ExecutionPolicy ByPass -File $file
   ~~~
   然后再执行：
   ```winrm set winrm/config/service '@{AllowUnencrypted="true"}'``` 
   ```winrm set winrm/config/service/auth '@{Basic="true"}'```

4. 在防火墙开放5985端口重新连接。

## 主控端设置
在 ansible 已安装的前提下，还需要安装 winrm 模块：
```pip install 'winrm>=0.3.0'```
```apt-get install libkrb5-dev```
```pip install kerberos```
```pip install paramiko PyYAML Jinja2 httplib2 six```

hosts 文件示例：
> [windows-server]
  40.121.53.104

  [windows-server:vars]
  ansible_ssh_user="admin"
  ansible_ssh_pass="123456"
  ansible_ssh_port=5985
  ansible_connection="winrm"
  ansible_winrm_server_cert_validation=ignore
