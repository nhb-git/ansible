php
=========

function:

1. 支持安装不同版本php

Requirements
------------

需要安装php的服务器能够访问到外网，方便yum在线安装依赖软件

Role Variables
--------------


```ansible
# project_info字典包含项目信息
project_info: {
  name: php,  # 项目名，安装目录前缀
  version: "{{ project_version }}", # 项目版本，安装目录后缀
  temp_dir: /tmp/ansible, # 项目执行过程用到的临时目录，执行完成后将删除
  base_dir: /usr/local/lenovosrv # 项目安装的基础目录
}

# centos_current_depends_software，在centos系统所要安装的软件和版本，php必须是列表中的最后一项
centos_current_depends_software: [
  { name: libiconv, version: _1_14 },
  { name: libmemcached, version: _1_0_18 },
  { name: mcrypt, version: _2_6_8 },
  { name: mhash, version: _0_9_9_9 },
  { name: php, version: "_{{ project_info.version.split('.') | join('_')}}" },
]

# redhat_current_depends_software和centos_current_depends_software类似
redhat_current_depends_software: [
]

software_info: {
  # yum 安装的基础包
  basic_software: [
  ],

  # centos 系统yum安装的基础包
  centos_software: [
  ],

  # 自定义安装软件信息
  depends_software: {
      php: {    # 软件类型
        _7_0_30: {    # 软件版本，可以是多个，格式必须是_开头，不同层级版本号之间用_分隔
          tar_name: php-7.0.30.tar.gz,    # 软件安装压缩包名
          unzip_dir_name: php-7.0.30,     # 软件压缩包解压后的名称
          install_cmd: ""                 # 软件安装命令
        },
      }
  }
}
```

Dependencies
------------

php安装包必须存在于files目录下

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
