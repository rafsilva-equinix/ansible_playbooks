# Playbook Ansible [WIP]

This playbook is used to configure actions and triggers on the clients' HeadNodes to streamline their monitoring configuration.

# Business rule

- Host with Python >= 3.10
- Headnode's devshell user with sudo permission
- Debian or Ubuntu system

## Packages that head node must have

- wget
- unzip

## Tasks

### Check Python version

This task checks the installed Python version on the main nodes. If it is lower than 3.10, the playbook will fail; therefore, **having at least Python 3.10 is a requirement for the system**.

```Python
- name: Check if Python version is 3.10 or higher
  assert:
    that: python_version.stdout | regex_search('(Python 3\.[1-9][0-9]*\.[0-9]*)') is not none
    fail_msg: "Python 3.10 or higher is not installed"
  run_once: true
```