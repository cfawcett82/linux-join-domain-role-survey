linux-join-domain-role-survey
=========

A role developed to join an EL 7.x or 8.x server to a windows AD domain

Requirements
------------

This was developed with an AWX/Tower survey in mind, and to be targeted at a single or small group of servers.


Role Variables
--------------
There are multiple concatinations of these variables in the main task. Please review prior to use.

Defaults: these are in place so that an accidental run will result in failure.  
input_host: none  
ad_server_user: user.last@domain.local  
ad_server_pass: 5up3rdup3r53cr3t  
ad_server_domain: domain.local  
ad_server_ldapuri: SHORTNAME_OF_SERVER  
ad_server_ip: IPADDRESS_OF_SERVER  
realm_permit_group: AD_GROUP_NAME  

vars: a list of packages required for domain join to function  
required_pkgs:  
  - realmd  
  - sssd  
  - oddjob  
  - oddjob-mkhomedir  
  - adcli  
  - samba-common  
  - samba-common-tools  
  - ntpdate  
  - ntp  


Dependencies
------------

none

Example Playbook
----------------

- hosts: "{{ input_host }}"
  become: yes
  
  roles:
    - linux-join-domain-role-survey
    - 
License
-------

BSD

Author Information
------------------
Cody Fawcett
cody@bncdiagnostics.com
https://github.com/cfawcett82
