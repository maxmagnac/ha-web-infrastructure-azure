`markdown
High Availability Web Infrastructure on Azure

A hands-on cloud engineering project demonstrating the design and deployment of a production-grade, highly available web infrastructure on Microsoft Azure.

Azure (https://img.shields.io/badge/Azure-Cloud-blue) Status (https://img.shields.io/badge/Status-Complete-brightgreen)

Architecture Overview

This project provisions a fully redundant web infrastructure including virtual networks, load balancing, database servers, NAT gateway, monitoring, and application deployment across multiple availability zones.

Resource Group Overview:
Infrastructure Resource Group (haweb_infr_rg.png)

Phase 1 - Network Setup

Configured the virtual network, subnets, and network security groups to establish a secure and segmented network foundation.

VNet Overview (screenshots/phase1/hawebvnet_overview.png)
Subnets (screenshots/phase1/hawebvnet_subnets_priv_pub.png)
NSGs (screenshots/phase1/hawebNSGs.png)
Public NSG Inbound Rules (screenshots/phase1/hawebNSGs_public-nsg inbound rules.png)
Private NSG Subnets (screenshots/phase1/haweb_private-nsg subnets.png)
Public NSG Subnets (screenshots/phase1/haweb_public-nsg subnets.png)

Phase 2 - Virtual Machine Deployment

Deployed web server VMs (vm-web-01, vm-web-02) and database server VMs (vm-db-01, vm-db-02).

VM Web Servers (haweb_vm1 and vm2.png)
VM Web-01 Settings (haweb_vm1_settings1.png)
VM Web-02 Settings (haweb_vm2_settings1.png)
Both VMs Overview (haweb_Both VMs overview.png)
DB VM 01 (haweb_vm-db-01.png)
Both DB VMs (haweb_vm-db-01_and_db-02.png)

Phase 3 - Load Balancer Configuration

Configured the Azure Load Balancer (ha-web-lb) to distribute traffic across both web servers.

LB Overview (haweb_lb_overview.png)
LB Deploy Success (haweb_lb_deploysuccess.png)
LB Settings (haweb_lb_settings1.png)
LB VM Health (haweb_lb_vm_health.png)

Phase 4 - NAT Gateway Configuration

Deployed and configured the NAT Gateway (ha-web-nat-gateway) to manage outbound internet connectivity for private subnet resources.

NAT Gateway Overview (screenshots/phase4/haweb_natgateway_overview.png)
NAT Gateway Subnet Association (screenshots/phase4/haweb_natgateway_subnet_association.png)
NAT Gateway Subnets Associated (screenshots/phase4/haweb_natgateway_subnets_associated.png)

Phase 5 - Nginx Web Server Installation

Installed and configured Nginx on both web server VMs to serve web traffic.

Nginx Install VM Web-01 (haweb_Nginx install_output_ vm-web-01.png)
Nginx Status VM Web-01 (haweb_Nginx_status_vm-web-01.png)
Nginx Install VM Web-02 (haweb_Nginx_install_output_vm-web-02.png)
Nginx Status VM Web-02 (haweb_Nginx_status_vm-web-02.png)
Curl Localhost VM Web-01 (haweb_curl_localhost_vm-web-01.png)
Curl Localhost VM Web-02 (haweb_curl_localhost_vm-web-02.png)

Phase 6 - Database Configuration

Installed and configured MySQL on the database VMs and validated connectivity from the web servers.

MySQL Install Output (haweb_mysql_install_output_vm-db-01.png)
MySQL Status (haweb_mysql_status_vm-db-01.png)
MySQL Monitor from VM Web-01 (haweb_MySQL monitor prompt from vm-web-01.png)
MySQL Monitor from VM Web-02 (haweb_MySQL monitor prompt from vm-web-02.png)

Phase 7 - Monitoring & Alerts

Configured Azure Monitor, Log Analytics Workspace, and alert rules for CPU spikes and VM health.

Log Analytics Workspace (haweb-log-analytics-workspace.png)
VM Web-01 Alerts (haweb-vm-web-01-alerts.png)
VM Web-02 Alerts (haweb-vm-web-02-alerts.png)
VM DB-01 Alerts (haweb-vm-db-01-alerts.png)
CPU Spike (haweb-cpu-spike.png)
Alert Email 1 (haweb-alert-email_1.png)
Alert Email 2 (haweb-alert-email_2.png)
Alert Email 3 (haweb-alert-email_3.png)

Phase 8 - Application Deployment & Testing

Deployed the web application and validated end-to-end connectivity through the load balancer.

LB Curl Test (haweb-lb-curl_phs8.png)
LB Connectivity 1 (haweb-lb-connectivity_phs8_1.png)
LB Connectivity 2 (haweb-lb-connectivity_phs8_2.png)
VM Web-01 App (haweb-vm-web-01-app_phs8.png)
VM Web-02 App (haweb-vm-web-02-app_phs8.png)
LB Failover Test (haweb-lb-failover-test.png)
DB Connectivity (haweb-db-connectivity.png)

Technologies Used

- Microsoft Azure (Virtual Network, Load Balancer, NAT Gateway, Azure Monitor)
- Ubuntu Linux VMs
- Nginx Web Server
- MySQL Database
- Azure Log Analytics

Author

Maurrin Carter - Cloud Engineer
GitHub (https://github.com/maxmagnac)
`
