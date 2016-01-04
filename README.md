# Ansible Role: Mopidy

[![Build Status](https://travis-ci.org/danielwhite/ansible-role-mopidy.svg?branch=master)](https://travis-ci.org/danielwhite/ansible-role-mopidy) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-mopidy-blue.svg)](https://galaxy.ansible.com/detail#/role/6804)

An Ansible role that installs [Mopidy](https://www.mopidy.com/) on Ubuntu/Debian.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
mopidy_extensions: []
```

A list of extensions to install from the package manager.

```
mopidy_settings: []
```

A list of additional options to configure. Each item requires the `section`, `option` and `value` properties to be defined. These are used by the [ini_file](http://docs.ansible.com/ansible/ini_file_module.html) module to configure `/etc/mopidy/mopidy.conf`.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: servers
  roles:
    - role: mopidy
      mopidy_extensions:
        - mopidy-local-sqlite
```

## License

BSD

## Author Information

This role was created in 2016 by [Daniel White](https://github.com/danielwhite).
