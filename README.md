# openstack-kolla

Agent-driven OpenStack cloud deployment and operations using [kolla-ansible](https://docs.openstack.org/kolla-ansible/latest/). Covers the full lifecycle: configuration, deployment, health checking, troubleshooting, and day-two operations.

## Supported Platforms

| OpenStack Release | Host OS |
|---|---|
| 2025.1 (Epoxy) | Rocky Linux 10+, Ubuntu 24.04 |
| 2025.2 | Rocky Linux 10+, Ubuntu 24.04 |

## Skills

| Skill | Description |
|---|---|
| [config-build](skills/config-build/) | Build globals.yml, inventory, and service configs from operator requirements |
| [deploy](skills/deploy/) | Full kolla-ansible deploy lifecycle — bootstrap, prechecks, pull, deploy, post-deploy |
| [health-check](skills/health-check/) | Validate environment health — APIs, agents, containers, networking |
| [diagnose](skills/diagnose/) | Systematic troubleshooting — logs, configs, container state, infrastructure |
| [day-two](skills/day-two/) | Day-two operations — add compute, reconfigure, upgrade, enable services |
| [decision-guides](skills/reference/decision-guides/) | Choose between networking modes (OVN/OVS/LinuxBridge) and storage backends (Ceph/LVM/NFS) |
| [compatibility](skills/reference/compatibility/) | Version compatibility matrix — OpenStack release x distro x networking x storage |
| [known-issues](skills/reference/known-issues/) | Known bugs and workarounds for supported OpenStack releases |

## Usage

This is an [agentic stack](https://github.com/agentic-stacks/agentic-stacks). Point an AI coding agent at a project directory with a `CLAUDE.md` that references this stack, then describe what you want to deploy. The agent uses the skills above to guide you through configuration, deployment, and operations.

### Quick Start

1. Create a new project directory
2. Install the stack (adds `CLAUDE.md`, `stacks.lock`, and `.stacks/openstack-kolla/`)
3. Tell the agent about your infrastructure — host count, roles, networking, storage, target release
4. The agent builds your configuration, runs deployment, and validates the result

All generated files are standard kolla-ansible format — no custom wrappers. You can use `kolla-ansible` directly at any point.

## Requirements

- Python >= 3.11
- [kolla-ansible](https://docs.openstack.org/kolla-ansible/latest/)
- [OpenStack CLI](https://docs.openstack.org/python-openstackclient/latest/)
- Docker

## License

See [LICENSE](LICENSE).
