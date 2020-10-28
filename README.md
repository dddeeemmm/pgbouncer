pgbouncer
=========

    Install and configure pgbouncer

Role Variables
--------------

    pgbouncer_install:                 [ default: true ] install packages
    pgbouncer_dbname: ''               [ required ] target database name 
    pgbouncer_host: ''                 [ required ] target host
    pgbouncer_host_port: ''            [ required ] target port
    pgbouncer_host_user: ''            [ required ] remote user
    pgbouncer_host_password: ''        [ required ] rebote password
    pgbouncer_userlist: []             [ not required ] user list 
    pgbouncer_databases: ''            [ default: '* = host=127.0.0.1 port=5432' ] local connection string
    pgbouncer_listen_addr: ''          [ default: 127.0.0.1 ] listen address
    pgbouncer_listen_port: ''          [ default: 6432 ] listen port
    pgbouncer_auth_type: ''            [ default: trust ] auth type
    auth_file: ''                      [ default: /etc/pgbouncer/userlist.txt ] user list file 
    pgbouncer_admin_users: ''          [ default: postgres ] admiun user
    pgbouncer_pool_mode: ''            [ default: transaction ] pool mode
    pgbouncer_server_reset_query: ''   [ default: DEALLOCATE ALL ] query reset
    pgbouncer_max_client_conn: ''      [ default: 1000 ] max client connections
    pgbouncer_default_pool_size: ''    [ default: 100 ] pool size
    pgbouncer_server_lifetime: ''      [ default: 1200 ] life time
    pgbouncer_server_idle_timeout: ''  [ default: 300 ] idle timeout
    pgbouncer_pkt_buf: ''              [ default: 8192 ] buffer size
    pgbouncer_dns_max_ttl: ''          [ default: 1 ] ttl
    
    nolog: ''                          [ default: true ] disable log secrets

Example Playbook
----------------

    - hosts: app
      become: true
      vars:
        pgbouncer_dbname: postgres 
        pgbouncer_host: postgres.domain.org
        pgbouncer_host_port: 5432
        pgbouncer_host_user: postgres
        pgbouncer_host_password: changeme
      roles:
        - { name: pgbouncer, tags: pgbouncer }

License
-------

    MIT

Author Information
------------------

    Dmitrij Petrov
