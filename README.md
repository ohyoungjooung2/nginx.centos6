Role Name
=========
nginx.centos6

This role nginx support for only centos6 distros(CentOS6.x)

Requirements
------------
None

Role Variables
--------------


defaults/main.yml
--------------

  os_update: false # os_update true update os updates(centos6.x)
  
  nginx_cert_config: false #private TLS cloud be installed by setting "true" or "--extra-vasr="nginx_cert_config=true" option.
  
  os: centos # This is used for templates/nginx.repo.j2
  
  centos_version: 6 # This is used for template/nginx.repo.j2. In the furture, CentOS7 cloud be supported.
  
  daemon_name: nginx #nginx daemon_name
  
  server_name: "localhost" #cloud be changed for your domain or ip by setting --extra-vars

vars/main.yml
--------------

  - key_file: /etc/nginx/ssl/nginx.key #private tls key
  - cert_file: /etc/nginx/ssl/nginx.cert #private tls cert
  - config_file: /etc/nginx/conf.d/default.conf #default vhost


  


Dependencies
------------
  None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         #- { role: username.rolename, x: 42 }
         - { role: ohyoungjooung2.nginx_centos6 }

License
-------
    - MIT


Author Information
------------------
  
    - wnapdlf05@gmail.com
