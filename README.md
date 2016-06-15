Role Name
=========

A simple role to install docker on supported ubuntu versions - a direct mapping of the instructions at this docker location: 
https://docs.docker.com/engine/installation/linux/ubuntulinux/

Tests are forthcoming - this has mainly been tested on xenial ubuntu with vagrant under virtualbox so you can fairly sure of success there.

Requirements
------------

Only requirement is the same as docker - Ubuntu 12.04 (Trusty Tahir) or higher
One important note is that this WILL restart the machine unless you set restart to false (see role variables below)

Role Variables
--------------

There are only a few variables at this time:
- `release` : Defaults to xenial. Can specify any of the supported versions to get the proper installation behavior for that version.
- `has_gui` : Defaults to false. Only used for the special case of precise (12.04) when the machine has a gui enabled (not headless)
- `restart` : Defaults to true. Restarting is recommended and will be done in the native way but in a cloud environment the native way may not be available or desired so please set this to false if that is the case. 

Dependencies
------------

Ansible 2.1 or greater

Example Playbook
----------------

Here's a small example of overriding some of the default variables in a case where restart is not desired nor is xenial.

    - hosts: servers
      roles:
         - { role: docker, release: 'wily', restart: false }

License
-------

BSD

Author Information
------------------

A.M. Knight - www.github.com/ilkelma - Pull requests welcome