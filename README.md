# Ansible Role: Raspberry Pi

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-raspberry-pi.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-raspberry-pi)

Configures a Raspberry Pi (running Raspbian).

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    TODO

## Dependencies

None.

## Example Playbook

    - hosts: pi
      vars_files:
        - vars/main.yml
      roles:
        - { role: geerlingguy.raspberry-pi }

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
