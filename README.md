Nutanix Role to search for a container UUID from a name
=========

This Ansible role will search for a container UUID based on the supplied container name.


Role Variables
--------------

Inputs

| Variable                      | Required | Default | Choices                   | Comments                                                                             |
|-------------------------------|----------|---------|---------------------------|--------------------------------------------------------------------------------------|
| nutanix_host                  | yes      |         |                           | The IP address or FQDN for the Prism (Element only) which you want to connect.       |
| nutanix_username              | yes      |         |                           | A valid username with appropriate rights to access the Nutanix API.                  |
| nutanix_password              | yes      |         |                           | A valid password for the supplied username.                                          |
| nutanix_port                  | no       | 9440    |                           | The Prism TCP port.                                                                  |
| validate_certs                | no       | no      | yes | no                  | Whether to check if Prism UI certificates are valid.                                 |
| nutanix_container_search_name | yes      |         |                           | Name of container to search for.                                                     |


Outputs

| Variable                     | Required | Default | Choices                   | Comments                                                                            |
|------------------------------|----------|---------|---------------------------|-------------------------------------------------------------------------------------|
| nutanix_container_found_uuid |          |         |                           | If a container is found its UUID will be returned in this variable                  |


Dependencies
------------

None.

Example Playbook
----------------

```
- hosts: localhost
  gather_facts: false
  roles:
    - grdavies.role_nutanix_pe_container_search
  vars:
    nutanix_host: 10.38.185.37
    nutanix_username: admin
    nutanix_password: nx2Tech165!
    nutanix_container_search_name: Default
```

License
-------

See LICENSE.md

Author Information
------------------

Ross Davies
