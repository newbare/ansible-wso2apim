Api Manager for Ansible Galaxy, runs for Vagrant
=========

This role get up a instances with the carbon product, wso2 api manager.

That make?
------------

- Creates a user
- Creates a group
- Downloads wso2 api manager
- Unzips zip api manager
- Creates a daemon for systemd
- Runs the api manager products 
- Creates user
- Creates group
- Downloads wso2 api manager
- Unzips zip api manager
- Installs java

Requirements
------------
- java

Role Variables
--------------

# defaults file for wso2apim-2.5.0
- wso2_user: wso2
- wso2_group: wso2
- carbon_base: "/opt/{{wso2_app}}" 
- carbon_home: "{{carbon_base}}/current"
- unzip_folder: "/tmp"

# these are the default ports for wso2 products
- wso2_user: user
- wso2_group: group
- carbon_base: personal folder
- carbon_home: home folder
- unzip_folder: temporal folder

# these are the default ports for wso2 products
- wso2_default_https_port: 9443
- wso2_default_http_port: 9763

#the following is written into the init.d file for the service
- java_home: "/usr/java/default"
- jvm_mem: "-Xms256m -Xmx1024m"

# wso2
- wso2_app: wso2am
- wso2_app_version: 2.5.0
- wso2_app_directory: "{{wso2_app}}-{{ wso2_app_version }}"
- java_home: road java

# wso2
- wso2_app: product name
- wso2_app_version: version
- wso2_app_directory: product directory 
- wso2_app_offset: 0
- wso2_headers: "User-Agent:testuser,Referer:http://connect.wso2.com/wso2/getform/reg/new_product_download"
- wso2_apim_url: "http://product-dist.wso2.com/products/api-manager/{{wso2_app_version}}/wso2am-{{wso2_app_version}}.zip"
- wso2_app_https_port: "{{ (wso2_default_https_port|int) + (wso2_app_offset|int) }}"
- wso2_app_http_port: "{{ (wso2_default_http_port|int) + (wso2_app_offset|int) }}"
- wso2_dir_archive: "/home/{{ wso2_user }}"
- wso2_app_archive: "{{ unzip_folder }}/{{wso2_app}}-{{wso2_app_version}}.zip"
=======
- wso2_app_archive: zip road

Dependencies
------------

- ansible-oracle-java
- https://github.com/falconmfm/ansible-oracle-java

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

