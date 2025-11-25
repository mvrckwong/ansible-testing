# infrastructure-ansible

Reusable Ansible scaffold for local VM bootstrap. Structure mirrors the
standard best-practice layout documented by the Ansible project.

## Layout

- `inventory/hosts.yml`: inventory groups and hosts
- `playbooks/`: entry-point playbooks (site + VM specific)
- `roles/base_config/`: baseline packages, dotfiles, and handler hooks
- `files/`: supporting static assets copied by roles
- `group_vars/all.yml`: defaults applied to every host
- `host_vars/<hostname>.yml`: host overrides

## Usage

1. Run `task install` to `uv sync` the `infra` dependency group.
2. Update `inventory/hosts.yml` with your hosts and SSH users.
3. Adjust variables in `group_vars/all.yml` and host overrides as needed.
4. Run `task ping` to validate connectivity.
5. Apply configuration with `task site` or `task configure-vm`.
