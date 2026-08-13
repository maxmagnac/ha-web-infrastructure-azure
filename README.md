# ha-web-infrastructure-azure
High Availability Web Infrastructure on Azure - Hands-On Cloud Engineering Project

Let's build it! 🔥 Here's your full GitHub README in Markdown:

``markdown
🏗️ High Availability Web Infrastructure on Azure

Azure (https://img.shields.io/badge/Cloud-Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
Terraform (https://img.shields.io/badge/IaC-Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
Ubuntu (https://img.shields.io/badge/OS-Ubuntu%2022.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
MySQL (https://img.shields.io/badge/Database-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
PHP (https://img.shields.io/badge/App-PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
Status (https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

Author: Maurrin Carter
GitHub: @maxmagnac (https://github.com/maxmagnac)
Platform: Microsoft Azure
Project Type: Hands-On Lab / Learning Project

📋 Project Overview

This project demonstrates hands-on cloud engineering skills through the full deployment of a high availability web infrastructure on Microsoft Azure. Every component - from virtual networking to load balancing, database connectivity, monitoring, and web application deployment - was built, configured, and validated manually.

This project serves as a portfolio piece showcasing real-world cloud architecture skills for a cloud engineering career.

🏛️ Architecture Summary

`
 ┌─────────────────────────────────────┐
 │ Microsoft Azure │
 │ │
 │ ┌──────────────────────────────┐ │
 │ │ Virtual Network │ │
 │ │ │ │
 │ │ ┌─────────┐ ┌─────────┐ │ │
 Internet ─────────▶ │vm-web-01│ │vm-web-02│ │ │
 │ │ └────┬────┘ └────┬────┘ │ │
 │ │ │ │ │ │
 │ │ ┌────▼─────────────▼────┐ │ │
 │ │ │ Azure Load Balancer │ │ │
 │ │ │ ha-web-lb │ │ │
 │ │ └────────────────────────┘ │ │
 │ │ │ │
 │ │ ┌─────────────────────────┐ │ │
 │ │ │ Private Subnet │ │ │
 │ │ │ ┌──────────────────┐ │ │ │
 │ │ │ │ vm-db-01 │ │ │ │
 │ │ │ │ MySQL Database │ │ │ │
 │ │ │ └──────────────────┘ │ │ │
 │ │ │ NAT Gateway │ │ │
 │ │ └─────────────────────────┘ │ │
 │ └──────────────────────────────┘ │
 │ │
 │ ┌──────────────────────────────┐ │
 │ │ Azure Monitor + Log Analytics│ │
 │ └──────────────────────────────┘ │
 └─────────────────────────────────────┘
`

Infrastructure Components

| Component | Resource Name | Details |
|-----------|--------------|---------|
| Virtual Network | ha-web-vnet | Segmented public/private subnets |
| Web Server 1 | vm-web-01 | Ubuntu 22.04 LTS - Apache/PHP |
| Web Server 2 | vm-web-02 | Ubuntu 22.04 LTS - Apache/PHP |
| Database Server | vm-db-01 | Ubuntu 22.04 LTS - MySQL |
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

Screenshots:

| Screenshot | Description |
|------------|-------------|
| hawebvnet_overview | Virtual Network overview showing VNet configuration |
| hawebvnet_subnets_priv_pub | VNet subnets showing public and private subnet setup |
| hawebNSGs | Network Security Groups overview |
| hawebNSGs_public-nsg inbound rules | Public NSG inbound rules configuration |
| haweb_public-nsg subnets | Public NSG subnet associations |
| haweb_private-nsg inbound rules | Private NSG inbound rules configuration |
| haweb_private-nsg subnets | Private NSG subnet associations |

Phase 2 - Virtual Machine Deployment

Deployed two Ubuntu Server 22.04 LTS web server VMs (vm-web-01 and vm-web-02) and one database server VM (vm-db-01). Configured each VM with appropriate network interfaces and placed them in their respective subnets. Installed and configured Nginx on both web servers.

Key skills demonstrated:
- Virtual Machine provisioning on Azure
- OS selection and VM sizing
- Multi-tier VM placement across subnets
- Web server installation and status verification

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb_vm1 and vm2 | Overview of both web server VMs |
| haweb_vm1_settings1 | vm-web-01 settings - Part 1 |
| haweb_vm1_settings2 | vm-web-01 settings - Part 2 |
| haweb_vm2_settings1 | vm-web-02 settings - Part 1 |
| haweb_vm2_settings2 | vm-web-02 settings - Part 2 |
| haweb_vm-db-01 | Database server VM overview |
| haweb_vm-db-01_settings1 | vm-db-01 settings - Part 1 |
| haweb_vm-db-01_settings2 | vm-db-01 settings - Part 2 |
| haweb_Nginx install_output_vm-web-01 | Nginx installation output on vm-web-01 |
| haweb_Nginx_install_output_vm-web-02 | Nginx installation output on vm-web-02 |
| haweb_Nginx_status_vm-web-01 | Nginx service status running on vm-web-01 |
| haweb_Nginx_status_vm-web-02 | Nginx service status running on vm-web-02 |
| haweb_Both VMs overview | Both web VMs running and confirmed |
| haweb_Both VMs_responding_test | Both web VMs responding to connectivity test |

Phase 3 - Load Balancer Configuration

Configured the Azure Load Balancer (ha-web-lb) with a frontend public IP, backend pool containing both web servers, health probes, and load balancing rules. Validated health probe responses from both VMs confirming active load balancer operation.

Key skills demonstrated:
- Azure Load Balancer provisioning
- Backend pool configuration
- Health probe setup and load balancing rules
- Load balancer validation and testing

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb_lb_deploysuccess | Load balancer deployment success confirmation |
| haweb_lb_overview | Load balancer overview and configuration |
| haweb_lb_settings1 | Load balancer settings - Part 1 |
| haweb_lb_settings2 | Load balancer settings - Part 2 |
| haweb_lb_vm_health | Load balancer VM health probe status |
| haweb_lb-vm-web-01-success | Health probe success for vm-web-01 |
| haweb_lb-vm-web-02-success | Health probe success for vm-web-02 |

Phase 4 - NAT Gateway Setup

Created and configured a NAT Gateway to provide secure outbound internet connectivity for the database subnet. This allows the database VM to receive updates and patches without exposure to inbound internet traffic.

Key skills demonstrated:
- NAT Gateway creation and subnet association
- Outbound connectivity design for private subnets
- Security-conscious network architecture

> 📸 NAT Gateway configuration captured in hawebvnet_subnets_priv_pub from Phase 1

Phase 5 - Database Deployment

Installed and configured MySQL on vm-db-01. Created a dedicated application database (haweb_db) and a scoped database user (haweb_user) with access limited to the application database only. Validated database connectivity from both web servers.

Key skills demonstrated:
- MySQL installation and configuration on Linux
- Database and user creation with scoped permissions
- Private network database access configuration
- Cross-tier connectivity validation

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb_mysql_install_output_vm-db-01 | MySQL installation output on vm-db-01 |
| haweb_mysql_status_vm-db-01 | MySQL service status running on vm-db-01 |
| haweb_MySQL monitor prompt from vm-web-01 | MySQL connection prompt accessed from vm-web-01 |
| haweb_MySQL monitor prompt from vm-web-02 | MySQL connection prompt accessed from vm-web-02 |
| haweb-db-connectivity | Database connectivity validation confirmation |
| haweb_vm-db-01_and_db-02 | Database VM infrastructure overview |

Phase 6 - Monitoring and Alerts

Created a Log Analytics Workspace (ha-web-logs) and connected it to the infrastructure. Configured Azure Monitor with custom alert rules across all three VMs. Validated alerts by triggering a CPU spike and confirming email delivery.

Key skills demonstrated:
- Log Analytics Workspace creation
- Azure Monitor configuration
- Custom alert rule setup per VM
- Alert validation through CPU spike testing

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb-log-analytics-workspace | Log Analytics Workspace creation and overview |
| haweb-lb-alert-overview | Azure Monitor alert rules overview |
| haweb-vm-web-01-alerts | Alert rules configured for vm-web-01 |
| haweb-vm-web-02-alerts | Alert rules configured for vm-web-02 |
| haweb-vm-db-01-alerts | Alert rules configured for vm-db-01 |
| haweb-cpu-spike | CPU spike triggered for alert validation |
| haweb-alert-email_1 | Alert email notification received - Part 1 |
| haweb-alert-email_2 | Alert email notification received - Part 2 |
| haweb-alert-email_3 | Alert email notification received - Part 3 |

Phase 7 - Testing and Validation

Conducted end-to-end testing of the entire infrastructure. Validated localhost connectivity on both web servers, confirmed load balancer failover behavior, and verified full stack connectivity through the load balancer's public IP.

Key skills demonstrated:
- Infrastructure validation and troubleshooting
- Localhost and cross-tier connectivity testing
- Load balancer failover testing
- Full stack validation through public IP

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb_vm-web-01-localhost-success | Localhost connectivity success on vm-web-01 |
| haweb_vm-web-02-localhost-success | Localhost connectivity success on vm-web-02 |
| haweb_curl_localhost_vm-web-01 | curl localhost output on vm-web-01 |
| haweb_curl_localhost_vm-web-02 | curl localhost output on vm-web-02 |
| haweb-lb-failover-test | Load balancer failover test result |
| haweb-lb-connectivity | Load balancer public IP connectivity confirmed |
| haweb_browser_success | Browser successfully serving app through load balancer |

Phase 8 - Web Application Deployment

Deployed a PHP web application to both web servers connecting to the MySQL database using the private IP of vm-db-01. Validated the full stack by curling the load balancer's public IP and confirming round-robin traffic distribution between both web servers with live database connectivity on every request.

Key skills demonstrated:
- PHP application deployment on Apache
- Database connectivity configuration from the application layer
- End-to-end load balancer validation with live traffic
- Round-robin traffic distribution confirmation

Screenshots:

| Screenshot | Description |
|------------|-------------|
| haweb-vm-web-01-app_phs8 | curl output confirming PHP app and DB connection on vm-web-01 |
| haweb-vm-web-02-app_phs8 | curl output confirming PHP app and DB connection on vm-web-02 |
| haweb-lb-connectivity_phs8_1 | Browser showing load balancer serving PHP app - vm-web-01 |
| haweb-lb-connectivity_phs8_2 | Browser showing load balancer serving PHP app - vm-web-02 |
| haweb-lb-curl_phs8 | Terminal showing round-robin curl output switching between both servers |

✅ Validation Results

| Test | Result |
|------|--------|
| VNet and subnet configuration | ✅ SUCCESS |
| VM deployment - all three VMs | ✅ SUCCESS |
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
├── screenshots/
│ ├── phase1/
│ ├── phase2/
│ ├── phase3/
│ ├── phase4/
│ ├── phase5/
│ ├── phase6/
│ ├── phase7/
│ └── phase8/
`

Built by Maurrin Carter | @maxmagnac (https://github.com/maxmagnac) | Microsoft Azure | 2026
`

That's your full GitHub README! 🔥💪🏾

Next steps to publish:
1. Create a new GitHub repo named ha-web-infrastructure-azure
2. Paste this as your README.md`
3. Upload your screenshots organized into phase folders matching the structure above

Ready to move to Project 2 - Terraform? 🚀
