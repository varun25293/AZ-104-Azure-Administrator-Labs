# Microsoft Azure Administrator (AZ-104) — Hands-On Enterprise Lab Portfolio

Complete end-to-end Azure infrastructure implementation covering all 5 official **AZ-104** exam domains, built with production governance guardrails, zero-trust network segmentation, automated scaling, and disaster recovery controls.

---

## Domain 1: Manage Azure Identities and Governance (20–25%)

### 1.1 Azure Policy & Resource Locks
Enforced mandatory `Environment` tag governance at the Resource Group scope and applied `CanNotDelete` locks on critical infrastructure.
![Azure Policy and Delete Lock](Domain1-Governance/01-policy-and-delete-lock.png)

### 1.2 Custom RBAC Role Definition
Authored and deployed a least-privilege JSON custom RBAC role scoped to subscription resources.
![Custom RBAC Role JSON](Domain1-Governance/02-custom-rbac-role-json.png)

### 1.3 Management Groups Hierarchy
Structured enterprise management group hierarchy (`Production` / `Development`) for inherited policy and billing governance.
![Management Groups Hierarchy](Domain1-Governance/03-management-groups-hierarchy.png)

### 1.4 Cost Management & Budget Alerts
Configured proactive forecasted and actual spend threshold alerts (`50%`, `80%`, `100%`) to enforce strict FinOps discipline.
![Cost Management Budget Alert](Domain1-Governance/04-cost-budget-alert.png)

---

## Domain 2: Implement and Manage Storage (15–20%)

### 2.1 Shared Access Signatures & Stored Access Policies
Implemented revocable container-level Stored Access Policies paired with time-bound, HTTPS-only SAS tokens.
![SAS and Stored Access Policy](Domain2-Storage/01-sas-stored-access-policy.png)

### 2.2 Blob Lifecycle Management
Automated data tiering (`Hot` → `Cool` → `Archive` / `Delete`) based on last-modified age thresholds to optimize storage costs.
![Blob Lifecycle Management Rule](Domain2-Storage/02-lifecycle-management-rule.png)

### 2.3 Azure Files SMB Integration
Provisioned an enterprise SMB file share and mounted it over port `445` (`Test-NetConnection` verified) as a persistent network drive.
![Azure Files SMB Mount](Domain2-Storage/03-azure-files-smb-connect.png)

### 2.4 Blob Soft Delete & Point-in-Time Recovery
Validated accidental deletion recovery by restoring soft-deleted blobs within the retention window.
![Blob Soft Delete Restore](Domain2-Storage/04-soft-delete-restore.png)

---

## Domain 3: Deploy and Manage Azure Compute Resources (20–25%)

### 3.1 Zone-Pinned Virtual Machine Deployment
Deployed an Availability Zone-pinned VM (`Central India`, Zone 1) with static private networking and hardened NSG rules.
![VM Availability Zone](Domain3-Compute/01-vm-availability-zone.png)

### 3.2 Custom Script Extension Automation
Automated post-deployment web server provisioning (`IIS`) and custom HTML payload injection without manual RDP intervention.
![Custom Script Extension IIS Live](Domain3-Compute/02-custom-script-iis-live.png)

### 3.3 VM Scale Sets (VMSS) & Custom Autoscale
Deployed a Flexible orchestration VMSS configured with metric-driven CPU scale-out (`> 80%`) and scale-in (`< 20%`) rules across `1–3` instances.
![VMSS Autoscale Rules](Domain3-Compute/03-vmss-autoscale-rules.png)
![VMSS Running Instances](Domain3-Compute/04-vmss-instances.png)

### 3.4 App Service & Zero-Downtime Deployment Slots
Configured a `staging` deployment slot on a Standard App Service Plan and executed zero-downtime VIP swaps with `production`.
![App Service Deployment Slots](Domain3-Compute/05-appservice-deployment-slots.png)

---

## Domain 4: Implement and Manage Virtual Networking (15–20%)

### 4.1 Hub-and-Spoke VNet Peering
Connected non-overlapping Hub (`10.10.0.0/16`) and Spoke (`10.20.0.0/16`) virtual networks with bidirectional `Fully Synchronized` peering over Azure's private backbone.
![VNet Peering Connected](Domain4-Networking/01-vnet-peering-connected.png)

### 4.2 Network Security Group (NSG) Micro-Segmentation
Restricted Spoke subnet ingress to HTTPS (`TCP/443`) exclusively from the Hub management CIDR (`10.10.1.0/24`) at Priority `100`.
![NSG Inbound Security Rules](Domain4-Networking/02-nsg-inbound-rules.png)

---

## Domain 5: Monitor and Maintain Azure Resources (10–15%)

### 5.1 Azure Monitor Metric Alerts & Action Groups
Built a real-time `Percentage CPU > 80%` metric alert rule integrated with an email-enabled Action Group (`ag-az104-admin`).
![Azure Monitor CPU Alert Rule](Domain5-Monitor/01-monitor-cpu-alert-rule.png)

### 5.2 Recovery Services Vault & VM Backup
Configured automated daily VM protection (`EnhancedPolicy`) in a Recovery Services Vault (`rsv-az104-centralindia`) with soft-delete retention.
![VM Backup Protected Item](Domain5-Monitor/02-vm-backup-protected-item.png)
