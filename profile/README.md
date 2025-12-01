# **Deevnet Platform Architecture**  
### *Deevnet — Defined in code. Delivered through automation.*

**Deevnet** is a unified platform architecture that applies modern Infrastructure-as-Code practices to both a **production home network** and an isolated **development lab environment**.  
Using **Terraform, Ansible, Packer, Vault, and MinIO**, Deevnet enables automated, reproducible provisioning across physical machines, VMs, and single-board computers.

The platform is structured as:

- **dvnt — Production Environment**  
  Stable, always-on home infrastructure running Proxmox, UniFi networking, Windows/NAS systems, and supporting Raspberry Pis. Treated as a production-grade environment.

- **dvntm — Lab / Development Environment**  
  A portable, self-contained infrastructure cluster used to experiment, prototype, test, and validate IaC changes before promoting them into production.

Together, these environments form a complete platform for infrastructure engineering and long-term automation development.

---

## 🧭 What the Deevnet Platform Enables

The Deevnet platform serves as a foundation for personal, professional, and creative growth. It enables:

- **Professional development in modern infrastructure engineering**  
  Hands-on experience with Terraform, Ansible, Packer, Vault, monitoring, PKI, and automated provisioning pipelines.

- **A portable demo and teaching environment for Meetups & workshops**  
  The dvntm lab supports on-site demonstrations of IaC workflows, Pi clusters, networking concepts, automation pipelines, and hardware/software integrations.

- **A controlled sandbox for experimentation and R&D**  
  Safely test new infrastructure patterns, network designs, OS images, and hardware integrations without impacting production services.

- **A highly automated home environment**  
  Automated provisioning of servers, Pis, network devices, monitoring components, and other home systems.

- **A platform for reproducible hardware/software projects**  
  Supporting Pi image factories, microcontrollers, CAD/PCB tooling, and OOB management solutions.

- **A consistent Dev → Prod workflow across all devices**  
  Build and validate in dvntm, refine the IaC modules, then promote reliably into dvnt.

- **A personal engineering playground for curiosity-driven learning**  
  Exploration of computing, networking, audio/digital systems, embedded hardware, and other technical domains.

- **A unified structure for organizing long-term projects**  
  Clear naming, version-controlled repositories, shared modules, and reproducible pipelines maintain order and sustainability over time.

---

## 📦 Public Repositories

### **Ansible Collections**
- **ansible-collection-deevnet.common** – Baseline system roles: admin tools, users, security hardening, exporters.  
- **ansible-collection-deevnet.net** – Network automation: OPNsense, UniFi, DNS, interfaces, VLANs.  

### **Terraform Modules**
- **tf-proxmox-vm** – Declarative VM lifecycle automation (cloud-init, VLANs, tags).  
- **tf-opnsense** – Firewall automation: interfaces, VLANs, DHCP, NAT, rules, aliases.  
- **tf-unifi** – Automated UniFi configuration: SSIDs, networks, VLANs, switch profiles.
- **tf-omada** – Automated TP-Link configuration: SSIDs, networks, VLANs, switch profiles. 
- **tf-dns-core** – DNS zone and record management (`service.env.deevnet.net`).  
- **tf-minio-backend** – S3-compatible Terraform state backed by MinIO and secured via Vault.  
- **tf-vault-core** – Vault bootstrap: auth methods, policies, KV engines, transit.  
- **tf-vault-pki** – PKI automation: root/intermediate CAs, short-lived certificates.  

### **Image Factory**
- **deevnet-image-factory** – Builds reproducible images for VMs, PCs and single-board computers, using Packer and Ansible, with optional Terraform glue.

### **Samples & Documentation**
- **infra-sample** – Demonstrates end-to-end module usage with example values.  
- **infra-ops** – Shared documentation, runbooks, diagrams, and helper scripts.

---

## 🔒 Private Repositories

- **infra-dvnt** – Full IaC definition for the at home production environment.  
- **infra-dvntm** – Full IaC definition for the mobile development environment.

Both environments use **Vault** for secret management and **MinIO** for S3-compatible Terraform state storage.

---

## 🏁 Vision

Deevnet exists to:

- Apply cloud engineering principles to real environments  
- Provide a robust platform for developing and refining modern IaC skills  
- Enable portable demonstrations, teaching, and community engagement  
- Support reproducible hardware and software project workflows  
- Maintain a stable, automated home environment through deterministic builds  
- Encourage continuous learning, experimentation, and technical exploration  

**Deevnet is an evolving automation platform—built in public, defined in code, and driven by curiosity.**

