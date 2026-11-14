# pypb.arch_workstation

Ansible roles and playbooks for configuring and maintaining my Arch Linux
workstation.

This collection is a skeleton for now.

## Requirements

- ansible-core 2.21 or newer
- [`community.general`](https://docs.ansible.com/ansible/latest/collections/community/general/)
  9.0.0 or newer, which is installed automatically with this collection
- Arch Linux on the managed host

## Installation

The collection is not published on Ansible Galaxy. Install it from Git:

```shell
ansible-galaxy collection install git+https://github.com/pypb/ansible-collection-arch-workstation.git
```

## Content

### Roles

None yet.

### Playbooks

None yet.

### Plugins

None yet.

### Collection-wide variables

None yet. Roles that share configuration should reference a collection-wide
variable from their `defaults/main.yml`, and that variable should be documented
here.

## Development

Clone the repository to a path ending in `ansible_collections/pypb/arch_workstation`,
which `ansible-test` requires.

```shell
uv sync

yamllint .
ansible-lint
ruff check .
ansible-test sanity --docker default
ansible-galaxy collection build
```

Molecule scenarios live in `extensions/molecule/`. Run them from `extensions/`
with `molecule test --scenario-name <name>`. They need Docker, or Podman with
its API socket enabled and `DOCKER_HOST` pointing to it, and this collection and
its dependencies on `ANSIBLE_COLLECTIONS_PATH`.

Describe each change in a fragment under `changelogs/fragments/`, then generate
the changelog at release time with `antsibull-changelog release`.

## License

Apache License 2.0. See [LICENSE](LICENSE) for the full text.
