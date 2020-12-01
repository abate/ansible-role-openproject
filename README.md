# Ansible OpenProject

An opinionated role that installs OpenProject as a single Docker multi-container.

While technically a fork of danihodovic/ansible-role-openproject I've re-written
almost everything.

This playbook installs openproject using multiple containers. It also adds traefik
labels to those containers. Can be used with or without traefik.

## Requirements

- poetry ( to install all the dependencies to run the tests )

### Role Variables

Required:

- `openproject_secret_key_base`
- `openproject_db_password`

Optional variables in [defaults.yml](./defaults/main.yml).

Example Playbook
----------------

```yaml
---

- name: Include ansible-role-openproject
  include_role:
    name: ansible-role-openproject
  vars:
    openproject_db_password: passwo4d
    openproject_secret_key_base: secret
    openproject_docker_ports: ['127.0.0.1:8080:8080']
    openproject_docker_network:
      - name: openproject
```

### License

MIT

### Author Information

Pietro Abate

### Credits:

Dani Hodovic (https://depode.com)
