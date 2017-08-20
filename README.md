# pdns-authoritative

This role installs and configures PowerDNS authoritative server.
pdns is automatically restarted after configuration changes, unless the role variables say otherwise.

## Requirements

Arch Linux or Ubuntu

## Role Variables

| Name                   | Default/Required | Description                                                                       |
|------------------------|:----------------:|-----------------------------------------------------------------------------------|
| `pdns_auth_repo_ver`   | `40`             | Version of the apt repository for PowerDNS (Ubuntu only)                          |
| `pdns_auth_config`     |                  | Configuration dict of PowerDNS                                                    |
| `pdns_auth_no_restart` | `false`          | Set this to true to prevent pdns from being restarted after configuration changes |

## Example Playbook

```yml
- hosts: dns
  roles:
  - powerdns-authoritative
     pdns_auth_config:
       master: "yes"
       chroot: "/var/empty"
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)