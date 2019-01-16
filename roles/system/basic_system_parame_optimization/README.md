basic_system_parame_optimization
=========

function:

1. 优化系统文件描述符打开数
2. 优化系统syn队列深度
3. 优化socket读写缓冲区最大值内存大小
4. 优化每个socket辅助缓冲区最大值内存大小
5. 开启time wait重复使用功能
6. 限制系统中time wait的最大数
7. 扩大对外连接所使用端口范围
8. 设定socket监听队列深度
9. 增大每个用户所能启动的最大进程数

Requirements
------------

1. 没有特殊模块需要安装
2. role适用于Debian或者Redhat系列操作系统

Role Variables
--------------

没有role变量需要设置

Dependencies
------------

没有其他依赖role

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: basic_system_parame_optimization }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
