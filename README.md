# docker-nagios-core

## About

This role installs Nagios Core within a docker container for you.  The defaults are built around https://github.com/JasonRivers/Docker-Nagios.

## Variables

``` yaml

```

## Credentials

### Defaults

Username: nagiosadmin
Password: nagios

### How to change

TBD

## Example playbook

``` yaml
- name: Install Nagios Core
  hosts: localhost
  vars:

  roles:
    - geerlingguy.docker
    - docker-nagios-core
```
