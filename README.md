# Ansible Role: NTP

[![Build Status](https://img.shields.io/travis/arillso/ansible.ntp.svg?branch=master&style=popout-square)](https://travis-ci.org/arillso/ansible.ntp) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-ntp-blue.svg?style=popout-square)](https://galaxy.ansible.com/arillso/ntp) [![Ansible Role](https://img.shields.io/ansible/role/d/id.svg?style=popout-square)](https://galaxy.ansible.com/arillso/ntp)

## Description

Ansible role for installing NTP on Linux and Windows.

## Installation

```bash
$ ansible-galaxy install arillso.ntp
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

### 1.4.0

* Support for Windows NTP Settings

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
