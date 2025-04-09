# Ansible Collection - bvierra.opkssh

[![Ansible Galaxy](https://img.shields.io/badge/Ansible%20Galaxy-bvierra.opkssh-blue)](https://galaxy.ansible.com/bvierra/opkssh)
[![License](https://img.shields.io/github/license/bvierra/ansible-role-opkssh-server)](LICENSE)

This Ansible collection provides roles and plugins for managing and configuring [OpenPubkey SSH (opkssh)](https://github.com/openpubkey/opkssh), a tool for managing SSH access using OpenID Connect providers.

## Roles

### `opkssh_server`
This role installs and configures the `opkssh` binary for use with OpenSSH. It supports managing users, configuring OpenID providers, and setting up SELinux policies.

- **Documentation**: See the [role README](roles/opkssh_server/README.md) for detailed usage instructions.

## Requirements

- Ansible >= 2.12
- Supported Platforms:
  - Debian (all versions)

## Installation

To install this collection, use the following command:

```bash
ansible-galaxy collection install bvierra.opkssh
```

Alternatively, include it in your requirements.yml:

```yaml
collections:
  - name: bvierra.opkssh
    version: 1.0.0
```

Then run:

```bash
ansible-galaxy collection install -r requirements.yml
```

## Usage

### Example Playbook

```yaml
- name: Configure opkssh
  hosts: all
  roles:
    - role: bvierra.opkssh.opkssh_server
```
### Variables

Refer to the [role documentation](roles/opkssh_server/README.md) for a complete list of configurable variables.

## License

This collection is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author
Created by [Billy Vierra](https://github.com/bvierra).