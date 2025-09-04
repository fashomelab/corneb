# Project FasHomeLab: A Living DevOps and Platform Engineering Portfolio

[![LinkedIn][linkedin-shield]][linkedin-url]
[![Project Status][status-shield]][status-url]

<div align="center">
  <h3>Automated Homelab for Hands-On DevOps Practice</h3>
  <p>
    Welcome to FasHomeLab – my personal, fully automated setup blending on-premise hardware with cloud integration. Built with Terraform, Ansible, Kubernetes, and GitOps, it's a showcase of resilient infrastructure engineering. Explore the architecture, dive into tech stacks, and see real-world skills in action.
    <br />
    <a href="#overall-architecture"><strong>View Architecture »</strong></a>
    · <a href="https://github.com/fashomelab/corneb/issues">Report Bug</a>
    · <a href="https://github.com/fashomelab/corneb/issues">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#overall-architecture">Overall Architecture</a></li>
    <li><a href="#tech-stack">Tech Stack</a></li>
    <li><a href="#technical-deep-dive">Technical Deep Dive</a></li>
    <li><a href="#devops-principles--skills-demonstrated">DevOps Principles & Skills</a></li>
    <li><a href="#repository-structure">Repository Structure</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## 🚀 About The Project

This homelab evolved from tinkering with Raspberry Pis into a production-grade setup for practicing DevOps. It's 100% automated – from VM provisioning to app deployments – demonstrating scalable, secure systems.

**Key Goals:**
- Showcase infrastructure, cloud, and automation expertise.
- Host resilient services for learning and experimentation.
- Automate everything via code for repeatability.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🗺️ Overall Architecture

A hybrid setup: on-premise Proxmox cluster for core workloads, Raspberry Pi fleet for always-on services, and Azure for state/security. Click for full view.

<div align="center">
  <a href="homelab-architecture.png">
    <img src="homelab-architecture.png" alt="Homelab Architecture Diagram" width="800">
  </a>
</div>

*(Note: If the image isn't loading, check for a filename typo – it might be "homelab-architecture.png" with an 'e'.)*

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🛠️ Tech Stack

| Category | Tools | Purpose |
|----------|-------|---------|
| **Virtualization** | Proxmox VE (3-node cluster) | High-availability VMs with LAG networking. |
| **Networking** | pfSense, VLANs, Snort | Secure routing, segmentation, IDS/IPS. |
| **Orchestration** | Kubernetes (k3s), ArgoCD/FluxCD, Cilium | GitOps-managed clusters with eBPF networking. |
| **Storage** | TrueNAS Scale, Longhorn, OpenMediaVault | Resilient, tiered storage. |
| **Automation** | Terraform, Ansible | IaC for provisioning; config management. |
| **Monitoring** | Prometheus, Grafana, Uptime Kuma | Centralized metrics and alerting. |
| **Cloud** | Azure (Blob, DevOps, Entra ID) | State storage, pipelines, auth. |
| **Security** | HashiCorp Vault, Sealed Secrets | HA secrets management. |
| **Hardware** | Raspberry Pi Fleet | Low-power, redundant services. |

*(Suggestion: Add skill icons/badges here from https://github.com/tandpfun/skill-icons for visual pop – e.g., ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white).)*

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🔍 Technical Deep Dive

<details>
  <summary>Virtualization: Proxmox VE Cluster</summary>
  <ul>
    <li>3-node HA setup for VM migration on failure.</li>
    <li>Dedicated nodes: pfSense on proxmox2, storage on proxmox3 with HDD/SSD passthrough.</li>
  </ul>
  *(Add a diagram: Proxmox cluster layout showing nodes and workloads.)*
</details>

<details>
  <summary>Networking: pfSense & VLANs</summary>
  <ul>
    <li>Virtualized firewall with Snort IDS and 5 VLANs for isolation (e.g., IoT segregated).</li>
    <li>VPN server for remote access; S2S tunnel to Azure.</li>
    <li>Central DHCP/DNS/firewall management.</li>
  </ul>
  *(Add a diagram: VLAN segmentation and traffic flow.)*
</details>

<details>
  <summary>Kubernetes (k3s) Clusters</summary>
  <ol>
    <li><strong>cauldron-factory (Management):</strong> FluxCD-managed; hosts Rancher, Traefik, Cert-Manager.</li>
    <li><strong>horizon-mountain (Production):</strong> ArgoCD, Cilium BGP, Vault HA, Longhorn, Prometheus/Grafana. Internal-only access via Nginx/Traefik.</li>
    <li><strong>zero-dawn (Dev/Test & CI):</strong> ArgoCD-managed; isolates CI/CD (GitHub runners) for security/performance.</li>
  </ol>
  *(Add a diagram: Multi-cluster setup with GitOps flows. Include screenshots of Rancher UI or Grafana dashboards.)*
</details>

<details>
  <summary>Physical Infrastructure: Raspberry Pi Fleet</summary>
  <ul>
    <li><strong>ravager & apollo:</strong> HA Pi-hole DNS with Keepalived VIP and Nebulasync sync.</li>
    <li><strong>thunderjaw:</strong> External Uptime Kuma monitoring.</li>
    <li><strong>sawtooth:</strong> Containerized download services for high I/O isolation.</li>
    <li><strong>stormbird:</strong> OMV staging NAS; central Prometheus/Grafana with Node Exporters.</li>
  </ul>
  *(Add a photo/diagram: Pi fleet layout and connections.)*
</details>

<details>
  <summary>Automation: IaC & Configuration Management</summary>
  <ul>
    <li>Terraform: VM lifecycle, Azure Blob state.</li>
    <li>Ansible: Post-provision config (hardening, apps); Azure DevOps-triggered.</li>
    <li>Secrets: Ansible Vault (migrating to Vault).</li>
  </ul>
  *(Add a flowchart: Terraform → Ansible workflow.)*
</details>

<details>
  <summary>Cloud Integration: Azure</summary>
  <ul>
    <li>Entra ID App Registration for secure auth in automations.</li>
  </ul>
</details>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 💡 DevOps Principles & Skills Demonstrated

- **IaC & GitOps:** Terraform for infra; ArgoCD/FluxCD for K8s.
- **CI/CD:** GitHub Actions linting; Azure Pipelines; self-hosted runners.
- **Containerization:** Docker/K8s with Cilium, Longhorn, Vault.
- **Hybrid Management:** On-prem (Proxmox/Pis) + Azure.
- **Observability:** Prometheus/Grafana/Uptime Kuma.
- **Networking/Security:** VLANs, pfSense/Snort, Vault/Sealed Secrets.
- **Version Control:** Git as single source of truth.

*(Suggestion: Add progress badges or icons for each skill.)*

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🏗️ Repository Structure

Central hub for the project. Private repos will go public soon:

- **/terraform:** Proxmox/Azure IaC.
- **/ansible:** Playbooks/roles.
- **/kubernetes:** Manifests, Helm, GitOps configs.
- **homelab-architecture.png:** Main diagram.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🗺️ Roadmap

- [ ] Unified Terraform/Ansible workflow.
- [ ] CI for Ansible/Terraform (lint/validate).
- [ ] Migrate secrets to HashiCorp Vault.
- [ ] CD pipelines for K8s apps.
- [ ] Add service mesh (Istio/Linkerd).

See issues for more.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 📞 Contact

Corne Blignaut - [LinkedIn](https://www.linkedin.com/in/corne-blignaut-10b618a4) - cblignaut989@hotmail.com

Project: [https://github.com/fashomelab/corneb](https://github.com/fashomelab/corneb)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🙏 Acknowledgments

- [Best-README-Template](https://github.com/othneildrew/Best-README-Template)
- /r/homelab and /r/selfhosted communities
- Docs for Proxmox, Terraform, K8s, Ansible, etc.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/corne-blignaut-10b618a4
[status-shield]: https://img.shields.io/badge/status-active-success.svg?style=for-the-badge
[status-url]: https://github.com/fashomelab/corneb