# Ansible Role: Raspberry Pi

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-raspberry-pi.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-raspberry-pi)

Configures a Raspberry Pi (running Raspbian).

This role will reconfigure certain options in the Raspberry Pi configuration files, but will not automatically _restart_ the Pi to make all the changes take effect. For most changes, you'll need to make sure to reboot your Pi(s) after this role runs.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    raspberry_pi_boot_config_options:
      # Set the GPU memory split value.
      - regexp: "^#?gpu_mem"
        line: "gpu_mem=16"
      # Enable 1200ma USB current on newer model Pis.
      - regexp: "^#?max_usb_current"
        line: "max_usb_current=1"

Use Ansible's `lineinfile` module to ensure certain settings are configured inside `/boot/config.txt`.

    raspberry_pi_rc_local_options:
      # Disable HDMI on startup (for power savings).
      - regexp: "^/usr/bin/tvservice"
        line: "/usr/bin/tvservice -o"

Use Ansible's `lineinfile` module to ensure certain settings are configured inside `/etc/rc.local`.

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
