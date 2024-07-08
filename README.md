# Ansible AWX

# About

This project witholds any related files and playbooks related to the Ansible process for the NVIDIA project.

# Sumary
1. Project files
1. Folders
1. Used modules

## Project files

```
├── README.md
├── collections
│   ├── requirements.yml
├── docs
│   ├── headnode-activation.md
│   └── patch-management.md
└── playbooks
    ├── headnode-activation.yaml
    └── patch-management.yaml
```

## Folders

**playbooks**

Stores all project Ansible playbooks. Since all playbooks here a used to be ran in a AWX context, it need to be updated in the remote repository and then sync with AWX project. Also, a playbook must be added to a template.

**roles** (currently not in use)

Stores tasks, variables and all that is reusable for a specific group of host group.

**collections**

Ansible Tower expects by default collections to be listed in the "collections/requirements.yml" path. When a Template is runned it install all collections listed in the file. 

## Used modules

https://docs.ansible.com/ansible/latest/collections/amazon/aws/secretsmanager_secret_lookup.html#ansible-collections-amazon-aws-secretsmanager-secret-lookup

