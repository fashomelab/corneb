# ApexVirtual Platform

Production-grade platform engineering showcase demonstrating infrastructure automation, configuration management, and security patterns across hybrid-cloud environments.

<div align="center">
  <img src="images/architecture-pipeline-flow.png" alt="ApexVirtual Infrastructure Pipeline" width="800">
  <p><em>Complete infrastructure-to-application pipeline showing Terraform → Ansible → ArgoCD integration</em></p>
</div>

## 🚀 What I Built

### Infrastructure Provisioning ([apexvirtual-terraform](https://github.com/fashomelab/apexvirtual-terraform))
- 29 VMs across hybrid cloud (Proxmox + Azure)
- Multi-environment management (on-prem, Azure dev, Azure prod)
- Data-driven infrastructure from YAML configuration
- Secretless CI/CD with Vault OIDC authentication

### Configuration Management ([apexvirtual-ansible](https://github.com/fashomelab/apexvirtual-ansible))
- Tag-based dynamic inventory from Terraform
- Automated OS hardening and security baseline
- Role-based architecture with 15+ reusable components
- Monitoring federation across infrastructure

### Application Deployment ([apexvirtual-gitops](https://github.com/fashomelab/apexvirtual-gitops))
- GitOps patterns with ArgoCD
- Multi-cluster Kubernetes management
- Sealed secrets for encrypted credentials

## 🏆 Key Technical Achievements
- **90% Faster Provisioning**: Reduced VM provisioning from 90 minutes to under 10 minutes through automated Terraform and Ansible pipeline.  
- **100% Secretless CI/CD**: Eliminated all static credentials using GitHub OIDC and HashiCorp Vault integration.  
- **Multi-Environment Consistency**: Single codebase manages dev, prod, and on-prem environments with zero configuration drift.  
- **Hybrid Cloud Architecture**: Seamless resource management across Proxmox (on-premise) and Azure (cloud) platforms.  

## 🏗️ Architecture

The platform follows a three-stage pipeline: infrastructure provisioning, configuration management, and application deployment.

### Infrastructure Layer (Terraform)
- Provisions VMs from YAML-defined specifications
- Applies tags for automated configuration targeting
- Manages network segmentation (VLANs 283, 284, 285)
- Stores state in Azure Blob Storage with locking

### Configuration Layer (Ansible)
- Discovers infrastructure via Proxmox dynamic inventory
- Groups hosts by Terraform-applied tags
- Deploys monitoring, security, and application services
- Retrieves all credentials from Vault at runtime

### Application Layer (GitOps)
- Declarative Kubernetes manifests in Git
- ArgoCD syncs cluster state automatically
- Sealed secrets for credential management
- Multi-cluster deployment patterns

## 🛠️ Technology Stack
- **Infrastructure**: Terraform, Proxmox VE, Microsoft Azure  
- **Configuration**: Ansible, HashiCorp Vault, Docker  
- **Orchestration**: Kubernetes (k3s), ArgoCD, FluxCD  
- **Observability**: Prometheus, Grafana, Node Exporter  
- **CI/CD**: GitHub Actions, Azure DevOps  

## 📦 Repositories
- [apexvirtual-terraform](https://github.com/fashomelab/apexvirtual-terraform)  
  Infrastructure as Code for hybrid-cloud platform. Demonstrates modular Terraform design, remote state management, OIDC authentication, and multi-environment workflows.  

- [apexvirtual-ansible](https://github.com/fashomelab/apexvirtual-ansible)  
  Configuration management with dynamic inventory. Demonstrates role-based architecture, Vault integration, data-driven configuration, and automated security hardening.  

- [apexvirtual-gitops](https://github.com/fashomelab/apexvirtual-gitops)
  Production GitOps patterns with ArgoCD ApplicationSets, multi-cluster Kubernetes management, and automated application deployment across environments.  

## 💡 Skills Demonstrated
- **Infrastructure as Code**: Advanced Terraform patterns with modules, remote state, multi-environment management  
- **Configuration Management**: Ansible with dynamic inventory, tag-based targeting, Vault integration  
- **Security Engineering**: Zero-trust networking, OIDC authentication, secrets management, automated hardening  
- **Cloud Architecture**: Hybrid cloud design, network segmentation, high-availability patterns  
- **DevOps Practices**: GitOps workflows, automated testing, CI/CD pipelines, infrastructure monitoring  

## 📞 Contact
**Corne Blignaut**  
[LinkedIn](https://www.linkedin.com/in/corne-blignaut) | cblignaut989@hotmail.com  
Available for Platform Engineering roles - Remote/Hybrid (Portsmouth UK area)  

---
Platform engineering showcase designed to demonstrate production-ready automation patterns through practical implementation of enterprise infrastructure practices.
