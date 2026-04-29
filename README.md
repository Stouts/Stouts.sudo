Stouts.sudo
===========

[![Galaxy](https://img.shields.io/badge/galaxy-Stouts.sudo-blue.svg?style=flat-square)](https://galaxy.ansible.com/Stouts/sudo)
[![Tag](https://img.shields.io/github/tag/Stouts/Stouts.sudo.svg?style=flat-square)]()

Ansible role which manages the sudoers file.

#### Variables

```yaml
sudo_enabled: true                              # Enable role
sudo_users: []                                  # A list of users who have sudo access
sudo_groups: [admin, sudo]                      # A list of groups who have sudo access
sudo_passwordless: [admin, sudo]                # A list of group/user names which have NOPASSWD
sudo_agent_forwarding: false                    # Preserve `SSH_AUTH_SOCK` when sudoing
sudo_defaults: ['!lecture', '!fqdn']            # List of default entries for configuration
sudo_include_sudoersd: false                    # Include /etc/sudoers.d directory
sudo_passwordless_command: []                   # Give ability to run a specific command without a password
#  - name: someuser
#    command: "/usr/bin/whoami"
```

#### Usage

Add `Stouts.sudo` to your roles and set vars in your playbook file.

Example:

```yaml
- hosts: all
  roles:
    - role: Stouts.sudo
      vars:
        sudo_users: [klen]
        sudo_passwordless: [klen]
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.sudo/issues)!
