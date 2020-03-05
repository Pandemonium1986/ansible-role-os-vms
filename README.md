# Ansible role : OpenStack Appliances

![](https://img.shields.io/github/release/Pandemonium1986/ansible-role-os-appliances.svg)
![](https://img.shields.io/github/repo-size/Pandemonium1986/ansible-role-os-appliances.svg)
![](https://img.shields.io/github/release-date/Pandemonium1986/ansible-role-os-appliances.svg)
![](https://img.shields.io/github/license/Pandemonium1986/ansible-role-os-appliances.svg)

Configure the resources needed for an OpenStack project.

-   network
-   subnet
-   router
-   security_group
-   security_group_rules
-   keypair
-   server_group

## Requirements

This role is not self contained. He requires pandemonium1986.os_requirements to work correctly.

```sh
  ansible-galaxy install -f pandemonium1986.os_requirements
```

## Role Variables

From defaults/main.yml :

```yaml
osappliances_users:
  - pandemonium
osappliances_openstack_project_name: "pandama"
osappliances_os_router_network:      "external-public"
```

## Dependencies

-   pandemonium1986.os_requirements

## Example Playbook

```yaml
- name : Openstack deployement
  hosts: local
  become: true
  tasks:
    - import_role:
        name: pandemonium1986.os_appliances
```

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details

## Author Information

-   **Michael Maffait** - _Initial work_ - [Pandemonium1986](https://github.com/Pandemonium1986)
