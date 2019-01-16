timezone
=========

function:

1. 设定linux服务器时区,默认时区为上海
2. 增加时区检查定时任务

Requirements
------------

1. 没有特殊模块需要安装
2. role适用于Debian或者Redhat系列操作系统

没有需要特殊安装的模块

Role Variables
--------------

1. timezone，默认值是'Asia/Shanghai',值的格式为 洲/城市

Dependencies
------------

没有其他依赖

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: timezone }
         或
    - hosts: servers
      roles:
         - { role: timezone, timezone: 'Asia/Shanghai' }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
