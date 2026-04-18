# Configuration Management Using Ansible Playbooks

Repository owner: **jyothi-samberpu**

GitHub repository: https://github.com/jyothi-samberpu/Configuration-Management-using-Ansible-playbooks

## Overview

This repository provides Ansible automation for infrastructure setup and maintenance tasks, including:

- Configuration management across Linux servers
- Kubernetes prerequisite setup
- Harbor and Vault related automation
- AWS CLI installation and CI/CD helper playbooks
- GitHub Runner and Jenkins support tasks
- System upgrade and cleanup operations

## Repository Structure

- `inventory/`: inventory file and shared variables
- `playbooks/`: top-level playbooks for common operations
- `roles/`: reusable Ansible roles
- `Scripts/`: deployment, compose templates, and pipeline helpers

## Prerequisites

- Ansible installed on the control node
- SSH access to target hosts
- Python available on managed hosts (as required by Ansible)

Install Ansible (examples):

```bash
sudo apt-get install -y ansible
sudo yum install -y ansible
sudo dnf install -y ansible
```

## Quick Start

1. Clone the repository:

```bash
git clone https://github.com/jyothi-samberpu/Configuration-Management-using-Ansible-playbooks.git
cd Configuration-Management-using-Ansible-playbooks
```

2. Update inventory in `inventory/hosts`.

Example:

```ini
[webservers]
server1 ansible_host=192.168.1.10
server2 ansible_host=192.168.1.11

[dbservers]
db1 ansible_host=192.168.1.20
```

3. Run a playbook:

```bash
ansible-playbook -i inventory/hosts playbooks/remove_ceph.yml
```

## Common Playbooks

- `playbooks/system_upgrade.yml`: system package upgrade tasks
- `playbooks/ssh_key_setup.yml`: SSH key and access setup
- `playbooks/github_runner.yaml`: GitHub Runner installation/configuration
- `playbooks/install_aws_cli.yaml`: AWS CLI installation
- `playbooks/linux_setup_harbor.yml`: Harbor-related setup tasks

## Notes

- Keep environment-specific values in inventory/group vars.
- Test changes in a non-production environment first.
