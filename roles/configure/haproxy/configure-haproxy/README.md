# Configure HAProxy

## Description

A role to install and configure HAProxy.

## Input variables

This role uses the following variables, that intended to be overriden:
- `haproxy_admin_username` - a username for HAProxy stats, e.g. `admin`. The default is `admin`
- `haproxy_admin_password` - a password for HAProxy stats, e.g. `haproxy_stats`. The default is `haproxy_stats`
- `server_port` - a port, on which PostgreSQL will accept connections, the available range is from `10` to `49151`. The default is `5432`
- `patroni_port` - a port, on which Patroni will accept connections, e.g. `8008`. The default is `8008`
- `haproxy_port` - a port, on which HAProxy web interface will be available, e.g. `8404`. The default is `8404`