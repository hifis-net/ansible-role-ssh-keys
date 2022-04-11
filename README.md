<!--
SPDX-FileCopyrightText: 2020 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2020 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

# SSH Keys Role

[![CI Status](https://github.com/hifis-net/ansible-role-ssh-keys/actions/workflows/ci.yml/badge.svg)](https://github.com/hifis-net/ansible-role-ssh-keys/actions/workflows/ci.yml)
[![Ansible Galaxy Role](https://img.shields.io/ansible/role/52667?color=orange)](https://galaxy.ansible.com/hifis/ssh_keys)
[![Ansible Galaxy Role downloads](https://img.shields.io/ansible/role/d/52667)](https://galaxy.ansible.com/hifis/ssh_keys)
[![Ansible Galaxy quality score](https://img.shields.io/ansible/quality/52667)](https://galaxy.ansible.com/hifis/ssh_keys)
[![Apache-2.0 Licensed](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/hifis-net/ansible-role-ssh-keys/blob/main/LICENSES/Apache-2.0.txt)
[![Latest release](https://img.shields.io/github/v/release/hifis-net/ansible-role-ssh-keys)](https://github.com/hifis-net/ansible-role-ssh-keys/releases)

This Ansible role distributes authorized SSH public keys to users.

Currently [supported platforms](meta/main.yml) are:

- CentOS 7
- CentOS 8
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Debian Stretch
- Debian Buster

## Requirements

None.

## Role Variables

```yaml
ssh_user_list:
  - name: root
    authorized_keys:
      - ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJi3wBlOT+oR8Rd+YQsV8tUoQOd3NSUuyzJYQp8finD6 john@example.com
      - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQDXkvy8jMmw45grnmYK+Ylk/mcc7IyG9taNseNiVrGjR8KRHVJpzEntW1g6SAomIGIpBLvviiyhal4E1v1bhpv2JopbiM3JDOck6gwc4AfpanjuZFPuq6stq5pF7bb2C+zliw16zTFL7bp09tD7nNs30GlchB5DU2sSn1zq4iC+eQ== john@example.com
```
In order to authorize SSH public keys you need to edit the variable
`ssh_user_list` and add a list entry containing the `name` of the user and a
list of `authorized_keys`. Each list entry corresponds to one user account.

```yaml
ssh_authorized_keys_exclusive: true
```
Whether to remove all other non-specified keys from the authorized_keys file.

## Dependencies

None.

## License

[Apache-2.0](LICENSES/Apache-2.0.txt)

## Author Information

This role was created by [HIFIS Software Services](https://software.hifis.net/).
