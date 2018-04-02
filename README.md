Role Name
=========
nginx_centos6

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

    key_file: /etc/nginx/ssl/nginx.key #private tls key
    cert_file: /etc/nginx/ssl/nginx.cert #private tls cert
    config_file: /etc/nginx/conf.d/default.conf #default vhost


  


Dependencies
------------
  None

Example Playbook
----------------

  Basic usage
       - hosts: servers
         roles:
              - { role: ohyoungjooung2.nginx_centos6 } #Basic nginx 80 port
             #- { role: ohyoungjooung2.nginx_centos6,nginx_cert_config: true } #Include TLS
             #- { role: ohyoungjooung2.nginx_centos6,os_update: true } #Include os update


   
License
-------
    - MIT


Author Information
------------------
  
    - wnapdlf05@gmail.com
