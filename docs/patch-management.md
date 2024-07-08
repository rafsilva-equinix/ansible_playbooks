# Playbook Ansible [WIP]

This playbook is used to update the packages of all active hosts and send them to the raw_upgradable table in the patch-management schema. These data are later processed by an ETL flow called etl_upgradebles, which is located in Prefect 2.0.

# Business rule

- The data must be sent from the localhost, thus not requiring direct communication between the nodes and the database.
- Headnode's devshell user with sudo permission.
- Debian or Ubuntu system.
- The inventory associated with the template that uses this playbook must only contain active hosts.

## Required variables
Every host registered in the inventory must have the following variables:

``` YAML
---
ansible_python_interpreter: '{{ ansible_playbook_python }}'
ansible_host: 172.0.0.0
sys_id: ca08c188-016b-48d4-a4d0-eed6ebdbadda
```

Hosts are already created with this pattern by the update_inventory workflow in Prefect 2.0.

## Packages that localhost must have

- psycopg2