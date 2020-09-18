# How to Send Sensu Go events to Graylog

## Configure Graylog

Create a Syslog UDP input:

![click on graylog dashboad system settings](https://cln.sh/6FmmxY)

![click on inputs](https://cln.sh/QMlL4K)

![search for syslog udp and launch input](https://cln.sh/3oFhWX)

![fill out the details for the syslog udp input](https://cln.sh/6T20DH)

## Configure Sensu

Create a UDP handler to send all events to Graylog:

```
type: Handler
api_version: core/v2
metadata:
  created_by: admin
  labels:
    sensu.io/managed_by: sensuctl
  name: graylog_udp
  namespace: default
spec:
  env_vars: null
  filters: null
  handlers: null
  runtime_assets: null
  secrets: null
  socket:
    host: logs.example.com
    port: 1514
  timeout: 0
  type: udp
```

## 
