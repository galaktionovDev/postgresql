# Configure Patroni

## Description

A role to install and configure Patroni.

## Input variables

This role uses the following variables, that intended to be overriden:
- `postgresql_version` - version of PostgreSQL installation, e.g. `17` or `18`. The default is `18`
- `admin_password` - password for user `postgres` of the PostgreSQL cluster. The default value is not set. An error will interrupt playbook execution in case this variable is not set.
- `server_port` - a port, on which PostgreSQL will accept connections, the available range is from `10` to `49151`. The default is `5432`
- `patroni_config_directory` - the directory for patroni configuration files, e.g. `etc/patroni`. The default is `/etc/patroni/`
- `patroni_port` - a port, on which Patroni will accept connections, e.g. `8008`. The default is `8008`
- `etcd_config_directory` - the directory for etcd configuration files, e.g. `etc/etcd`. The default is `/etc/etcd`
- `posgresql_directory` - a directory, in which PostgreSQL files will be stored, e.g. `/usr/local/pgsql`. The default is `/usr/local/pgsql`
- `max_connections` - the maximum number of concurrent connections the PostgreSQL server will accept, e.g. `100` or `250`. The default is `100`
- `shared_buffers` - a size of the dedicated area of shared memory (RAM) used to cache data pages, e.g. `128MB` or `256MB`. The default is  `256MB`