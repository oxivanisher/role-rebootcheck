rebootckeck
===========
[![Ansible Lint](https://github.com/oxivanisher/role-rebootcheck/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/oxivanisher/role-rebootcheck/actions/workflows/ansible-lint.yml)

Checks if a reboot is required and if requested, also reboots the system.
The behavior can be controlled with the tags:
* `rebootcheck`
* `reboot`
If you supply no tags, wit will do both!

It can also send pushover notification for systems being rebooted.

Role Variables
--------------

| Name                         | Comment                                   | Default value |
|------------------------------|-------------------------------------------|---------------|
| rebootcheck_pushover_userkey | Pushover user key for reboot notification | ``            |
| rebootcheck_pushover_appkey  | Pushover app key for reboot notification  | ``            |


Dependencies
------------

None

Example Playbook
----------------

```yaml
- name: Raspberry Pi
  hosts: all
  collections:
    - oxivanisher.linux_base
  roles:
    - role: oxivanisher.linux_base.rebootcheck              # check if a reboot is required
      tags:
        - upgrade                                           # only upgrade
        - never                                             # don't reboot
```

License
-------

BSD

Author Information
------------------

This role is part of the [oxivanisher.linux_base](https://galaxy.ansible.com/ui/repo/published/oxivanisher/linux_base/) collection, and the source for that is located on [github](https://github.com/oxivanisher/collection-linux_base).
