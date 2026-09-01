# Ansible Role: Nginx & Firewalld

An Ansible role that installs and enables Nginx and Firewalld, then configures firewall rules to allow HTTP and HTTPS traffic on ports 80/tcp and 443/tcp.

## Requirements

* Target OS: RHEL, CentOS, Rocky Linux, AlmaLinux, or Fedora
* Privileges: Root or sudo access (`become: true`)
* Ansible Collections: `ansible.posix`

To install the required collection:
```bash
ansible-galaxy collection install ansible.posix
```
## Role Variables
| Variable | Default | Description |
| ---  |  ---  |  ---  |
| `firewalld_zone` | `public` | The firewalld zone to apply rules to |
| `firewalld_services` |`['http', 'https']` | Firewall service names to allow |
| `nginx_ports` | `['80/tcp', '443/tcp']` | Ports to allow explicitly |

## Handlers

** Restart firewalld:** Triggered whenever changes are made to allowed services or ports

## Depedencies

**None**

## Example Playbook

```yaml
---
- name: Configure Web Servers
  hosts: webservers
  become: true
  roles:
    - role: firewalld
```
