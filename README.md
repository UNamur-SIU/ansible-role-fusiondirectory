# Ansible Role: Fusion Directory

![Build Status](https://github.com/UNamur-SIU/ansible-role-fusiondirectory/actions/workflows/ci.yml/badge.svg)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-_unamur.fusiondirectory-blue.svg)](https://galaxy.ansible.com/unamur/fusiondirectory/)

Installs [Fusion Directory](https://fusiondirectory-user-manual.readthedocs.io) on Debian 10/11 with [ansible](http://www.ansible.com/home).

The goal here is to provide a standalone fusiondirectory role that can be added into your playbooks.

The ansible role allows you to install, for the moment, the version 1.4 of Fusion Directory.

## Requirements

* A running openLDAP.
* If you are using SSL/TLS, you will need to provide your own certificate and key files. You can generate a self-signed certificate with a command like `openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout example.key -out example.crt`.

## Role Variables for Fusion Directory

Available variables are listed below, along with default values (see `defaults/main.yml`):

### fd

Change the variables to your needs.

	fd_packages:
	- fusiondirectory
	- fusiondirectory-schema
	- fusiondirectory-plugin-webservice
	- fusiondirectory-plugin-webservice-schema

	fd_ldap_uri: ldaps://CHANGEME/dc=CHANGEME
	fd_ldap_admin_dn: cn=CHANGEME
	fd_ldap_admin_password: CHANGEME (you should use ansible-vault for the variable)

	fd_apache_update_vhosts: false
	fd_apache_vhosts_filename: "00-fusiondirectory.conf"
	fd_apache_vhosts_template: "00-fusiondirectory.conf.j2"

    fd_entreprise_setup: false
	fd_entreprise_auth_filename: "auth.conf"
	fd_entreprise_auth_template: "auth.conf.j2"

## Example Playbook

```yaml
- hosts: fd
  become: true
  roles:
    - role: unamur.fusiondirectory
```

## Tests

### testing locally with [Vagrant](https://www.vagrantup.com/)

You can test this ansible role by using `vagrant`. See the Vagrantfile.

## Future improvements

*  Provide more recent/different versions of Fusion Directory
*  More OS support

Feel free to contribute.

## License

[MIT License](LICENSE)
