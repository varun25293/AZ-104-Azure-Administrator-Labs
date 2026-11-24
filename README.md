\# Microsoft Azure Administrator (AZ-104) — Hands-On Enterprise Lab Portfolio



Complete end-to-end Azure infrastructure implementation covering all 5 official \*\*AZ-104\*\* exam domains, built with production governance guardrails, zero-trust network segmentation, automated scaling, and disaster recovery controls.



\---



\## Architecture \& Implementation Summary



\### Domain 1: Manage Azure Identities and Governance (20–25%)

\* \*\*Azure Policy \& Resource Locks (`01-policy-and-delete-lock.png`):\*\* Enforced mandatory `Environment` tag governance at the Resource Group scope and applied `CanNotDelete` locks on critical infrastructure.

\* \*\*Custom RBAC Role Definition (`02-custom-rbac-role-json.png`):\*\* Authored and deployed a least-privilege JSON custom RBAC role scoped to subscription resources.

\* \*\*Management Groups Hierarchy (`03-management-groups-hierarchy.png`):\*\* Structured enterprise management group hierarchy (`Production` / `Development`) for inherited policy and billing governance.

\* \*\*Cost Management \& Budget Alerts (`04-cost-budget-alert.png`):\*\* Configured proactive forecasted and actual spend threshold alerts (`50%`, `80%`, `100%`) to enforce strict FinOps discipline.



\### Domain 2: Implement and Manage Storage (15–20%)

\* \*\*Shared Access Signatures \& Stored Access Policies (`01-sas-stored-access-policy.png`):\*\* Implemented revocable container-level Stored Access Policies paired with time-bound, HTTPS-only SAS tokens.

\* \*\*Blob Lifecycle Management (`02-lifecycle-management-rule.png`):\*\* Automated data tiering (`Hot` → `Cool` → `Archive` / `Delete`) based on last-modified age thresholds to optimize storage costs.

\* \*\*Azure Files SMB Integration (`03-azure-files-smb-connect.png`):\*\* Provisioned an enterprise SMB file share and mounted it over port `445` (`Test-NetConnection` verified) as a persistent network drive.

\* \*\*Blob Soft Delete \& Point-in-Time Recovery (`04-soft-delete-restore.png`):\*\* Validated accidental deletion recovery by restoring soft-deleted blobs within the retention window.



\### Domain 3: Deploy and Manage Azure Compute Resources (20–25%)

\* \*\*Zone-Pinned Virtual Machine Deployment (`01-vm-availability-zone.png`):\*\* Deployed an Availability Zone-pinned VM (`Central India`, Zone 1) with static private networking and hardened NSG rules.

\* \*\*Custom Script Extension Automation (`02-custom-script-iis-live.png`):\*\* Automated post-deployment web server provisioning (`IIS`) and custom HTML payload injection without manual RDP intervention.

\* \*\*VM Scale Sets (VMSS) \& Custom Autoscale (`03-vmss-autoscale-rules.png`, `04-vmss-instances.png`):\*\* Deployed a Flexible orchestration VMSS configured with metric-driven CPU scale-out (`> 80%`) and scale-in (`< 20%`) rules across `1–3` instances.

\* \*\*App Service \& Zero-Downtime Deployment Slots (`05-appservice-deployment-slots.png`):\*\* Configured a `staging` deployment slot on a Standard App Service Plan and executed zero-downtime VIP swaps with `production`.



\### Domain 4: Implement and Manage Virtual Networking (15–20%)

\* \*\*Hub-and-Spoke VNet Peering (`01-vnet-peering-connected.png`):\*\* Connected non-overlapping Hub (`10.10.0.0/16`) and Spoke (`10.20.0.0/16`) virtual networks with bidirectional `Fully Synchronized` peering over Azure's private backbone.

\* \*\*Network Security Group (NSG) Micro-Segmentation (`02-nsg-inbound-rules.png`):\*\* Restricted Spoke subnet ingress to HTTPS (`TCP/443`) exclusively from the Hub management CIDR (`10.10.1.0/24`) at Priority `100`.



\### Domain 5: Monitor and Maintain Azure Resources (10–15%)

\* \*\*Azure Monitor Metric Alerts \& Action Groups (`01-monitor-cpu-alert-rule.png`):\*\* Built a real-time `Percentage CPU > 80%` metric alert rule integrated with an email-enabled Action Group (`ag-az104-admin`).

\* \*\*Recovery Services Vault \& VM Backup (`02-vm-backup-protected-item.png`):\*\* Configured automated daily VM protection (`EnhancedPolicy`) in a Recovery Services Vault (`rsv-az104-centralindia`) with soft-delete retention.

