# egeneralov.zabbix-proxy

Provide zabbix proxy installation.

## Requirements

Debian-based supported distribution.

## Role Variables

- **zbx_database**: `sqlite3` (sqlite3 or pgsql)
- **zbx_server**: `127.0.0.1` ip address
- **sqlite_db**: used with `zbx_database == sqlite3`
  - **path**: `/var/lib/zabbix`
  - **name**: `proxy.db`
- **zbx_proxy_conf**: List with dicts. Example: `[{ "k": "DebugLevel", "v": "3" }]`
- **egeneralov**:
  - **postgresql**: used with `zbx_database == pgsql`, vars for [egeneralov.postgresql](https://github.com/egeneralov/postgresql)

## Dependencies

#### hard-linked

- egeneralov.zabbix-repository

#### can be included

- egeneralov.postgresql

## Example Playbook

    - hosts: zabbix-proxy
      vars:
        zbx_version: 4.2
        zbx_server: zabbix.company.tld
      roles:
        - egeneralov.zabbix-proxy

## License

MIT

## Author Information

Eduard Generalov <eduard@generalov.net>
