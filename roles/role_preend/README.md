Ansible Role: Preend
=========

本 Role 是主要用于处理准备制作镜像前的准备工作，包括：安装一些特殊组件

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux|
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在语法上不依赖其他 role 的变量，但程序运行时需要确保已经运行: common。以下为例：

```
  roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_cloud, tags: "role_cloud"}
    - {role: role_template, tags: "role_template"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| template_applications | True, False | 布尔 | 否 |

注意： 
1. ×××××××
2. ×××××××

## Example

```
- name: Memcached
  hosts: all
  become: yes
  become_method: sudo 
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