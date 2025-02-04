# System Configuration Playbook

This Ansible playbook provides automated configuration for system encryption, CPU tuning, and network interface management.

## Features

### 1. Disk Encryption
- Second disk encryption with LUKS2
- Root-adjacent partition encryption

### 2. CPU Tuning
- C-states management for all processors
- Performance mode configuration check

### 3. Network Configuration
- Active interface renaming to "net0"
- Network status display
- Processor and threading information display

## Quick Start

1. Clone the repository:
```bash
git clone git@github.com:cptLamo/ansible-test-assignment.git
cd ansible-test-assignment
```

2. Configure your inventory (inventory/hosts.yml):
```yaml
all:
  hosts:
    server:
      ansible_host: "your server"
```

3. Run the playbook:
```bash
# Run all roles
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username"
```

### Run specific roles:
To learn more about launching individual roles, go to the "roles" folder

## Roles Documentation

Detailed documentation for each role is available in their respective directories:

- [Encryption Role](roles/encryption/README.md)
- [CPU Tuning Role](roles/cpu_tuning/README.md)
- [Network rename Role](roles/network/README.md)

## Directory Structure
```
aws-test/
├── inventory/
│   └── hosts.yml          # Inventory configuration
├── roles/
│   ├── cpu_tuning/        # CPU performance tuning role
│   ├── network/           # Network configuration role
│   └── encryption/        # Disk encryption role
└── playbook.yml           # Main playbook
```

## Configuration

### Inventory Configuration
The inventory file (inventory/hosts.yml) contains host-specific settings

### Role Variables
Some role has its own variables that can be configured:
- defaults/main.yml: Default variable values
- vars/main.yml: Role-specific variables

### Checking Mode
```bash
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --check
```

## Output and Logs

During the playbook execution, all information will be displayed on the screen

## Notes

- Always backup important data before running encryption tasks
- Network connectivity may be temporarily interrupted during interface renaming
- Check role-specific README files for detailed information