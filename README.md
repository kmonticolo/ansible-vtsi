Role Name
=========

ansible-role-vtsi role installs and configures vTSI application on Centos 7 server.

Requirements
------------

- Centos 7
- mirror with vTSI package

Role Variables
--------------
mirror: set a mirror that contains vTSI package
build: informs which package build should be used

host_entries: set an IP with hostnames that will be located in /etc/hosts file, make sure that you are using the correct ones.

vtsi_host: vTSI hostname

snmp_address: IP address for SNMP
mdb_host: name/IP of MDB
mdb_username: MDB database username (default: sa)
mdb_password: MDB database password
sdb_username: SDB database username (same as for MDB, when no separate SDB exists)
sdb_password: SDB database password
mvl_login: MVL username
mvl_password: MVL password
alarm_login: Alarm username
alarm_password: Alarm password
alarm_host: Alarm hostname (default is to be MDB host)


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: vtsi
      become: yes
      gather_facts: false
      roles:
         - ansible-role-vtsi

License
-------

BSD

Author Information
------------------

Kamil Monticolo
