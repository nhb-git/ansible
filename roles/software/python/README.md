python
=========

编译安装指定python版本

Requirements
------------

需要安装python的服务器能够访问到外网，方便yum在线安装依赖软件

Role Variables
--------------

```ansible
project_info: {
  name: python, # 项目名，安装目录前缀
  version: "{{ project_version }}", # 项目版本，安装目录后缀
  temp_dir: /tmp/ansible, # 项目执行过程用到的临时目录，执行完成后将删除
  base_dir: /usr/local/lenovosrv,  # 项目安装的基础目录
}

# centos_current_depends_software，在centos系统所要安装的软件和版本，php必须是列表中的最后一项
centos_current_depends_software: [
  { name: python, version: "_{{ project_info.version.split('.') | join('_')}}" },
]

redhat_current_depends_software: [
  { name: python, version: "_{{ project_info.version.split('.') | join('_')}}" },
]


software_info: {
  # yum 安装的基础包
  basic_software: [
    openssl-static
  ],

  # centos 系统yum安装的基础包
  centos_software: [
  ],

  # 自定义安装软件信息
  depends_software: {
      python: {  # 软件类型
        _3_6_5: {   # 软件版本，可以是多个，格式必须是_开头，不同层级版本号之间用_分隔
          tar_name: python-3.6.5.tar.gz,  # 软件安装压缩包名
          unzip_dir_name: python-3.6.5,  # 软件压缩包解压后的名称
          douban_source: "{{ douban_source | default('false') }}",  # 是否添加豆瓣源，默认不添加
          pip_conf_dir: "{{ ansible_env.PWD }}/.pip",   # pip配置文件目录
          # install_cmd 安装命令
          install_cmd: "./configure --prefix={{ project_info.base_dir }}/{{ project_info.name }}-{{ project_info.version }} 
                          --enable-optimizations && make && make install"
        },
      },
  }

}
```

Dependencies
------------

python安装包必须存在于files目录下

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: python, project_version: 7.0.30 }
         或
    - hosts: servers
      roles:
         - { role: python }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
