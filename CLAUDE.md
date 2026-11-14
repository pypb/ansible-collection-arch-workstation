# pypb.arch_workstation

Ansible collection for configuring and maintaining an Arch Linux workstation.
It is currently an empty skeleton.

## Content

- Roles: none yet
- Playbooks: none yet
- Plugins: none yet

Update these lists, and the matching sections of `README.md`, when content is
added.

## Commands

- Build: `ansible-galaxy collection build`
- Install dependencies: `uv sync`
- Lint: `yamllint .`, `ansible-lint` and `ruff check .`
- Sanity tests: `ansible-test sanity --docker default`
- Molecule: run `molecule test --scenario-name <name>` from `extensions/`, with
  `ANSIBLE_COLLECTIONS_PATH` covering this collection and its dependencies.
  With Podman, also start the API socket and set `DOCKER_HOST`
- Changelog: add a fragment to `changelogs/fragments/`, then run
  `antsibull-changelog release` when releasing

Python dependencies are declared in `pyproject.toml`. Its `version` is separate
from the collection version in `galaxy.yml`, which is the one that matters for
releases.

## Conventions

- Follow the Red Hat CoP automation good practices:
  https://github.com/redhat-cop/automation-good-practices
- Role names are snake_case. Each role has `meta/argument_specs.yml`.
- Target Arch Linux only. Install packages with `community.general.pacman`, and
  AUR packages through a helper rather than building them as root.
- Keep system-wide configuration (run with become) separate from per-user
  configuration, so user roles can run without root.
- Document collection-wide variables in `README.md`, since they are referenced
  from role defaults rather than declared explicitly.
- When adding a role, also add a scenario in `extensions/molecule/`, using a
  `docker.io/library/archlinux` based image with systemd, and list it in a
  molecule job in `.github/workflows/ci.yml`.
- This repo is public. Keep machine-specific hostnames, usernames and secrets
  out of it.
