# Simple example of ansible static inventory as a source of truth

In environments where you don't have, or don't want to use DNS (such as a home lab), you have to manage hosts files on every host.

This is a working example of how to do this using ansible inventory as the source of truth, including the IP addresses of each host.

## The directory structure
```

```
Here is what each file does:
- `ansible.cfg` is the configuration of Ansible itself.
- `base.yml` is the base playbook that uses the base role.
- `group_vars/all` is a file with global variables accessible from every role; these variables can be overridden in any role.
- `inventory/inventory.yml` is the static inventory file, the source of truth. It contains the IP addresses of each host in inventory as well.
- `roles/base` is a directory for the `base` role that is called by base.yml.
- `roles/base/tasks/main.yml` is the paybook containing the task to update the hosts files on managed hosts.
- `roles/base/templates/hosts.j2 is the Jinja template of an ubuntu hosts file.
