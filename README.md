# Ansible Role: Puppet Agent

[![CI](https://github.com/LPARS/ansible-role-puppet-agent/actions/workflows/ci.yml/badge.svg)](https://github.com/LPARS/ansible-role-puppet-agent/actions/workflows/ci.yml)

This role installs [Puppet](https://www.puppet.com) or [OpenVox](https://voxpupuli.org/openvox/) agent on Linux.

## Requirements

This role requires the `community.general` collection to be installed. You can include it in your
`requirements.yml` like this:

```
---
collections:
  - name: community.general
    version: ">12.0.0"
```

## Role Variables

    puppet_variant: "openvox"

The variant of the agent package to install. Choices include puppet or openvox. Defaults to `openvox`.

    puppet_version: "8"

The major version of Puppet/OpenVox to be installed. Defaults to version `8`.

    puppet_agent_server_fqdn: ""

The server the Puppet/OpenVox agent will request its catalog from.

    puppet_agent_service_state: "started"
    puppet_agent_service_enabled: true
    puppet_agent_service_manage: false

The state of the Puppet/OpenVox agent service. By default, this role will not manage it.

## Dependencies

None.

## Example Playbook

      hosts: all
      become: true
      roles:
        - lpars.puppet_agent

## License

MIT

## Acknowledgments

This Ansible role was inspired by Jeff Geerling's https://github.com/geerlingguy/ansible-role-puppet. A huge thanks to him for helping me learn Ansible.
