nginx
=========

function:

1. 支持安装不同版本nginx

Requirements
------------

需要安装nginx的服务器能够访问到外网，方便yum在线安装依赖软件

Role Variables
--------------

```ansible
# project_info字典包含项目信息
project_info: {
  name: nginx,  # 项目名，安装目录前缀
  version: "{{ project_version }}", # 项目版本，安装目录后缀
  temp_dir: /tmp/ansible, # 项目执行过程用到的临时目录，执行完成后将删除
  base_dir: /usr/local/lenovosrv # 项目安装的基础目录
}
```

Dependencies
------------

nginx安装包必须存在于files目录下

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
    - hosts: servers
      roles:
         - { role: nginx, project_version: 1.16.0 }
         或
    - hosts: servers
      roles:
         - { role: nginx }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
