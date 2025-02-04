# CPU Tuning Role

This role manages CPU power states and performance settings:
- Disabling C-states for all processors
- Checking cpu performance mode

## Requirements

- kernel-tools package

## Usage

1. Run the role:
```bash
# Run only cpu c-state role
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags cstate

# Run only check performance cpu role
ansible-playbook -i inventory/hosts.yml playbook.yml -u "username" --tags performance
```

## Handlers

The role includes handlers for:
- Verifying C-states status
- Displaying CPU information

## Notes

- Performance impact should be monitored after changes