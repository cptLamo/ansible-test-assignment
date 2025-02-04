# Network Role

This role manages network interface configuration for Ubuntu server:
- Renaming active network interface to "net0"
- Displaying network interface information
- Showing processor and threading information

## Requirements

- NetworkManager
- Root/sudo access

## Role Variables

### Default Variables (defaults/main.yml)

### Role Variables (vars/main.yml)
```yaml
# Net interface 
new_interface_name: "net0"
net_interface_path: "/etc/netplan/"
```

## Usage

1. Configure variable of the interface in your vars:
```yaml
  new_interface_name: "net0"
```

2. Run the role:
```bash
# Run rename role
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags rename
```

## Handlers

The role includes handlers for:
- Verifying interface rename
- Showing network status
- Updating network configuration
- CPU info

## Notes

- Network connectivity may be temporarily interrupted during interface renaming
