``markdown
🏗️ High Availability Web Infrastructure on Azure

Author: Maurrin Carter
GitHub: @maxmagnac (https://github.com/maxmagnac)
Platform: Microsoft Azure
Project Type: Hands-On Lab / Learning Project

📋 Project Overview

This project demonstrates hands-on cloud engineering skills through the full deployment of a high availability web infrastructure on Microsoft Azure. Every component - from virtual networking to load balancing, database connectivity, monitoring, and web application deployment - was built, configured, and validated manually.

This project serves as a portfolio piece showcasing real-world cloud architecture skills for a cloud engineering career.

Infrastructure Resource Group (screenshots/haweb_infr_rg.png)
Full infrastructure resource group showing all deployed Azure resources

🏛️ Architecture Summary

`
┌─────────────────────────────────────────┐
│ Microsoft Azure │
│ │
│ ┌──────────────────────────────────┐ │
│ │ Virtual Network │ │
│ │ │ │
│ │ ┌───────────┐ ┌───────────┐ │ │
│ │ │ vm-web-01 │ │ vm-web-02 │ │ │
│ │ └─────┬─────┘ └─────┬─────┘ │ │
│ │ │ │ │ │
│ │ ┌─────▼──────────────▼──────┐ │ │
│ │ │ Azure Load Balancer │ │ │
│ │ │ ha-web-lb │ │ │
│ │ └───────────────────────────┘ │ │
│ │ │ │
│ │ ┌───────────────────────────┐ │ │
│ │ │ Private Subnet │ │ │
│ │ │ ┌─────────┐ ┌─────────┐ │ │ │
│ │ │ │vm-db-01 │ │vm-db-02 │ │ │ │
│ │ │ │ MySQL │ │ MySQL │ │ │ │
│ │ │ └─────────┘ └─────────┘ │ │ │
│ │ │ NAT Gateway │ │ │
│ │ └───────────────────────────┘ │ │
│ └──────────────────────────────────┘ │
│ │
│ ┌──────────────────────────────────┐ │
│ │ Azure Monitor + Log Analytics │ │
│ └──────────────────────────────────┘ │
└─────────────────────────────────────────┘
`

Infrastructure Components

| Component | Resource Name | Details |
|-----------|--------------|---------|
| Virtual Network | ha-web-vnet | Segmented public/private subnets |
| Web Server 1 | vm-web-01 | Ubuntu 22.04 LTS - Apache/PHP |
| Web Server 2 | vm-web-02 | Ubuntu 22.04 LTS - Apache/PHP |
| Database Server 1 | vm-db-01 | Ubuntu 22.04 LTS - MySQL |
| Database Server 2 | vm-db-02 | Ubuntu 22.04 LTS - MySQL |
| Load Balancer | ha-web-lb | Public frontend - round-robin |
| NAT Gateway | ha-web-nat-gateway | Secure outbound for private subnet |
| Monitoring | ha-web-logs | Log Analytics + Azure Monitor alerts |

📁 Phase Breakdown

Phase 1 - Virtual Network Setup

Built the foundation of the entire infrastructure by creating a Virtual Network (VNet) in Azure. Configured segmented subnets to separate web traffic from database traffic, establishing network isolation and security from the start. Configured Network Security Groups (NSGs) for both public and private subnets.

Key skills demonstrated:
- Virtual Network creation and configuration
- Subnet segmentation for multi-tier architecture
- Network Security Group configuration

VNet Overview (screenshots/phase1/hawebvnet_overview.png)
Virtual Network overview showing VNet configuration

VNet Subnets (screenshots/phase1/hawebvnet_subnets_priv_pub.png)
VNet subnets showing public and private subnet setup

NSGs Overview (screenshots/phase1/hawebNSGs.png)
Network Security Groups overview

Public NSG Inbound Rules (screenshots/phase1/hawebNSGs_public-nsg_inbound_rules.png)
Public NSG inbound rules configuration

Public NSG Subnets (screenshots/phase1/haweb_public-nsg_subnets.png)
Public NSG subnet associations

Private NSG Inbound Rules (screenshots/phase1/haweb_private-nsg_inbound_rules.png)
Private NSG inbound rules configuration

Private NSG Subnets (screenshots/phase1/haweb_private-nsg_subnets.png)
Private NSG subnet associations

Phase 2 - Virtual Machine Deployment

Deployed two Ubuntu Server 22.04 LTS web server VMs (vm-web-01 and vm-web-02) and two database server VMs (vm-db-01 and vm-db-02). Configured each VM with appropriate network interfaces and placed them in their respective subnets. Installed and configured Nginx on both web servers.

Key skills demonstrated:
- Virtual Machine provisioning on Azure
- OS selection and VM sizing
- Multi-tier VM placement across subnets
- Web server installation and status verification

Both Web VMs (screenshots/phase2/haweb_vm1_and_vm2.png)
Overview of both web server VMs

VM Web 01 Settings 1 (screenshots/phase2/haweb_vm1_settings1.png)
vm-web-01 settings - Part 1

VM Web 01 Settings 2 (screenshots/phase2/haweb_vm1_settings2.png)
vm-web-01 settings - Part 2

VM Web 02 Settings 1 (screenshots/phase2/haweb_vm2_settings1.png)
vm-web-02 settings - Part 1

VM Web 02 Settings 2 (screenshots/phase2/haweb_vm2_settings2.png)
vm-web-02 settings - Part 2

VM DB 01 (screenshots/phase2/haweb_vm-db-01.png)
Database server vm-db-01 overview

VM DB 01 Settings 1 (screenshots/phase2/haweb_vm-db-01_settings1.png)
vm-db-01 settings - Part 1

VM DB 01 Settings 2 (screenshots/phase2/haweb_vm-db-01_settings2.png)
vm-db-01 settings - Part 2

VM DB 02 Settings 1 (screenshots/phase2/haweb_vm-db-02_settings1.png)
vm-db-02 settings - Part 1

VM DB 02 Settings 2 (screenshots/phase2/haweb_vm-db-02_settings2.png)
vm-db-02 settings - Part 2

Nginx Install VM Web 01 (screenshots/phase2/haweb_Nginx_install_output_vm-web-01.png)
Nginx installation output on vm-web-01

Nginx Install VM Web 02 (screenshots/phase2/haweb_Nginx_install_output_vm-web-02.png)
Nginx installation output on vm-web-02

Nginx Status VM Web 01 (screenshots/phase2/haweb_Nginx_status_vm-web-01.png)
Nginx service status running on vm-web-01

Nginx Status VM Web 02 (screenshots/phase2/haweb_Nginx_status_vm-web-02.png)
Nginx service status running on vm-web-02

Both VMs Overview (screenshots/phase2/haweb_Both_VMs_overview.png)
Both web VMs running and confirmed

Both VMs Responding (screenshots/phase2/haweb_Both_VMs_responding_test.png)
Both web VMs responding to connectivity test

Phase 3 - Load Balancer Configuration

Configured the Azure Load Balancer (ha-web-lb) with a frontend public IP, backend pool containing both web servers, health probes, and load balancing rules. Validated health probe responses from both VMs confirming active load balancer operation.

Key skills demonstrated:
- Azure Load Balancer provisioning
- Backend pool configuration
- Health probe setup and load balancing rules
- Load balancer validation and testing

LB Deploy Success (screenshots/phase3/haweb_lb_deploysuccess.png)
Load balancer deployment success confirmation

LB Overview (screenshots/phase3/haweb_lb_overview.png)
Load balancer overview and configuration

LB Settings 1 (screenshots/phase3/haweb_lb_settings1.png)
Load balancer settings - Part 1

LB Settings 2 (screenshots/phase3/haweb_lb_settings2.png)
Load balancer settings - Part 2

LB VM Health (screenshots/phase3/haweb_lb_vm_health.png)
Load balancer VM health probe status

LB VM Web 01 Success (screenshots/phase3/haweb_lb-vm-web-01-success.png)
Health probe success for vm-web-01

LB VM Web 02 Success (screenshots/phase3/haweb_lb-vm-web-02-success.png)
Health probe success for vm-web-02

That's exactly what we need! 🔥

Both private subnets checked and saved:
- private-subnet-1 (10.1.3.0/24) ✅
- private-subnet-2 (10.1.4.0/24) ✅

Here's the updated Phase 4 section of the README:

``markdown

Phase 4 - NAT Gateway Setup

Created and configured a NAT Gateway to provide secure outbound internet connectivity for the database subnet. This allows the database VMs to receive updates and patches without exposure to inbound internet traffic. Both private subnets were associated with the NAT Gateway to ensure full high availability coverage across the database tier.

Key skills demonstrated:
- NAT Gateway creation and subnet association
- Outbound connectivity design for private subnets
- Security-conscious network architecture
- High availability configuration across multiple private subnets

NAT Gateway Subnet Association (screenshots/phase4/haweb_natgateway_subnets_associated.png)
NAT Gateway associated with both private subnets - private-subnet-1 and private-subnet-2
``

That Phase 4 section now tells a complete story with real proof. 💪🏾

Ready to move on to uploading all your screenshots to GitHub? 🚀

Phase 5 - Database Deployment

Installed and configured MySQL on both vm-db-01 and vm-db-02. Created a dedicated application database (haweb_db) and a scoped database user (haweb_user) with access limited to the application database only. Validated database connectivity from both web servers.

Key skills demonstrated:
- MySQL installation and configuration on Linux
- Database and user creation with scoped permissions
- Private network database access configuration
- Cross-tier connectivity validation

MySQL Install Output (screenshots/phase5/haweb_mysql_install_output_vm-db-01.png)
MySQL installation output on vm-db-01

MySQL Status (screenshots/phase5/haweb_mysql_status_vm-db-01.png)
MySQL service status running on vm-db-01

MySQL Monitor VM Web 01 (screenshots/phase5/haweb_MySQL_monitor_prompt_from_vm-web-01.png)
MySQL connection prompt accessed from vm-web-01

MySQL Monitor VM Web 02 (screenshots/phase5/haweb_MySQL_monitor_prompt_from_vm-web-02.png)
MySQL connection prompt accessed from vm-web-02

DB Connectivity (screenshots/phase5/haweb-db-connectivity.png)
Database connectivity validation confirmation

DB 01 and DB 02 (screenshots/phase5/haweb_vm-db-01_and_db-02.png)
Both database VMs overview

Phase 6 - Monitoring and Alerts

Created a Log Analytics Workspace (ha-web-logs) and connected it to the infrastructure. Configured Azure Monitor with custom alert rules across all VMs. Validated alerts by triggering a CPU spike and confirming email delivery.

Key skills demonstrated:
- Log Analytics Workspace creation
- Azure Monitor configuration
- Custom alert rule setup per VM
- Alert validation through CPU spike testing

Log Analytics Workspace (screenshots/phase6/haweb-log-analytics-workspace.png)
Log Analytics Workspace creation and overview

Alert Overview (screenshots/phase6/haweb-lb-alert-overview.png)
Azure Monitor alert rules overview

VM Web 01 Alerts (screenshots/phase6/haweb-vm-web-01-alerts.png)
Alert rules configured for vm-web-01

VM Web 02 Alerts (screenshots/phase6/haweb-vm-web-02-alerts.png)
Alert rules configured for vm-web-02

VM DB 01 Alerts (screenshots/phase6/haweb-vm-db-01-alerts.png)
Alert rules configured for vm-db-01

CPU Spike (screenshots/phase6/haweb-cpu-spike.png)
CPU spike triggered for alert validation

Alert Email 1 (screenshots/phase6/haweb-alert-email_1.png)
Alert email notification received - Part 1

Alert Email 2 (screenshots/phase6/haweb-alert-email_2.png)
Alert email notification received - Part 2

Alert Email 3 (screenshots/phase6/haweb-alert-email_3.png)
Alert email notification received - Part 3

Phase 7 - Testing and Validation

Conducted end-to-end testing of the entire infrastructure. Validated localhost connectivity on both web servers, confirmed load balancer failover behavior, and verified full stack connectivity through the load balancer's public IP.

Key skills demonstrated:
- Infrastructure validation and troubleshooting
- Localhost and cross-tier connectivity testing
- Load balancer failover testing
- Full stack validation through public IP

VM Web 01 Localhost Success (screenshots/phase7/haweb_vm-web-01-localhost-success.png)
Localhost connectivity success on vm-web-01

VM Web 02 Localhost Success (screenshots/phase7/haweb_vm-web-02-localhost-success.png)
Localhost connectivity success on vm-web-02

Curl Localhost VM Web 01 (screenshots/phase7/haweb_curl_localhost_vm-web-01.png)
curl localhost output on vm-web-01

Curl Localhost VM Web 02 (screenshots/phase7/haweb_curl_localhost_vm-web-02.png)
curl localhost output on vm-web-02

LB Failover Test (screenshots/phase7/haweb-lb-failover-test.png)
Load balancer failover test result

LB Connectivity (screenshots/phase7/haweb-lb-connectivity.png)
Load balancer public IP connectivity confirmed

Browser Success (screenshots/phase7/haweb_browser_success.png)
Browser successfully serving app through load balancer

Phase 8 - Web Application Deployment

Deployed a PHP web application to both web servers connecting to the MySQL database using the private IP of vm-db-01. Validated the full stack by curling the load balancer's public IP and confirming round-robin traffic distribution between both web servers with live database connectivity on every request.

Key skills demonstrated:
- PHP application deployment on Apache
- Database connectivity configuration from the application layer
- End-to-end load balancer validation with live traffic
- Round-robin traffic distribution confirmation

VM Web 01 App (screenshots/phase8/haweb-vm-web-01-app_phs8.png)
curl output confirming PHP app and DB connection on vm-web-01

VM Web 02 App (screenshots/phase8/haweb-vm-web-02-app_phs8.png)
curl output confirming PHP app and DB connection on vm-web-02

LB Connectivity Phase 8 - 1 (screenshots/phase8/haweb-lb-connectivity_phs8_1.png)
Browser showing load balancer serving PHP app - vm-web-01

LB Connectivity Phase 8 - 2 (screenshots/phase8/haweb-lb-connectivity_phs8_2.png)
Browser showing load balancer serving PHP app - vm-web-02

LB Curl Phase 8 (screenshots/phase8/haweb-lb-curl_phs8.png)
Terminal showing round-robin curl output switching between both servers

✅ Validation Results

| Test | Result |
|------|--------|
| VNet and subnet configuration | ✅ SUCCESS |
| VM deployment - all four VMs | ✅ SUCCESS |
| Nginx running on both web servers | ✅ SUCCESS |
| Load balancer deployment and health probes | ✅ SUCCESS |
| MySQL installation and configuration | ✅ SUCCESS |
| Database connectivity from web tier | ✅ SUCCESS |
| Azure Monitor alerts and email notifications | ✅ SUCCESS |
| Full stack PHP app with DB connection | ✅ SUCCESS |
| Load balancer round-robin distribution | ✅ SUCCESS |

🛠️ Tools & Technologies

Azure (https://img.shields.io/badge/Microsoft%20Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
Ubuntu (https://img.shields.io/badge/Ubuntu%2022.04-E95420?style=flat-square&logo=ubuntu&logoColor=white)
Apache (https://img.shields.io/badge/Apache-D22128?style=flat-square&logo=apache&logoColor=white)
PHP (https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
MySQL (https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
Linux (https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)

- Microsoft Azure (VNet, VM, Load Balancer, NAT Gateway, Azure Monitor)
- Ubuntu Server 22.04 LTS
- Apache Web Server
- PHP / PDO
- MySQL
- Log Analytics Workspace
- SSH / Terminal

💡 Key Takeaways

This project demonstrates the ability to design and deploy a multi-tier, high availability cloud infrastructure from scratch. Every phase required hands-on configuration, troubleshooting, and validation - reflecting the real-world responsibilities of a cloud engineer. The completed infrastructure handles traffic distribution, database connectivity, outbound security, and observability in a production-grade architecture.

🗂️ Repository Structure

`
ha-web-infrastructure-azure/
├── README.md
└── screenshots/
    ├── haweb_infr_rg.png
    ├── phase1/
    ├── phase2/
    ├── phase3/
    ├── phase4/
    ├── phase5/
    ├── phase6/
    ├── phase7/
    └── phase8/
`

Built by Maurrin Carter | @maxmagnac (https://github.com/maxmagnac) | Microsoft Azure | 2026
`
