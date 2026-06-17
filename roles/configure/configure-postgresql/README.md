# Configure PostgreSQL

## Description

A role to install and configure specified PostgreSQL version.

## Input variables

This role uses the following variables, that intended to be overriden:
- `postgresql_version` - version of PostgreSQL installation, e.g. `17` or `18`. The default is `18`
- `posgresql_directory` - a directory, in which PostgreSQL files will be stored, e.g. `/usr/local/pgsql`. The default is `/usr/local/pgsql`
- `server_port` - a port, on which PostgreSQL will accept connections, the available range is from `10` to `49151`. The default is `5432`
- `admin_password` - password for user `postgres` of the PostgreSQL cluster. The default value is not set. An error will interrupt playbook execution in case this variable is not set.
- `postgresql_systemd_service` - a name for systemd service which will handle PostgreSQL server. The default is `cld_postgresql`.