# [Catena](https://github.com/alysoid/catena) Ansible Role: sysctl

Configure kernel parameters at runtime with [sysctl](https://wiki.archlinux.org/title/Sysctl) using [sysctl.conf](https://man.archlinux.org/man/sysctl.conf.5.en) preload/configuration files containing sysctl values, managed by [systemd-sysctl](https://man.archlinux.org/man/systemd-sysctl.service.8.en).

## Role variables

### `sysctl_conf`

Manage sysctl configuration files. They will be placed in `/etc/sysctl.d` directory.

```yaml
# Default
sysctl_conf: []

# Example
sysctl_conf:
  # /etc/sysctl.d/10-arch.conf
  - name: 10-arch
    options:
      # Raise inotify resource limits
      fs.inotify.max_user_instances: 1024
      fs.inotify.max_user_watches: 524288
```

### `sysctl_cleanup`

Remove all existing configuration files before creating the new ones.

```yaml
# Default
sysctl_cleanup: false
```
