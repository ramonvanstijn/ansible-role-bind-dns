# Ansible Role: BIND DNS

Installs and configures BIND DNS on RedHat Linux servers.

## Requirements

None.

## Role Variables

Available variables are listed below (see `defaults/main.yml`):

    dns_domain_name: ""

    dns_cidr: ""

    dns_records: []

## Dependencies

None.

## Example Playbook

    - hosts: dns_server
      become: yes
      vars:
        dns_domain_name: example.com
        dns_cidr: 192.168.1.0/24
        dns_records:
          - name: control-plane
            ipaddress: "192.168.1.10"
          - name: compute
            ipaddress: "192.168.1.11"
      roles:
        - { role: bind-dns }
