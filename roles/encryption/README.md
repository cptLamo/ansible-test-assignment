# Encryption Role

This role implements disk encryption functionality for:
- Second disk encryption
- Root-adjacent partition encryption

## Requirements

- LUKS2 support in the system
- Sufficient disk space for encryption overhead

## Role Variables

```yaml
# Second disk encryption
device_name: "/dev/xvdf"
encryption_type: "luks2"
encrypted_name: "encrypted_disk"
key_file_disk: "/root/luks-key-disk"
key_file_partition: "/root/luks-key-partition"
```

## Usage

2. Run the role:
```bash
# Run partition encryption role
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags encryption

# Run disk encryption role
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags disk

# Run disk encryption role with specific disk
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags disk -e "device_name=/dev/xvdf"
```

## Handlers

The role includes handlers for:
- Verifying encryption status

## Notes

- Always backup important data before encryption