graywrk.ansible_role_postgresql
=========

Role for install and configure PostgreSQL

Role Variables
--------------

```
# validate certs for postgresql repo key
postgresql_validate_certs: "yes"

# postgresql apt key name
postgresql_apt_key: "ACCC4CF8.asc"

# version of postgresql (9.1, 9.2, 9.3, 9.4, 9.5, 9.6, 10, etc)
postgresql_version: 14

# Database port to connect to
postgresql_port: 5432

# Path to postgresql.conf
postgresql_config_path: "/etc/postgresql/{{ postgresql_version }}/main"

# postgresql data directory
postgresql_data_directory: "/var/lib/postgresql/{{ postgresql_version }}/main"

# path to template of pg_hba.conf
postgresql_pghba_template_path: "{{ role_path }}/templates/pg_hba.conf.j2"

# Options for postgresql config
postgresql_config_options:
  - option: listen_addresses
    value: "*"
    state: 'present' # present (default)| absent
  - option: port
    value: "{{ postgresql_port }}"

# list of database users
postgresql_users: []
#  - name:
#    password:
#    encrypted: no (optional) (must 'yes' for postgresql version 10 and higher)
#    role_attr_flags: NOSUPERUSER (optional) http://docs.ansible.com/ansible/latest/postgresql_user_module.html#options

# list of databases
postgresql_dbs: []
#  - db:
#    user:
#    encoding: UNICODE (optional)
#    ext: (optional)
#      - ext1
#      - ext2
#    schema: (optional)
#      - schema1
#      - schema2

# flag to create the databases 
postgresql_create_db: true
```

License
-------

MIT


