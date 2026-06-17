# Configure Keeplived

## Description

A role to install and configure Keepalived.

## Input variables

This role uses the following variables, that intended to be overriden:
- `keepalived_password` - a password for Keepalived, e.g. `keepalived`. The default is `3Q8azoG8DRAZmO4`
- `server_port` - a port, on which PostgreSQL will accept connections, the available range is from `10` to `49151`. The default is `5432`
- `keepalived_address` - a virtual IP address, which master host will have, e.g. `192.168.10.10`. The default value is not set