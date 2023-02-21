# Ansible Role: http_proxy

Configure Debian GNU/Linux networking to use HTTP_PROXY. It places configuration into `/etc/profile.d/proxy.sh`, which should be enough. Apt is explicitly configured via `/etc/apt/apt.conf.d/80proxy` to prevent restarting after creating `/etc/profile.d/proxy.sh`.
## Role Variables

```
proxy:
  http: http://192.168.0.1:3128/
  https: http://192.168.0.1:3128/
  ftp: http://192.168.0.1:3128/
  ftps: http://192.168.0.1:3128/
  dont_use_for:
    - host1.example.com
    - host2.example.com
```

## Example Playbook
```
- hosts: localhost
  connection: local

  roles:
    - role: http_proxy
```
