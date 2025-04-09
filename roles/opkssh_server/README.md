# Ansible Role: OpenPubkey SSH (opkssh)

[![Ansible Role](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/)  
[![License](https://img.shields.io/github/license/bvierra/ansible-role-opkssh-server)](LICENSE)

This Ansible role installs and configures [OpenPubkey SSH (opkssh)](https://github.com/openpubkey/opkssh), a tool for managing SSH access using OpenID Connect providers.

## Requirements

- Ansible >= 2.12
- Supported Platforms:
  - Debian (all versions)

## Role Variables

The following variables can be customized in your playbook or inventory:

### General Configuration
| Variable                          | Default Value | Description                                                                 |
|-----------------------------------|---------------|-----------------------------------------------------------------------------|
| `opkssh_disable_home_policy`      | `false`       | Disable policy files in user home directories.                             |
| `opkssh_restart_sshd`             | `true`        | Restart `sshd` to apply changes.                                           |
| `opkssh_version`                  | `"0.3.0"`     | Version of `opkssh` to install. Use `"latest"` to always fetch the latest. |
| `opkssh_manage_auth_id`           | `true`        | Manage the `auth_id` file for user access.                                 |

### Provider Configuration
| Variable                          | Default Value | Description                                                                 |
|-----------------------------------|---------------|-----------------------------------------------------------------------------|
| `opkssh_providers_google`         | `true`        | Enable Google as an OpenID provider.                                       |
| `opkssh_providers_microsoft`      | `true`        | Enable Microsoft as an OpenID provider.                                    |
| `opkssh_providers_gitlab`         | `true`        | Enable GitLab as an OpenID provider.                                       |
| `opkssh_providers_google_expiration` | `"24h"`    | Token expiration for Google provider.                                      |
| `opkssh_providers_microsoft_expiration` | `"24h"` | Token expiration for Microsoft provider.                                   |
| `opkssh_providers_gitlab_expiration` | `"24h"`    | Token expiration for GitLab provider.                                      |

### User Configuration
Define users in the `opkssh_users` list:
```yaml
opkssh_users:
  - principal: "user"
    id: "user@example.com"
    issuer: "google"
  - principal: "admin"
    id: "admin@example.com"
    issuer: "microsoft"
```