<a name="readme-top"></a>

# Project FasHomeLab: A Living DevOps and Platform Engineering Portfolio

[![LinkedIn][linkedin-shield]][linkedin-url]
[![Project Status][status-shield]][status-url]

<div align="center">
  <h3>Automated Homelab for Hands-On DevOps Practice</h3>
  <p>
    Welcome to FasHomeLab. Inspired by the complex, automated systems of the <em>Horizon</em> game series, this project is where my passion for gaming and technology comes together. I named the lab after "FAS" (Faro Automated Solutions) from the game, creating a place where I practice building my own resilient, code-driven systems.
    <br><br>
    What started with a few Raspberry Pis has become a fully automated setup blending on-premise hardware with cloud integration. Built with <strong>Terraform</strong>, <strong>Ansible</strong>, <strong>Kubernetes</strong>, and <strong>GitOps</strong>, it's a living showcase of my real-world engineering skills.
    <br />
    <a href="#overall-architecture"><strong>View Architecture »</strong></a>
    · <a href="https://github.com/fashomelab/corneb/issues">Report Bug</a>
    · <a href="https://github.com/fashomelab/corneb/issues">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#-about-the-project">About The Project</a></li>
    <li><a href="#️-overall-architecture">Overall Architecture</a></li>
    <li><a href="#️-tech-stack">Tech Stack</a></li>
    <li><a href="#-technical-deep-dive">Technical Deep Dive</a></li>
    <li><a href="#-devops-principles--skills-demonstrated">DevOps Principles & Skills Demonstrated</a></li>
    <li><a href="#️-repository-structure">Repository Structure</a></li>
    <li><a href="#️-roadmap">Roadmap</a></li>
    <li><a href="#-contact">Contact</a></li>
    <li><a href="#-acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## 🚀 About The Project

This project is the result of a long-standing passion for building automated systems, inspired by the complex worlds in games like *Horizon*. What began as a small cluster of Raspberry Pis for hands-on learning has evolved into the production-grade platform you see today.

My focus has been on automating everything from server builds to application deployments, allowing me to practice building the kind of resilient and secure infrastructure seen in professional environments.

**Key Goals:**
- Showcase a comprehensive skillset in infrastructure, cloud, and automation.
- Host resilient services for my own learning and experimentation.
- Automate everything possible via code for true repeatability.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🗺️ Overall Architecture

A hybrid setup: on-premise Proxmox cluster for core workloads, Raspberry Pi fleet for always-on services, and Azure for state/security. Click for full view.

<div align="center">
  <a href="images/homelab-architecture.png">
    <img src="images/homelab-architecture.png" alt="Homelab Architecture Diagram" width="800">
  </a>
  <p><em>Homelab Architecture Diagram.</em></p>
</div>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🛠️ Tech Stack

<p align="center">
  <strong>Virtualization & Networking:</strong><br>
  <img src="https://img.shields.io/badge/Proxmox-E52F2F?style=for-the-badge&logo=proxmox&logoColor=white" alt="Proxmox"/>
  <img src="https://img.shields.io/badge/pfSense-212121?style=for-the-badge&logo=pfsense&logoColor=white" alt="pfSense"/>
  <img src="https://img.shields.io/badge/TrueNAS-0095D5?style=for-the-badge&logo=truenas&logoColor=white" alt="TrueNAS"/>
  <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu"/>
  <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx"/>
</p>
<p align="center">
  <strong>Containerization & Orchestration:</strong><br>
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/ArgoCD-EF7422?style=for-the-badge&logo=argocd&logoColor=white" alt="ArgoCD"/>
  <img src="https://img.shields.io/badge/Flux-4695CF?style=for-the-badge&logo=flux&logoColor=white" alt="FluxCD"/>
  <img src="https://img.shields.io/badge/Cilium-0077B5?style=for-the-badge&logo=cilium&logoColor=white" alt="Cilium"/>
  <img src="https://img.shields.io/badge/Longhorn-0077B5?style=for-the-badge&logo=longhorn&logoColor=white" alt="Longhorn"/>
</p>
<p align="center">
  <strong>Automation, IaC & CI/CD:</strong><br>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform"/>
  <img src="https://img.shields.io/badge/Ansible-EE0000?style=for-the-badge&logo=ansible&logoColor=white" alt="Ansible"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" alt="GitHub Actions"/>
  <img src="https://img.shields.io/badge/Azure_DevOps-0078D7?style=for-the-badge&logo=azuredevops&logoColor=white" alt="Azure DevOps"/>
  <img src="https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white" alt="Git"/>
</p>
<p align="center">
  <strong>Cloud, Security & Observability:</strong><br>
  <img src="https://img.shields.io/badge/Microsoft_Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" alt="Azure"/>
  <img src="https://img.shields.io/badge/HashiCorp_Vault-FFEC6E?style=for-the-badge&logo=hashicorp&logoColor=black" alt="HashiCorp Vault"/>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white" alt="Prometheus"/>
  <img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white" alt="Grafana"/>
</p>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🔍 Technical Deep Dive

<details>
  <summary><strong>Virtualization: 3-Node Proxmox HA Cluster</strong></summary>
  <br>
  The foundation of the on-premise lab is a 3-node Proxmox cluster, providing a resilient and flexible platform for all virtualized workloads.

  <ul>
    <li><strong>Clustering & High Availability:</strong> A 3-node setup was chosen to learn and implement enterprise-grade resilience. If one host fails, critical VMs can be automatically migrated to another node.</li>
    <li><strong>Network Teaming (LAGs):</strong> Link Aggregation is configured to the managed switch, preventing network bottlenecks and providing redundancy for the entire cluster.</li>
    <li><strong>Dedicated Workloads:</strong> A key design choice was to isolate workloads onto specific nodes for stability and performance. For example, <code>proxmox2</code> is dedicated to the virtualized <strong>pfSense router</strong> to protect core network functions, while <code>proxmox3</code> is tailored for storage-heavy services like <strong>TrueNAS Scale</strong>.</li>
  </ul>
</details>

<details>
  <summary><strong>Networking: pfSense, VLANs & Site-to-Site VPN</strong></summary>
  <br>
  A virtualized pfSense router acts as the brain of the network, managing security, routing, and traffic segmentation.

  <ul>
    <li><strong>Security-First Design:</strong> Virtualizing the firewall allows for easy snapshots, backups, and quick recovery. <strong>Snort</strong> is used for active intrusion detection, and the entire network is segmented into five <strong>VLANs</strong> to prevent lateral movement. For example, untrusted IoT devices are on a separate network and cannot access management interfaces.</li>
    <li><strong>VPN Gateway:</strong> The firewall functions as a central VPN gateway, providing two key capabilities: secure <strong>remote access</strong> into the homelab (as a VPN server), and a persistent <strong>site-to-site (S2S) tunnel</strong> to Microsoft Azure, securely bridging my on-premise and cloud environments.</li>
    <li><strong>Core Services:</strong> All essential network services (DHCP, DNS, firewall rules) are centralized on pfSense for simplified management.</li>
  </ul>
</details>

<details>
  <summary><strong>Kubernetes: Multi-Cluster GitOps Environment (k3s)</strong></summary>
  <br>
  The heart of my service deployment strategy is a multi-cluster Kubernetes environment. This setup mirrors enterprise best practices by separating management, production, and development workloads for enhanced security and stability. All clusters are managed declaratively using GitOps principles.

  <ol>
    <li><strong><code>cauldron-factory</code> (Management Cluster):</strong> This cluster follows the "management cluster" pattern, providing a central point of control. Managed by <strong>FluxCD</strong>, it hosts <strong>Rancher</strong> for UI-based management, along with core services like Traefik and Cert-Manager.</li>
    <li><strong><code>horizon-mountain</code> (Production Cluster):</strong> This cluster is dedicated to running primary, user-facing applications for the internal network. Managed by <strong>ArgoCD</strong>, it uses <strong>Cilium with BGP</strong> for advanced eBPF networking and includes a production-grade stack with <strong>HashiCorp Vault (HA)</strong> and <strong>Longhorn</strong> for storage. Access is strictly internal, protected from the public internet.</li>
    <li><strong><code>zero-dawn</code> (Dev/Test & CI Cluster):</strong> This cluster acts as a sandbox and hosts CI/CD infrastructure, including <strong>self-hosted GitHub Actions runners</strong>. This isolates resource-intensive build jobs from the production environment, ensuring performance and security.</li>
  </ol>

  <div align="center">
    <img src="images/kubernetes-clusters.png" alt="Multi-Cluster Kubernetes Setup with GitOps Management" width="600">
    <p><em>Multi-Cluster Kubernetes Setup with GitOps Management.</em></p>
  </div>
</details>

<details>
  <summary><strong>Physical Infrastructure: High-Availability Raspberry Pi Fleet</strong></summary>
  <br>
  To ensure critical services are always online without the power consumption of the main server cluster, a dedicated fleet of low-power Raspberry Pis runs 24/7. This is a deliberate design choice focused on energy efficiency and resilience.

  <ul>
    <li><strong><code>ravager</code> & <code>apollo</code> (HA DNS):</strong> DNS is the most critical service in the lab; if it's down, nothing works. This is a redundant <strong>Pi-hole</strong> setup in an active/passive cluster using <strong>Keepalived</strong> to manage a virtual IP for seamless failover.</li>
    <li><strong><code>thunderjaw</code> (External Monitoring):</strong> To provide a true external viewpoint, this Pi runs <strong>Uptime Kuma</strong>. It monitors all infrastructure from outside the main cluster, ensuring I get alerts even if the primary network or hosts are down.</li>
    <li><strong><code>sawtooth</code> (Isolated I/O Workloads):</strong> This node is dedicated to a high-volume data ingestion workload, keeping this high-churn activity separate from the main storage arrays to protect their performance.</li>
    <li><strong><code>stormbird</code> (Tiered Storage & Central Monitoring):</strong> Runs <strong>OpenMediaVault</strong> as a fast staging area for data, which is then synced nightly to the main TrueNAS VM. It also hosts the central <strong>Prometheus</strong> & <strong>Grafana</strong> "single pane of glass" for the entire lab.</li>
  </ul>

  <div align="center">
    <img src="images/uptime-kuma-monitoring.png" alt="Uptime Kuma Monitoring for thunderjaw" width="600">
    <p><em>Uptime Kuma Monitoring for thunderjaw.</em></p>
  </div>

  <div align="center">
    <img src="images/cluster-usage-grafana-monitoring.png" alt="Cluster Usage Monitoring with Grafana on stormbird" width="600">
    <p><em>Cluster Usage Monitoring with Grafana on stormbird.</em></p>
  </div>
</details>

<details>
  <summary><strong>Automation: IaC & Hybrid Cloud Strategy</strong></summary>
  <br>
  Automation is the central principle of this lab, with a clear separation of concerns between provisioning (Terraform) and configuration (Ansible).

  <ul>
    <li><strong>Terraform (IaC):</strong> Manages the entire lifecycle of all Proxmox VMs, with state stored securely in <strong>Azure Blob Storage</strong> to enable CI/CD integration.</li>
    <li><strong>Ansible (Configuration Management):</strong> Configures new VMs after provisioning, handling security hardening and application setup. Playbooks are triggered automatically by an <strong>Azure DevOps</strong> pipeline.</li>
    <li><strong>Azure Cloud Services:</strong> An <strong>Entra ID App Registration</strong> provides secure, passwordless authentication for all automated services (Terraform, ADO) interacting with the Azure subscription.</li>
  </ul>
</details>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 💡 DevOps Principles & Skills Demonstrated

This project puts the following key DevOps principles and engineering skills into practice:
* **Infrastructure as Code (IaC):** Using **Terraform** to declaratively manage all virtual infrastructure.
* **GitOps:** Using **ArgoCD** and **FluxCD** to manage Kubernetes cluster state and application deployments directly from Git.
* **Configuration Management:** Using **Ansible** for repeatable and consistent server configuration and software deployment.
* **CI/CD Automation:**
    * Implementing validation workflows in **GitHub Actions**.
    * Using **Azure DevOps Pipelines** for infrastructure update automation.
    * Building and managing **self-hosted CI runners** on Kubernetes.
* **Containerization & Orchestration:** Deep expertise in **Docker** and **Kubernetes (k3s)**, including advanced networking (**Cilium**), storage (**Longhorn**), and security (**Sealed Secrets**, **Vault**).
* **Hybrid-Cloud Management:** Seamlessly managing resources across on-premise (**Proxmox**, Raspberry Pis) and cloud platforms (**Azure**).
* **Observability:** Building a comprehensive, multi-layered monitoring stack with **Prometheus**, **Grafana**, and **Uptime Kuma**.
* **Network Security:** Implementing network segmentation with **VLANs**, enterprise-grade firewalls with **pfSense/Snort**, and robust secrets management.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🏗️ Repository Structure

Central hub for the project. Private repos will go public soon:

- **/terraform:** Proxmox/Azure IaC.
- **/ansible:** Playbooks/roles.
- **/kubernetes:** Manifests, Helm, GitOps configs.
- **homelab-architecture.png:** Main diagram.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## 🗺️ Roadmap

- [ ] **Unified Terraform/Ansible workflow:** Integrate IaC and configuration management for seamless, end-to-end server provisioning.
- [ ] **CI for Ansible & Kubernetes:** Expand the CI/CD pipeline to include linting and validation for Ansible roles and Kubernetes manifests.
- [ ] **Migrate all secrets to HashiCorp Vault:** Centralize all secrets (including Ansible Vault) into a single, secure source of truth.
- [ ] **Implement a Service Mesh (Istio/Linkerd):** Enhance security and observability within the Kubernetes clusters by adding a service mesh for mTLS and traffic management.

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