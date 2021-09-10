# Ansible Role: Fusion Directory

[![Build Status]()]()
[![Ansible Galaxy]()](https://galaxy.ansible.com/unamur-siu/fusiondirectory/)

Installs [Fusion Directory](https://fusiondirectory-user-manual.readthedocs.io) on Debian 11 with [ansible](http://www.ansible.com/home).

The goal here is to provide a standalone fusiondirectory role that can be added into your playbooks.

The ansible role allows you to install, for the moment, the version 1.3 of Fusion Directory.

## Requirements

You can use this ansible role to set up php:
* 

## Role Variables for Fusion Directory

Available variables are listed below, along with default values (see `defaults/main.yml`):

### tomcat

	tomcat_version: '8.5.31'
	tomcat_port: '8080'
	tomcat_port_ajp: '8009'
	tomcat_port_https: '8443'
	tomcat_port_shutdown: '8005'
	tomcat_group: 'tomcat'
	tomcat_user: 'tomcat'
	tomcat_user_home: '/opt/tomcat'
	
You can set variables related to tomcat here.
	
### geerlingguy php

	java_home: '/lib/jvm/jre-1.8.0-openjdk'
	
## Dependencies

  - geerlingguy.php

## Example Playbook

```yaml
- hosts: fusiondirectory
  become: true
  roles:
    - role: geerlingguy.php
    - role: unamur-siu.fusiondirectory
```

## Tests

### testing locally with [Vagrant](https://www.vagrantup.com/)

You can test this ansible role by using `vagrant`. See the Vagrantfile.

### testing with Travis

See the playbook used for Travis CI tests (tests/test.yml).

## Future improvements

*  Provide more recent/different versions of Fusion Directory
*  More OS support

Feel free to contribute.

## License

MIT License https://github.com/cetic/ansible-role-tomcat8.5/blob/master/LICENSE
