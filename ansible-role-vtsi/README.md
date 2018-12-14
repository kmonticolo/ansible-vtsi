Role Name
=========

ansible-role-vtsi role installs and configures vTSI application on Centos 7 server.

Requirements
------------

- Centos 7
- mirror with vTSI package

Role Variables
--------------
Role variables are to be set in `ansible-vtsi/ansible-role-vtsi/vars/main.yml`

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `mirror` | `http://172.31.67.7/artifacts/vtsi/master/latest/vtsi-kit.tar.gz` | Source of vTSI package. |
| `build` | `latest` | Informs which package build should be used. |
| `host_entries` | `[undefined]` | Set an IP with hostnames that will be located in /etc/hosts file. |
| `vtsi_host` | `VTSI` | vTSI hostname. |
| `snmp_address` | `[undefined]` | IP address for SNMP. |
| `mdb_host` | `SPOTDB2016` | hostname or IP addres of Master database. |
| `mdb_username` | `sa` | Master database username. |
| `mdb_password` | `Cdci2010` | Master database password. |
| `sdb_username` | `sa` | Slave database username. |
| `sdb_password` | `Cdci2010` | Slave database password. |
| `mvl_login` | `administrator` | Video Library username. |
| `mvl_password` | `Cdci2018` | Video Library password. |
| `alarm_login` | `administrator` | Alarm username. |
| `alarm_password` | `Cdci2018` | Lines in `postgres.conf` that are set in order to enable streaming replication. |
| `alarm_host` | `SPOTDB2016` | Lines in `postgres.conf` that are set in order to enable streaming replication. |

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
    - hosts: vtsi
      become: yes
      gather_facts: false
      roles:
         - ansible-role-vtsi
```
Running
-------
```
$ ansible-playbook -i inventory vtsi.yml
```
Testing
-------

Verify if vTSI is running by issuing the following command:
```
curl localhost:8080/actuator/health
```
The expected response is {"status":"UP"}.

Then, issue the following command:
```
telnet localhost 8021
```
The expected response is 220 Service ready for new user.

License
-------

BSD

Author Information
------------------

Kamil Monticolo
