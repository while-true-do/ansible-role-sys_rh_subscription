<!--
name: README.md
description: This file contains important information for the repository.
author: while-true-do.io
contact: hello@while-true-do.io
license: BSD-3-Clause
-->

<!-- github shields -->
[![Github (tag)](https://img.shields.io/github/tag/while-true-do/ansible-role-sys_rh_subscription.svg)](https://github.com/while-true-do/ansible-role-sys_rh_subscription/tags)
[![Github (license)](https://img.shields.io/github/license/while-true-do/ansible-role-sys_rh_subscription.svg)](https://github.com/while-true-do/ansible-role-sys_rh_subscription/blob/master/LICENSE)
[![Github (issues)](https://img.shields.io/github/issues/while-true-do/ansible-role-sys_rh_subscription.svg)](https://github.com/while-true-do/ansible-role-sys_rh_subscription/issues)
[![Github (pull requests)](https://img.shields.io/github/issues-pr/while-true-do/ansible-role-sys_rh_subscription.svg)](https://github.com/while-true-do/ansible-role-sys_rh_subscription/pulls)
<!-- travis shields -->
[![Travis (com)](https://img.shields.io/travis/com/while-true-do/ansible-role-sys_rh_subscription.svg)](https://travis-ci.com/while-true-do/ansible-role-sys_rh_subscription)
<!-- ansible shields -->
[![Ansible (min. version)](https://img.shields.io/badge/dynamic/yaml.svg?label=Min.%20Ansible%20Version&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwhile-true-do%2Fansible-role-sys_rh_subscription%2Fmaster%2Fmeta%2Fmain.yml&query=%24.galaxy_info.min_ansible_version&colorB=black)](https://galaxy.ansible.com/while_true_do/sys_rh_subscription)
[![Ansible (platforms)](https://img.shields.io/badge/dynamic/yaml.svg?label=Supported%20OS&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwhile-true-do%2Fansible-role-sys_rh_subscription%2Fmaster%2Fmeta%2Fmain.yml&query=galaxy_info.platforms%5B*%5D.name&colorB=black)](https://galaxy.ansible.com/while_true_do/sys_rh_subscription)
[![Ansible (tags)](https://img.shields.io/badge/dynamic/yaml.svg?label=Galaxy%20Tags&url=https%3A%2F%2Fraw.githubusercontent.com%2Fwhile-true-do%2Fansible-role-sys_rh_subscription%2Fmaster%2Fmeta%2Fmain.yml&query=%24.galaxy_info.galaxy_tags%5B*%5D&colorB=black)](https://galaxy.ansible.com/while_true_do/sys_rh_subscription)

# Ansible Role: sys_rh_subscription

An Ansible Role to register a RedHat System to a RedHat Subscription Service.

## Motivation

Subscribing a RedHat System to a proper Subscription Manager is a very common
task and should be done properly.

## Description

This Ansible Role subscribes a RedHat System to a Subscription Manager Service:

- install subscription-manager packages
- register via activation key

## Requirements

Used Modules:

-   [Ansible Package Module](https://docs.ansible.com/ansible/latest/modules/package_module.html)
-   [Ansible RedHat Subscription Module](https://docs.ansible.com/ansible/latest/modules/redhat_subscription_module.html)

## Installation

Install from [Ansible Galaxy](https://galaxy.ansible.com/while_true_do/sys_rh_subscription)
```
ansible-galaxy install while_true_do.sys_rh_subscription
```

Install from [Github](https://github.com/while-true-do/ansible-role-sys_rh_subscription)
```
git clone https://github.com/while-true-do/ansible-role-sys_rh_subscription.git while_true_do.sys_rh_subscription
```

## Usage

### Role Variables

```
---
# defaults file for while_true_do.sys_rh_subscription

## Package Management
wtd_sys_rh_subscription_package: "subscription-manager"
# State can be present|latest|absent
wtd_sys_rh_subscription_package_state: "present"

## Configuration Management
# Configuration to register the system to a RHSM Service.
# You need to prepare activiation keys for this Role and attach subscriptions
# to it.
wtd_sys_rh_subscription_handle:
  organisation_id: ""
  activiation_key: ""
  state: "present"
```

### Example Playbook

Running Ansible
[Roles](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html)
can be done in a
[playbook](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html).

#### Simple

```
---
- hosts: all
  roles:
    - role: while_true_do.sys_rh_subscription
      wtd_sys_rh_subscription_handle:
        organisation_id: "<my Organisation Number (123456789)"
        activiation_key: "<my Key Name>"
```

## Known Issues

1.  RedHat Testing is currently not possible in public, due to limitations
    in subscriptions.
2.  Some services and features cannot be tested properly, due to limitations
    in docker.

## Testing

Most of the "generic" tests are located in the
[Test Library](https://github.com/while-true-do/test-library).

Ansible specific testing is done with
[Molecule](https://molecule.readthedocs.io/en/stable/).

Infrastructure testing is done with
[testinfra](https://testinfra.readthedocs.io/en/stable/).

Automated testing is done with [Travis CI](https://travis-ci.com/while-true-do).

## Contribute

Thank you so much for considering to contribute. We are very happy, when somebody
is joining the hard work. Please fell free to open
[Bugs, Feature Requests](https://github.com/while-true-do/ansible-role-sys_rh_subscription/issues)
or [Pull Requests](https://github.com/while-true-do/ansible-role-sys_rh_subscription/pulls) after
reading the [Contribution Guideline](https://github.com/while-true-do/doc-library/blob/master/docs/CONTRIBUTING.md).

See who has contributed already in the [kudos.txt](./kudos.txt).

## License

This work is licensed under a [BSD-3-Clause License](https://opensource.org/licenses/BSD-3-Clause).

## Contact

-   Site <https://while-true-do.io>
-   Twitter <https://twitter.com/wtd_news>
-   Code <https://github.com/while-true-do>
-   Mail [hello@while-true-do.io](mailto:hello@while-true-do.io)
-   IRC [freenode, #while-true-do](https://webchat.freenode.net/?channels=while-true-do)
-   Telegram <https://t.me/while_true_do>
