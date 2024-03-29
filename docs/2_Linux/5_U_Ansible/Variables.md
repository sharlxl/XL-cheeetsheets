---
title: Variables
sidebar_position: 4
---

# Variables

Stores information that varies with each host

```yaml
vars:
  dns_server: 10.1.250.10
tasks:
  - lineinfile:
      path: /etc/resolv.conf
      line: "nameserver {{dns_server}}"
```

\*\* Jinja2 templating --> {{ }}

===
Examples:

```yaml
- name: "Update nameserver entry into resolv.conf file on localhost"
  hosts: localhost
  vars:
    car_model: "BMW M3"
    country_name: "USA"
    title: "Systems Engineer"
  tasks:
    - name: "Print my car model"
      command: 'echo "My car''s model is {{car_model}}"'
    - name: "Print my country"
      command: 'echo "I live in the {{country_name}}"'
    - name: "Print my title"
      command: 'echo "I work as a {{title}}"'
```
