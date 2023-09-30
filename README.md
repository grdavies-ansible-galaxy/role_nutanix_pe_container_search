# Nutanix Role to search for a container UUID from a name

This Ansible role will search for a container UUID based on the supplied container name.

## Input Variables

| Variable                                             | Required | Default | Choices                   | Comments                                                                             |
|------------------------------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------|
| role_nutanix_pe_container_search_host                | yes      |         |                           | The IP address or FQDN for the Prism (Element only) which you want to connect.       |
| role_nutanix_pe_container_search_host_username       | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                  |
| role_nutanix_pe_container_search_host_password       | yes      |         |                           | A valid password for the supplied username.                                          |
| role_nutanix_pe_container_search_host_port           | no       | 9440    |                           | The Prism TCP port.                                                                  |
| role_nutanix_pe_container_search_host_validate_certs | no       | false   | true / false              | Whether to check if Prism UI certificates are valid.                                 |
| role_nutanix_pe_container_search_name                | yes      |         |                           | Name of container to search for.                                                     |
| role_nutanix_pe_container_search_debug               | no       | false   | true / false              | Enable debug logging.                                                                |

## Output Variables

| Variable                                    | Required | Default | Choices                   | Comments                                                                            |
|---------------------------------------------|----------|---------|---------------------------|-------------------------------------------------------------------------------------|
| role_nutanix_pe_container_search_found_uuid |          |         |                           | If a container is found its UUID will be returned in this variable                  |

## Dependencies

- grdavies.role_nutanix_prism_api

## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - grdavies.role_nutanix_pe_container_search
  vars:
    role_nutanix_pe_container_search_host: 10.38.185.37
    role_nutanix_pe_container_search_host_username: admin
    role_nutanix_pe_container_search_host_password: nx2Tech165!
    role_nutanix_pe_container_search_name: Default
```

## License

See LICENSE.md

## Author Information

Ross Davies
