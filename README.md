# Deevnet Infrastructure

**Deevnet** is a collection of infrastructure-as-code projects that define my home (dvnt) and mobile (dvntm) labs.  
The goal: fully reproducible, automated environments using Terraform, Ansible, Packer, Vault, and MinIO.

- **Home lab (dvnt):** UniFi network, Proxmox cluster, Windows/NAS servers.  
- **Mobile lab (dvntm):** two Proxmox servers, OPNsense firewall, admin Pi, and a Pi cluster.  
- **Common code:** shared Ansible collections, Terraform modules, and Packer image builds.  
- **Security:** HashiCorp Vault manages all secrets and PKI; MinIO provides S3-compatible Terraform state storage.

---

## 📦 Public Repositories

### Ansible Collections
- [**ansible-collection-deevnet.common**](./ansible-collection-deevnet.common) – Baseline roles (admin tools, node_exporter, hardening, users).  
- [**ansible-collection-deevnet.net**](./ansible-collection-deevnet.net) – Network helpers (OPNsense, UniFi, DNS).  
- [**ansible-collection-deevnet.pi**](./ansible-collection-deevnet.pi) – Pi bootstrap, udev/FTDI, ser2net.  

### Terraform Modules
- [**tf-proxmox-vm**](./tf-proxmox-vm) – Proxmox VM lifecycle (cloud-init, VLANs, tags).  
- [**tf-opnsense**](./tf-opnsense) – Firewall rules, VLANs, DHCP, NAT via OPNsense API.  
- [**tf-unifi**](./tf-unifi) – UniFi controller automation (networks, SSIDs, switches).  
- [**tf-dns-core**](./tf-dns-core) – DNS zones/records (`app.dev.deevnet.net` style).  
- [**tf-minio-backend**](./tf-minio-backend) – S3-compatible Terraform state backend (writes keys to Vault).  
- [**tf-vault-core**](./tf-vault-core) – Bootstraps Vault (auth, policies, KV, Transit).  
- [**tf-vault-pki**](./tf-vault-pki) – PKI engine for short-lived TLS certs across services.  

### Image Factory
- [**packer-pi-image-factory**](./packer-pi-image-factory) – Reproducible Pi/Linux images with baseline roles baked in.  

### Samples / Docs
- [**infra-sample**](./infra-sample) – Demonstrates end-to-end usage of modules and collections with dummy values.  
- [**infra-ops**](./infra-ops) – Shared docs, runbooks, helper scripts.  

---

## 🔒 Private Repositories

- `infra-dvnt` – Defines home lab stack (UniFi, Proxmox cluster, Windows/NAS).  
- `infra-dvntm` – Defines mobile lab stack (Proxmox pair, OPNsense, Pi cluster).  

Both use Vault for secrets and MinIO for Terraform state.  

---

## 🧭 Vision

This ecosystem is meant to:
- Provide reproducible, declarative infrastructure for both dvnt and dvntm labs.  
- Demonstrate patterns (Terraform + Ansible + Packer + Vault) others can reuse.  
- Serve as a playground for experimenting with secure, automated, cloud-like workflows at home.  

