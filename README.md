Role Name
=========

The goal of the role is to contenerize a python application on a remote host. 
Role expects specific folder structure.

- <root>/
  - app/
  - requirements.txt
  - conteinerize.yml

Requirements
------------

No extra requirements.

Role Variables
--------------

* app_name  - name of the application
* app_root  - root of the application to be installed on remote host
* app_ports - list of application ports to expose
* python_image   - base python image to host application
* app_maintainer - maintainer of the application
* app_image_name - don't change it unless would like to specify specific image tag.
* app_file         - python file which contains application and is used as startup file. Default: main.py
* src_app_root     - Source of the application, from where to copy it. Default: ./app
* src_requirements - Path to requirements file. Default: ./requirements.txt
* src_dockerfile   - Name of the Dockerfile tempalte. Default file is provided. Default: Dockerfile.j2

Dependencies
------------

No dependencies.

Example Playbook
----------------

    - hosts: servers
      vars:
        app_name: "AppName"
        app_root: "/opt"
        app_ports:
          - "8031"
        python_image: python:3.8.0-alpine
        app_maintainer: "xxx.yyy@zzz.com"
        app_file: app.py
      roles:
         - role: ViacheslavIsaev.containeraize-py-app

License
-------

BSD

Author Information
------------------

Viacheslav Isaev has two decades of experience of distributed high payload systems development. He has been in charge of developing control systems for safety-critical facilities like railroads and particle accelerators, high-payload event processing systems for cybersecurity and mobile access points, introducing in house CI/CD practices. His hands-on experience incldues all stages of IT solutions development and operation. Vyacheslav’s interests lays in automation spectr either it is pure software or hardware-software solutions. Vyacheslav defines the key to success in 3 pillars  Domain Driven Design, Behavioral Driven and Test-Driven Development, which are standing on the foundation of  Object Oriented Design and Clean Code practices.
