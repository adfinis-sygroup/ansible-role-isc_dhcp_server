# ROLE isc\_dhcp\_server

[![GitHub](https://img.shields.io/github/license/adfinis-sygroup/ansible-role-isc_dhcp_server.svg?style=flat-square)](https://github.com/adfinis-sygroup/ansible-role-isc_dhcp_server/blob/master/LICENSE)
[![Travis (.org)](https://img.shields.io/travis/adfinis-sygroup/ansible-role-isc_dhcp_server.svg?style=flat-square)](https://travis-ci.org/adfinis-sygroup/ansible-role-isc_dhcp_server)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-adfinis--sygroup.isc_dhcp_server-660198.svg?style=flat-square)](https://galaxy.ansible.com/adfinis-sygroup/isc_dhcp_server)

This role configures and manages the ISC DHCP server.

## Requirements

This role has no additional requirements.

## Role Variables

The following defaults variables can be configured:

``` yaml
# OMAPI synchronization port
isc_dhcp_server_omapi_port: 7911

# DHCP server subnet configuration. Default is not to configure any subnets.
isc_dhcp_server_subnet:
  - netaddress: 192.168.121.0
    netmask: 255.255.255.0
    routers: 192.168.121.1
    domain: lab.local
    domain_search: lab.local
    dns: 192.168.121.1
    range: 192.168.121.20 192.168.121.100
```

The following vars variables are set for Debian / Ubuntu and can be overwritten
if necessary:

``` yaml
# isc_dhcp_server related packages
isc_dhcp_server_pkg: isc-dhcp-server

# isc_dhcp_server daemon
isc_dhcp_server_service: isc-dhcp-server
```

The following vars variables are set for RHEL / CentOS and can be overwritten if
necessary:

``` yaml
# isc_dhcp_server related packages
isc_dhcp_server_pkg: dhcp

# isc_dhcp_server daemon
isc_dhcp_server_service: dhcpd
```

## Dependencies

This role has no additional dependencies.

## Example Playbook

Below example shows how the role can be integrated into a playbook using
external vars:

``` yaml
- hosts: servers
  roles:
    - { role: adfinis-sygroup.isc_dhcp_server }
```

## License

[GPL-3.0](https://github.com/adfinis-sygroup/ansible-role-isc_dhcp_server/blob/master/LICENSE)

## Author Information

isc\_dhcp\_server role was written by:

-   Adfinis SyGroup AG \| [Website](https://www.adfinis-sygroup.ch/) \|
    [Twitter](https://twitter.com/adfinissygroup) \|
    [GitHub](https://github.com/adfinis-sygroup)
