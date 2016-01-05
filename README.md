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
mopidy_external_extensions: []
```

A list of external extensions that are not contained in the repository, but can be obtained with pip.

```
mopidy_settings: []
```

A list of additional options to configure. Each item requires the `section`, `option` and `value` properties to be defined. These are used by the [ini_file](http://docs.ansible.com/ansible/ini_file_module.html) module to configure `/etc/mopidy/mopidy.conf`.

Alternatively, you can apply settings with the `tasks/settings.yml` task. This task accepts the `settings` variable, and allows for updating configuration where `mopidy_settings` might already be in use.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: servers
  roles:
    - role: mopidy
      mopidy_extensions:
        - mopidy-local-sqlite
  tasks:
    - include: roles/mopidy/tasks/settings.yml
      vars:
        settings:
          - section: mpd
            option: password
            value: hackme
```

## License

BSD

## Author Information

This role was created in 2016 by [Daniel White](https://github.com/danielwhite).
