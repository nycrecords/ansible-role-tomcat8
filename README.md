Ansible Role: Tomcat 8
======================
![GitHub](https://img.shields.io/github/license/nycrecords/ansible-role-tomcat8)
[![Build Status](https://travis-ci.com/nycrecords/ansible-role-tomcat8.svg?branch=master)](https://travis-ci.com/nycrecords/ansible-role-tomcat8)
[![Galaxy](https://img.shields.io/badge/galaxy-nycrecords.tomcat8-blue.svg)](https://galaxy.ansible.com/nycrecords/tomcat8)
![Ansible](https://img.shields.io/ansible/role/d/90483)
![Ansible](https://img.shields.io/ansible/quality/90483)

An Ansible role that installs Tomcat 8 on:

* Centos/RHEL 7.x
* Ubuntu Xenial


Requirements
------------

Ansible 2.4 or higher

On RedHat-based distributions, requires the EPEL repository (you can simply add the role `geerlingguy.repo-epel` to install ensure EPEL is available) or a valid RedHat Subscription.


Role Variables
--------------

Available variables are listed below, along with default values:

Tomcat packages to install

    tomcat_packages:
      - tomcat

Tomcat admin packages to install

    tomcat_admin_packages:
      - tomcat-admin


Directory to install Tomcat into

    tomcat_home: /var/lib/tomcat


Whether to install the Tomcat administrative interface

    tomcat_admin_install: yes


Tomcat roles

    tomcat_roles: []


Tomcat users

    tomcat_users: []


User and group to run Tomcat as

    tomcat_server_user: tomcat
    tomcat_server_group: tomcat


Some OS-specific variables are set in vars/* but can be overridden

    tomcat_home: /opt/tomcat


Including these only used by CentOS/RH

    tomcat_version: 8.5.27
    tomcat_binary_url:  "http://www-eu.apache.org/dist/tomcat/tomcat-8/v{{ tomcat_version }}/bin/apache-tomcat-{{ tomcat_version }}.tar.gz"
    tomcat_target_dir:  "/opt/apache-tomcat-{{ tomcat_version }}"

Set Tomcat Java Heap Size options for Tomcat Service

    tomcat_heap_min: "128m"
    tomcat_heap_max: "128m"
    tomcat_max_perm_size: "512m"

Dependencies
------------

* nycrecords.java

Example Playbook
----------------

    - hosts: webservers
      roles:
        - { role: nycrecords.tomcat }

License
-------

MIT

Author Information
------------------

This role was originally created by [Islandora Devops](https://github.com/Islandora-Devops)

Modified by [Joel Castillo](https://github.com/joelbcastillo) for the [NYC Department of Records and Information Services](https://github.com/nycrecords).
