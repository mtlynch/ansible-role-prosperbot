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

The user and group under which to run PropserBot.

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

TODO

### Running Example Playbook

TODO

## License

Apache2

## Author Information

This role was created in 2016 by [Michael Lynch](http://mtlynch.io).
