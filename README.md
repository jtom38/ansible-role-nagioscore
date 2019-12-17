# NagiosCore

## About

This role installs Nagios Core within a docker container for you.  

The defaults are built around https://github.com/JasonRivers/Docker-Nagios.

## Variables

[vars](https://github.com/luther38/nagioscore/defaults/main.yml)

``` yaml
# Accepts: install
nagios_action: string

# Define Nagios etc folder
pathEtc: string

# Defines Nagios var folder
pathVar: string

# Defines Nagios plugins folder
pathPlugins: string

# Defines Nagios Graph var
pathGraphVar: string

# Defines Nagios Graph etc
pathGraphEtc: string

# Defines the host that will be used to relay email
envMailRelayHost: string

# Defines the Mail Protocols that will be used
envMailInetProtocols: string

# Defines the Fully Qualified Domain Name that Nagios will use
envNagiosFqdn: string

# Defines the timezone
envNagiosTimezone: string

# Defines what port to use to access Nagios
port: int
```

## Credentials

### Defaults

``` yaml
Username: nagiosadmin
Password: nagios
```

### How to change

TBD

## Example playbook

``` yaml
- name: Install Nagios Core
  hosts: localhost
  vars:
    nagios_action: install
    dockerImage: 'jasonrivers/nagios'
    pathEtc: '/docker/nagios/etc'
    pathVar: '/docker/nagios/var'
    pathPlugins: '/docker/nagios/plugins'
    pathGraphVar: '/docker/nagios/graph/var'
    pathGraphEtc: '/docker/nagios/graph/etc'
    envMailRelayHost: 'localhost'
    envMailInetProtocols: ''
    envNagiosFqdn: 'nagios.domain'
    envNagiosTimezone: 'America/Los_Angeles'
    port: 8080

  roles:
    - geerlingguy.docker
    - luther38.nagioscore
```

## Requirements.yml

``` yaml
roles:
  - src: https://github.com/luther38/nagioscore
    name: luther38.nagioscore
```

## Nagios Documentation

[Nagios Official Documentation](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/toc.html)
