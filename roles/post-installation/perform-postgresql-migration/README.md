# Perform PostgreSQL migration

## Description

A role to perform PostgreSQL migration by executing SQL script, which comes as a variable.

## Input variables

This role uses the following variables, that intended to be overriden:
- `connection_type` - should the migration be executed locally without authentication or with connection to remote server with authentication, possible choices are `local` and `remote`. The default is `local`.

  When the connection type is `local`, `postgresql_server_address`, `postgresql_username` and `postgresql_password` aren't used, since the task is executed with `postgres` user privileges

- `postgresql_server_address` - the address of the server or loadbalancer of PostgreSQL cluster, against which the migration will be performed, e.g `10.10.10.10`. The default value is not set. An error will interrupt playbook execution in case this variable is not set.

  > Only applicable to `remote` connection type

- `postgresql_server_port` - the port of the server or loadbalancer of PostgreSQL cluster, against which the migration will be performed, e.g. `5432` or `30000`. The default is `5432`
- `postgresql_migration_database` - the name of the database on which the migration will be performed, e.g. `postgres`. The default is `postgres`
- `postgresql_username` - the name of the user to connect to, e.g. `postgres`. The default is `postgres`

  > Only applicable to `remote` connection type

- `postgresql_password` - the password of the user to connect to. The default value is not set. An error will interrupt playbook execution in case this variable is not set.

  > Only applicable to `remote` connection type

- `postgresql_migration_script` - the string containing the migration script, e.g.:
  ```SQL
  BEGIN;
  CREATE TABLE
    IF NOT EXISTS users (
        id SERIAL PRIMARY KEY,
        username VARCHAR(255) NOT NULL UNIQUE,
        email VARCHAR(255) NOT NULL
    );
  COMMIT;
  ```
  The default value is not set. An error will interrupt playbook execution in case this variable is not set
- `migration_script_location` - a path to file, in which the migration script will be rendered from the `postgresql_migration_script` variable with Jinja2, e.g. `/tmp/migration.sql`. The default is `/tmp/migration.sql`