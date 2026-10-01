# Infrastructure as Code (IaC): Linux Baseline Hardening

Automated provisioning and baseline security hardening playbooks targeting Debian/Ubuntu and ARM64 edge nodes via Ansible.

## Scope of Automation
- **System Maintenance:** Automated repository sync and package upgrades.
- **Defensive Tooling:** Installs and enables `fail2ban`, `ufw`, and baseline system monitoring tools.
- **SSH Hardening:** Enforces `PermitRootLogin no`, disables empty passwords, and restricts `MaxAuthTries` via validated config injection.
- **Network Ingress Control:** Implements a default-deny ingress policy with explicit SSH port scoping.

## Setup & Execution
1. Copy the example inventory and edit your target host details:
   ```bash
   cp inventory.example.ini inventory.ini

2. Execute the playbook
ansible-playbook baseline.yml -i inventory.ini --ask-become-pass
