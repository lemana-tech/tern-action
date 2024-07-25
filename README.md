# tern-action

Tern migrator action runs a [Docker image](https://github.com/lemana-tech/tern/pkgs/container/tern) with a set of provided arguments.

### Action parameters

The parameters and their default values correspond to the parameters of the [tern tool](https://github.com/jackc/tern?tab=readme-ov-file#configuration).

| Parameter     | Required | Description                                                                                            | Default value         |
| ------------- | -------- | ------------------------------------------------------------------------------------------------------ | --------------------- |
| conn_string   | Yes      | URI or DSN as described in https://www.postgresql.org/docs/current/libpq-connect.html#LIBPQ-CONNSTRING |                       |
| command       | No       | Command to run                                                                                         | migrate               |
| destination   | No       | Destination migration version                                                                          | last                  |
| migrations    | No       | Path to migrations directory                                                                           | .                     |
| version_table | No       | Version table name                                                                                     | public.schema_version |

### Usage

```yml
- name: migrate
  uses: lemana-tech/tern-action@v1
  with:
    conn_string: postgres://user:password@host:port
    migrations: migrations
```

### TODO

- Switch to `jackc/tern` docker image after release
