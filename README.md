# Ansible role archive
A role to generate archives

## Requirements
- Hosts should be bootstrapped for ansible usage (have python,...)

## Role Variables

| Variable | Description | Default value |
|----------|-------------|---------------|
| `rsync_directories` | Definitions for directories to synchronize. See below for details. | [] |


### `rsync_directories` details

The following params are params provided by this role. Since this role is a wrapper for Ansibles `synchronize` module all
available params are documented in the official [Ansible docs](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters). 

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| excludes | List of files and directories to exclude when syncing | no | [] |
| pre_sync_commands | List of commands to execute on the remote machine before synching | no | [] |
| post_sync_commands | List of commands to execute on the remote machine after synching | no | [] |

The following are the default vars for Ansibles `synchronize` module.

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| src | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| dest | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| rsync_opts | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| archive | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| checksum | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| compress | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| copy_links | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| delete | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| dest_port | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| dirs | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| existing_only | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| group | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| link_dest | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| links | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| mode | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| owner | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| partial | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| perms | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| private_key | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| recursive | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| rsync_path | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| rsync_timeout | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| set_remote_user | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| times | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| use_ssh_args | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |
| verify_host | See [Ansible docs for synchronize](https://docs.ansible.com/ansible/latest/modules/synchronize_module.html#parameters) | / | / |


## Dependencies

--

## Example playbook
```yaml
- name: Syncing directories
  hosts: rsync
  roles:
    - role: phizzl.rsync
      vars:
        rsync_directories:
          - path: /var/www/source/
            dest: /media/backup/target/
            excludes:
              - .git/
            mode: pull
```
