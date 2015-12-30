ansible-oracle-db-create
=========

Creates oracle databases

Based on oravirt/ansible-oracle (https://github.com/oravirt/ansible-oracle)


Role Variables
--------------

**database_parameters** Use default values for vagrant machines.  otherwise override values from inventory group_vars variable.

```yaml
  database_parameters:
    <dbname>:
      db_version: # 11.2.0.4 or 12.1.0.2
      redolog_size_mb: # size of db redo logs, ie 75
      db_recovery_file_dest_size: # size of FRA in, ie 10G
      sga_target: # sga target, ie 2G
      pga_aggregate_target: # pga target, ie 1G
      log_mode: # archivelog or noarchivelog
```

Example Playbook
----------------

    - hosts: oracle
      roles:
        - role: ansible-role-common
        - role: ansible-oracle-host
        - role: ansible-oracle-install
        - role: ansible-oracle-db-create

Example requirements.yml
----------------
```
- src: https://github.com/CruGlobal/ansible-oracle-db-create
  version: v0.1
  path: roles/
```

License
-------

BSD
