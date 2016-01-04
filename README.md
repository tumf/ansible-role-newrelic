# Ansible Newrelic Role

Based on [franklinkim.newrelic](https://galaxy.ansible.com/list#/roles/3917)

[![Build Status](https://img.shields.io/travis/tumf/ansible-role-newrelic.svg)](https://travis-ci.org/tumf/ansible-role-newrelic)
[![Galaxy](http://img.shields.io/badge/galaxy-tumf.newrelic-blue.svg)](https://galaxy.ansible.com/list#/roles/6788)
[![GitHub Tags](https://img.shields.io/github/tag/tumf/ansible-role-newrelic.svg)](https://github.com/tumf/ansible-role-newrelic)
[![GitHub Stars](https://img.shields.io/github/stars/tumf/ansible-role-newrelic.svg)](https://github.com/tumf/ansible-role-newrelic)

> `newrelic` is an [ansible](http://www.ansible.com) role which:
>
> * installs newrelic
> * configures newrelic
> * configures service

## Installation

Using `ansible-galaxy`:

```shell
$ ansible-galaxy install tumf.newrelic
```

Using `requirements.yml`:

```yaml
- src: tumf.newrelic
```

Using `git`:

```shell
$ git clone https://github.com/tumf/ansible-role-newrelic.git tumf.newrelic
```

## Dependencies

* Ansible >= 1.9

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
# newrelic_license_key: yourkey

# user name
newrelic_user: newrelic
# Name of the file where the server monitor will store it's log messages.
newrelic_logfile: /var/log/newrelic/nrsysmond.log
# Level of detail you want in the log file
newrelic_loglevel: info
# Set to true to disable NFS client statistics gathering.
newrelic_disable_nfs: no
# Set to true to disable Docker container statistics gathering.
newrelic_disable_docker: no
# start on boot
newrelic_service_enabled: yes
# current state: started, stopped
newrelic_service_state: started
```

## Handlers

These are the handlers that are defined in `handlers/main.yml`.

* `restart newrelic`

## Example playbook

```yaml
- hosts: all
  sudo: yes
  roles:
    - tumf.newrelic
  vars:
    newrelic_license_key: yes
    newrelic_service_state: started
    newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
```

## Testing

```shell
$ git clone https://github.com/tumf/ansible-role-newrelic.git tumf.newrelic
$ cd tumf.newrelic
$ ./tests/run
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

Copyright (c) We Are Interactive under the MIT license.

@tumf
