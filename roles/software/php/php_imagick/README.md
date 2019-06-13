php_cphalcon
=========

安装php的扩展cphalcon。

Requirements
------------

1. 需要php安装在/usr/local/lenovosrv/php/目录下面
2. 需要php开启动态增加模块的功能

Role Variables
--------------

temp_cphalcon_dir: 存放第三方安装包的临时目录
cphalcon_name: 第三方压缩包的名字
php_conf: php.ini的路径

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: php_cphalcon }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
