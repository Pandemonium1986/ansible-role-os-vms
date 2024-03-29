# Ansible role : OpenStack Vms

![Ansible Role](https://img.shields.io/ansible/role/47135?logo=ansible)
![Gitlab pipeline status](https://img.shields.io/gitlab/pipeline/Pandemonium1986/ansible-role-os-vms?logo=gitlab)
![GitHub release](https://img.shields.io/github/release/Pandemonium1986/ansible-role-os-vms.svg?logo=github)
![Github license](https://img.shields.io/github/license/Pandemonium1986/ansible-role-os-vms.svg?logo=github)
![Ansible Quality Score](https://img.shields.io/ansible/quality/47135?logo=ansible)

Deploy vms into an OpenStack project.

## Disclaimer

!!! This images is no longer support.!!!

## Requirements

This role is not self contained. He requires pandemonium1986.os_appliances to work correctly.

```sh
  ansible-galaxy install -f pandemonium1986.os_appliances
```

## Role Variables

From defaults/main.yml :

```yaml
osvms_users:
  - pandemonium
osvms_openstack_project_name: "pandama"
osvms_vms:
  - { name: "default", flavor: "tiny", image: "cirros", auto_ip: true, delete_fip: true, volume_size: 10 }
```

## Dependencies

- pandemonium1986.os_appliances

## Example Playbook

```yaml
- name : Openstack deployement
  hosts: local
  become: true
  tasks:
    - import_role:
        name: pandemonium1986.os_appliances
```

## Note

`osvms_openstack_project_name` must be the same as the one declared in os_appliances.  
For molecule users you have to export two variables :

- OPENSTACK_HOSTNAME="your_open_stack_fqdn"
- OPENSTACK_IP="your_open_stack_ip"

The goal is to add an entry in the hosts file of container

```sh
export OPENSTACK_HOSTNAME="your_open_stack_fqdn" export OPENSTACK_IP="your_open_stack_ip"
molecule test
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

## Author Information

- **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
