configuration
=========

从gitlab仓库拉取配置并推送到linux远程服务器

Requirements
------------

没有其他需要

Role Variables
--------------

configuration_info: {
    # app_name,对应gitlab配置仓库中的项目目录名称
    app_name: "{{ app_name | default('') }}",
    # config_owner，定义配置文件在远程机器的owner,默认为ansible连接用户
    config_owner: "{{ config_owner | default(ansible_user) }}",
    # env, 对应gitlab配置仓库中的环境目录名称
    env: "{{ env | default('') }}",
    # config_addr，gitlab配置仓库地址，推荐ssh地址，拉取配置时可以不用验证
    config_addr: "{{ config_addr | default('') }}",
    dir_info: {
        # local_config_base_dir，在控制机拉取配置的临时目录
        local_config_base_dir: /tmp/ansible-config,
        # remote_config_dir，配置同步到远程机器的目录
        remote_config_dir: "{{ remote_config_dir | default('') }}"
    },
    action: {
        # config_before_cmd，同步配置前执行的操作
        config_before_cmd: "{{ config_before_cmd | default('') }}",
        # config_after_cmd，同步配置后执行的操作
        config_after_cmd: "{{ config_after_cmd | default('') }}"
    }
}

Dependencies
------------

没有其他依赖

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: configuration/configuration, env: prod, app_name: 'mds-ai',
            config_addr: 'git@gitlab.xpaas.lenovo.com:CBP-Application/MDS-AI-CONFIG.git',
            remote_config_dir: /tmp }
          或
    - hosts: servers
      roles:
         - { role: configuration/configuration, env: prod, app_name: 'mds-ai',
            config_addr: 'git@gitlab.xpaas.lenovo.com:CBP-Application/MDS-AI-CONFIG.git',
            remote_config_dir: /tmp, config_owner: 'xopsadmin' }

License
-------

BSD

Author Information
------------------

mail: niuhb2@lenovo.com
