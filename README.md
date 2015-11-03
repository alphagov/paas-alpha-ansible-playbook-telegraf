# ansible-playbook-telegraf

Ansible role for deploying [https://github.com/influxdb/telegraf] Telegraf stats collection client for influxdb

### Requirements

The following ansible variables are used by this role - the default values are shown alongside.

```
telegraf_version: 0.1.2
influxdb_url: http://localhost:8086
influxdb_database: testdb
influxdb_user: someuser
influxdb_pass: somepassword
```

You will want to override these role variables within your playbooks.

You can associate tags with the server and they will be recognised by influxdb and grafana. Example:

```
influxdb_tags:
	role: web-server
	region: eu-west
```

### Usage

```
- hosts: "{{ hosts_prefix }}-*"
  sudo: yes
  roles:
    - telegraf
```

