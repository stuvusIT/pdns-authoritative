# pdns-authoritative

This role installs and configures PowerDNS authoritative server.
pdns is automatically restarted after configuration changes, unless the role variables say otherwise.

## Requirements

Debian 11 (Bullseye)

## Role Variables

| Name                                | Default/Required | Description                                                                       |
|-------------------------------------|:----------------:|-----------------------------------------------------------------------------------|
| `pdns_auth_repo_ver`                | `41`             | Version of the apt repository for PowerDNS (Ubuntu only)                          |
| `pdns_auth_config`                  |                  | Configuration dict of PowerDNS                                                    |
| `pdns_auth_no_restart`              | `false`          | Set this to true to prevent pdns from being restarted after configuration changes |
| `pdns_auth_configure_postgres`      | `true`           | Whether to configure a PostgreSQL user and database and import the schema         |
| `pdns_auth_postgres_login_host`     | `localhost`      | Host to connect to for setting up PostgreSQL                                      |
| `pdns_auth_postgres_login_user`     | `postgres`       | User to connect with for setting up PostgreSQL                                    |
| `pdns_auth_postgres_login_password` |                  | Password to connect with for setting up PostgreSQL                                |

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

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
