php
=========

function:

1. 支持安装不同版本php

Requirements
------------

需要安装php的服务器能够访问到外网，方便yum在线安装依赖软件

Role Variables
--------------

temp_dir: 存放安装包、执行安装程序的临时安装目录，有默认目录。
project_name: 默认为php
project_version： 软件版本，默认7.0.30
project_base_dir： 软件安装的基础目录
project_install_dir： 软件安装目录
project_install_dir_softlink： 软件安装目录的软连接
project_install_cmd：php软件编译安装命令
redhat_depends_software： redhat系系统需要编译安装的依赖软件
depends_software：编译安装的依赖软件
basic_software： yum安装的软件列表
centos_software：centos系统yum安装的软件列表

Dependencies
------------

php安装必须存在于files目录下，php软件包名称必须是 php-版本号.tar.gz，解压后的目录名必须是 php-版本号

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: php, project_version: 7.0.30 }
         或
    - hosts: servers
      roles:
         - { role: php }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
