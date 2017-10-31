# Ansible Role: NTP
[![Build Status](https://travis-ci.org/arillso/ansible.ntp.svg?branch=master)](https://travis-ci.org/arillso/ansible.ntp)

## Description

Ansible role for installing ntp on installs RHEL/CentOS or Debian/Ubuntu.

## Installation

```
$ ansible-galaxy install arillso.redis
```

## Requirements

This role requires Ansible 1.4 or higher, and platform requirements are listed
in the metadata file.

## Dependencies

None

## Example Playbook

1) Install ntp and set the default settings.

```yml
    - hosts: all
      roles:
        - arillso.ntp
```

2) Install ntp and set some custom servers.

```yml
    - hosts: all
      roles:
        - arillso.ntp
	      ntp_config_server: [2.ubuntu.pool.ntp.org, 1.ubuntu.pool.ntp.org]
```

## Changelog

### 1.3

* rename role name

### 1.2

* add become

### 1.1

* add multiple os support

### 1.0

* add my settings

## Author

* Benno Joy
* René Moser
* [Simon Bärlocher](https://sbaerlocher.ch)

## License

BSD