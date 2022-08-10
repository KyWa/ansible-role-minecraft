minecraft
=========

This role is for Ansible to install Minecraft Servers. It provides the functionality to create multiple instances on a single host as each option is variablized.

Requirements
------------

The only requirement is a Linux server (RHEL/CentOS/Rocky/Fedora or Debian/Ubuntu/*untu) that is reachable and can obtain sudo privileges.

Role Variables
--------------

The defaults found in `defaults/main.yml` contain all of Minecraft Servers `server.properties` that can be overwritten. The core variables that matter are as follows:

* `minecraft_install` - Set this to true to install a Minecraft Server instance
* `minecraft_uninstall` - Set this to true to uninstall a Minecraft Server instance
* `minecraft_upgrade` - Set this to true to upgrade a Minecraft Server instance
* `minecraft_config_change` - Set this to true to change the configuration a Minecraft Server instance with vars for `server.properties`
* `minecraft_backup` - Set this to true to backup a Minecraft Server instance
* `minecraft_restore` - Set this to true to restore a Minecraft Server instance

A good plan for host vars would look something like this:

```sh
group_vars:
- minecraft_version: "latest"
- minecraft_backup: true
host_vars:
- spawn_monsters: "false"
```

Example Playbook
----------------

Below is an example playbook to install a Minecraft Server instance:

```yaml
- hosts: servers
  roles:
    - { role: kywa.minecraft, minecraft_install: true }
```

License
-------

MIT / BSD
