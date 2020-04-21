Ansible Role: Tools
=========

本 Role 是主要用于在Windows上安装一些重要企业级应用工具，例如：dbForge, SQLbackupMaster等

## Requirements

运行本 Role，请确认被控端的Windows主机符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | Windows2008 或 以上|
| Powershell 版本 | 3.0 或以上  |
| Powershell 组件 |    |
| Runtime | WinRM, .Net4.0 或以上|


## Related roles

本 Role 在语法上不依赖其他 role 的变量，以下为例：

```
  roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_cloud, tags: "role_cloud"}
    - {role: role_tools, tags: "role_tools"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| tools_application_name | True, False | 布尔 | 否 |

注意： 

1. ×××××××
2. ×××××××

## Example

```
- name: Memcached
  hosts: all
  become: yes
  become_method: 
  vars_files:
    - vars/main.yml 

  roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_cloud, tags: "role_cloud"}
    - {role: role_template, tags: "role_template"}
```

## FAQ

1. 注意变量命名一定要符合role名称在前的规范
2. 尽量减少role之间的依赖关系
3. role默认变量设置要科学，即默认变量下语法是顺畅的