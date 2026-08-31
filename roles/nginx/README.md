# Ansible Role: Nginx

An Ansible role that installs, configures, and manages the Nginx web server on Linux distributions.

## Requirements

* Minimum Ansible version: `2.9`
* Root/sudo privileges on target hosts (`become: true`)
* Supported OS: Linux distributions using standard package managers (`apt`, `dnf`, `yum`)

## Role Variables

Available variables are defined in `defaults/main.yml`:

| Variable | Default | Description |
| --- | --- | --- |
| `nginx_port` | `80` | Port for Nginx to listen on |

## Dependencies

None.

## Example Playbook

```yaml
- name: Deploy Nginx Web Server
  hosts: webservers
  become: true
  roles:
    - role: nginx
      vars:
        nginx_port: 8080

