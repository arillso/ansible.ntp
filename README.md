# Ansible Role: NTP

[![Build Status](https://img.shields.io/travis/arillso/ansible.ntp.svg?branch=master&style=popout-square)](https://travis-ci.org/arillso/ansible.ntp) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-ntp-blue.svg?style=popout-square)](https://galaxy.ansible.com/arillso/ntp) [![Ansible Role](https://img.shields.io/ansible/role/d/21608.svg?style=popout-square)](https://galaxy.ansible.com/arillso/ntp)

## Description

Ansible role for installing and configuring NTP on Linux and Windows.

## Installation

```bash
$ ansible-galaxy install arillso.ntp
```

## Requirements

This role requires Ansible 2.7 or higher, and platform requirements are listed
in the metadata file.

## Role Variables

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| ntp_server | [2.pool.ntp.org, 1.pool.ntp.org] | |

### Linux

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| ntp_config_restrict | ['-4 default kod notrap nomodify nopeer noquery', '-6 default kod notrap nomodify nopeer noquery', '127.0.0.1', '::1'] | |
| ntp_config_listen | [] | |
| ntp_config_filegen | ['loopstats file loopstats type day enable', 'peerstats file peerstats type day enable', 'clockstats file clockstats type day enable'] | |
| ntp_config_statistics | 'loopstats peerstats clockstats' | |
| ntp_config_crypto | '' | |
| ntp_config_includefile | '' | |
| ntp_config_keys | '' | |
| ntp_config_trustedkey | '' | |
| ntp_config_requestkey | '' | |
| ntp_config_controlkey | '' | |
| ntp_config_broadcast | '' | |
| ntp_config_broadcastclient | '' | |
| ntp_config_multicastclient | '' | |
| ntp_config_tinker_panic_enabled | '' | |

### Windows

| Variable             | Default     | Comments (type)                                   |
| :---                 | :---        | :---                                              |
| ntp_time_type | 'NTP' | |
| ntp_crosssitesyncflags | '2' | |
| ntp_resolvepeerbackoffminutes | '15' | |
| ntp_resolvepeerbackoffmaxtimes | '7' | |
| ntp_specialpollinterval | '1024' | |
| ntp_eventlogflags | '0' | |

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
