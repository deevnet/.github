# Deevnet Platform Architecture

**Deevnet — Defined in code. Delivered through automation.**

Deevnet is a unified platform architecture that applies modern Infrastructure-as-Code practices to both a **production home network** and an isolated **development lab environment**.
Using Ansible, Packer, and Terraform, Deevnet enables automated, reproducible provisioning across physical machines, VMs, and single-board computers.

The platform is structured as:

- **dvnt — Production Environment**
  Stable, always-on home infrastructure running Proxmox, networking gear, and supporting Raspberry Pis. Treated as production-grade.

- **dvntm — Lab / Development Environment**
  A portable, self-contained infrastructure cluster used to experiment, prototype, test, and validate IaC changes before promoting them into production.

Together, these environments form a complete platform for infrastructure engineering and long-term automation development.

---

## What the Deevnet Platform Enables

- **Professional development in modern infrastructure engineering** — Hands-on experience with Terraform, Ansible, Packer, and automated provisioning pipelines.

- **A portable demo and teaching environment** — The dvntm lab supports on-site demonstrations of IaC workflows, Pi clusters, networking concepts, and hardware/software integrations.

- **A controlled sandbox for experimentation** — Safely test new infrastructure patterns, network designs, OS images, and hardware integrations without impacting production.

- **A highly automated home environment** — Automated provisioning of servers, Pis, network devices, and other home systems.

- **A consistent Dev → Prod workflow** — Build and validate in dvntm, refine the IaC, then promote reliably into dvnt.

- **A unified structure for organizing long-term projects** — Clear naming, version-controlled repositories, shared modules, and reproducible pipelines.

---

## Documentation

**[Deevnet Infrastructure Platform Documentation](https://deevnet.github.io/deevnet-docs/)** — Authoritative standards, architecture, and policies for the Deevnet ecosystem.

---

## Public Repositories

### Ansible Collections

| Repository | Description |
|------------|-------------|
| **ansible-collection-deevnet.builder** | Workstation setup, artifact servers (nginx), PXE boot servers, Omada controller, base system roles |
| **ansible-collection-deevnet.mgmt** | Centralized management services — logging, alerting, telemetry, secrets management, provisioning |
| **ansible-collection-deevnet.net** | Network automation for OPNsense, DNS, interfaces, VLANs |

### Ansible Inventory

| Repository | Description |
|------------|-------------|
| **ansible-inventory-deevnet** | Central inventory for platform infrastructure — contains `dvntm/` and `dvnt/` directories for each environment. Tenant applications maintain their own inventories to avoid tight coupling. |

### Image Factory

| Repository | Description |
|------------|-------------|
| **deevnet-image-factory** | Builds reproducible images for Raspberry Pi and Proxmox VMs using Packer |

### Terraform Modules

| Repository | Description |
|------------|-------------|
| **deevnet-terraform** | Terraform modules for infrastructure provisioning |

### Documentation

| Repository | Description |
|------------|-------------|
| **[deevnet-docs](https://deevnet.github.io/deevnet-docs/)** | Authoritative documentation site — standards, architecture, and policies that apply across all repositories |

---

## Platform and Tooling

| Technology | Purpose |
|------------|---------|
| Ansible | Infrastructure provisioning via collections and roles |
| Packer | OS image builds (Raspberry Pi, Proxmox templates) |
| Terraform | Declarative infrastructure provisioning |
| Fedora/RHEL | Primary OS platform (dnf-based, SELinux enabled) |
| Proxmox VE | Virtualization platform |
| Podman | Container runtime (systemd-managed) |

---

## Vision

Deevnet exists to:

- Apply cloud engineering principles to real environments
- Provide a robust platform for developing modern IaC skills
- Enable portable demonstrations, teaching, and community engagement
- Support reproducible hardware and software project workflows
- Maintain a stable, automated home environment through deterministic builds
- Encourage continuous learning, experimentation, and technical exploration

**Deevnet is an evolving automation platform—built in public, defined in code, and driven by curiosity.**
