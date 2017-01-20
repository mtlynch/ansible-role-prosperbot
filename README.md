# Ansible Role: ProsperBot

[![Build Status](https://travis-ci.org/mtlynch/ansible-role-prosperbot.svg?branch=master)](https://travis-ci.org/mtlynch/ansible-role-prosperbot)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-prosperbot-blue.svg?style=flat-square)](https://galaxy.ansible.com/mtlynch/prosperbot)
[![License](http://img.shields.io/:license-apache-blue.svg?style=flat-square)](LICENSE)

Ansible role for the [ProsperBot](https://github.com/mtlynch/prosperbot) Go app.

## Role Variables

Available variables are listed below, along with default values (see [defaults/main.yml](defaults/main.yml)):

```yaml
prosperbot_user: prosperbot
prosperbot_group: prosperbot
```

The user and group under which to run ProsperBot.

```yaml
prosperbot_gopath: /home/prosperbot/go
prosperbot_goroot: /usr/local/go
```

The filesystem path for Go source files and Go binaries.

```yaml
prosperbot_creds_file: /home/prosperbot/go/src/github.com/mtlynch/prosperbot/prosper-creds.json
```

The location on the filesystem to place the user's Prosper credentials.


```yaml
prosperbot_enable_buying: true
```

Indicates whether buying notes is enabled for ProsperBot.


```yaml
prosperbot_extra_args: ""
```

Additional arguments to pass to the ProsperBot process on startup.

## Dependencies

* [joshualund.golang](https://galaxy.ansible.com/joshualund/golang/)

## Example Playbook

The following playbook will install ProsperBot to a host, configured to authenticate with your Prosper credentials. ProsperBot depends on Redis, so in this example, we'll be installing the [DavidWittman.redis](https://github.com/DavidWittman/ansible-redis) Ansible role on the same host.

#### `secrets.yml`

```yaml
prosperbot_prosper_client_id: [insert your Prosper client ID]
prosperbot_prosper_client_secret: [insert your Prosper client secret]
prosperbot_prosper_username: [insert your Prosper username]
prosperbot_prosper_password: [insert your Prosper password]
```

`prosperbot_prosper_client_id` and `prosperbot_prosper_client_secret` are the values Prosper assigns to you when you generate OAuth credentials on the [OAuth Settings](https://www.prosper.com/oauth#/settings) page.

`prosperbot_prosper_username` and `prosperbot_prosper_password` are the credentials you use to log in to Prosper via the web site.

#### `example.yml`

```yaml
- hosts: all
  vars_files:
    - secrets.yml
  vars:
    - prosperbot_enable_buying: false
  roles:
    - { role: DavidWittman.redis }
    - { role: mtlynch.prosperbot }
```

### Running Example Playbook

```shell
ansible-galaxy install DavidWittman.redis mtlynch.prosperbot
ansible-playbook example.yml
```

## License

Apache2

## Author Information

This role was created in 2016 by [Michael Lynch](http://mtlynch.io).
