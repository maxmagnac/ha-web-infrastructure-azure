``markdown
High Availability Web Infrastructure on Azure

A hands-on cloud engineering project demonstrating the design and deployment of a production-grade, highly available web infrastructure on Microsoft Azure.

Azure (https://img.shields.io/badge/Azure-Cloud-blue) Status (https://img.shields.io/badge/Status-Complete-brightgreen)

Architecture Overview

This project provisions a fully redundant web infrastructure including virtual networks, load balancing, database servers, NAT gateway, monitoring, and application deployment across multiple availability zones.

Phase 1 - Network Setup

Configured the virtual network, subnets, and network security groups to establish a secure and segmented network foundation.

VNet Overview (screenshots/phase1/hawebvnet_overview.png)
Subnets (screenshots/phase1/hawebvnet_subnets_priv_pub.png)
NSGs (screenshots/phase1/hawebNSGs.png)
Public NSG Inbound Rules (screenshots/phase1/hawebNSGs_public-nsg%20inbound%20rules.png)
Private NSG Inbound Rules (screenshots/phase1/haweb_private-nsg%20inbound%20rules.png)
Private NSG Subnets (screenshots/phase1/haweb_private-nsg%20subnets.png)
Public NSG Subnets (screenshots/phase1/haweb_public-nsg%20subnets.png)

Phase 2 - Virtual Machine Deployment

Deployed web server VMs (vm-web-01, vm-web-02) and database server VMs (vm-db-01, vm-db-02).

Both VMs Overview (screenshots/phase2/haweb_Both%20VMs%20overview.png)
Both VMs Responding (screenshots/phase2/haweb_Both%20VMs_responding_test.png)
VM1 and VM2 (screenshots/phase2/haweb_vm1%20and%20vm2.png)
VM Web-01 Settings 1 (screenshots/phase2/haweb_vm1_settings1.png)
VM Web-01 Settings 2 (screenshots/phase2/haweb_vm1_settings2.png)
VM Web-02 Settings 1 (screenshots/phase2/haweb_vm2_settings1.png)
VM Web-02 Settings 2 (screenshots/phase2/haweb_vm2_settings2.png)
VM DB-01 (screenshots/phase2/haweb_vm-db-01.png)
VM DB-01 Settings 1 (screenshots/phase2/haweb_vm-db-01_settings1.png)
VM DB-01 Settings 2 (screenshots/phase2/haweb_vm-db-01_settings2.png)
VM DB-02 Settings 1 (screenshots/phase2/haweb_vm-db-02_settings1.png)
VM DB-02 Settings 2 (screenshots/phase2/haweb_vm-db-02_settings2.png)
Nginx Install VM Web-01 (screenshots/phase2/haweb_Nginx%20install_output_%20vm-web-01.png)
Nginx Install VM Web-02 (screenshots/phase2/haweb_Nginx_install_output_vm-web-02.png)
Nginx Status VM Web-01 (screenshots/phase2/haweb_Nginx_status_vm-web-01.png)
Nginx Status VM Web-02 (screenshots/phase2/haweb_Nginx_status_vm-web-02.png)

Phase 3 - Load Balancer Configuration

Configured the Azure Load Balancer (ha-web-lb) to distribute traffic across both web servers.

LB Overview (screenshots/phase3/haweb_lb_overview.png)
LB Deploy Success (screenshots/phase3/haweb_lb_deploysuccess.png)
LB Settings 1 (screenshots/phase3/haweb_lb_settings1.png)
LB Settings 2 (screenshots/phase3/haweb_lb_settings2.png)
LB VM Health (screenshots/phase3/haweb_lb_vm_health.png)
LB VM Web-01 Success (screenshots/phase3/haweb_lb-vm-web-01-success.png)
LB VM Web-02 Success (screenshots/phase3/haweb_lb-vm-web-02-success.png)

Phase 4 - NAT Gateway Configuration

Deployed and configured the NAT Gateway (ha-web-nat-gateway) to manage outbound internet connectivity for private subnet resources.

NAT Gateway Overview (screenshots/phase4/haweb_natgateway_overview.png)
NAT Gateway Subnet Association (screenshots/phase4/haweb_natgateway_subnet_association.png)
NAT Gateway Subnets Associated (screenshots/phase4/haweb_natgateway_subnets_associated.png)
VNet Subnets (screenshots/phase4/hawebvnet_subnets_priv_pub.png)

Phase 5 - Database Configuration

Installed and configured MySQL on the database VMs and validated connectivity from the web servers.

DB Connectivity (screenshots/phase5/haweb-db-connectivity.png)
MySQL Install Output (screenshots/phase5/haweb_mysql_install_output_vm-db-01.png)
MySQL Status (screenshots/phase5/haweb_mysql_status_vm-db-01.png)
MySQL Monitor VM Web-01 (screenshots/phase5/haweb_MySQL%20monitor%20prompt%20from%20vm-web-01.png)
MySQL Monitor VM Web-02 (screenshots/phase5/haweb_MySQL%20monitor%20prompt%20from%20vm-web-02.png)
Both DB VMs (screenshots/phase5/haweb_vm-db-01_and_db-02.png)

Phase 6 - Monitoring & Alerts

Configured Azure Monitor, Log Analytics Workspace, and alert rules for CPU spikes and VM health.

Log Analytics Workspace (screenshots/phase6/haweb-log-analytics-workspace.png)
LB Alert Overview (screenshots/phase6/haweb-lb-alert-overview.png)
VM Web-01 Alerts (screenshots/phase6/haweb-vm-web-01-alerts.png)
VM Web-02 Alerts (screenshots/phase6/haweb-vm-web-02-alerts.png)
VM DB-01 Alerts (screenshots/phase6/haweb-vm-db-01-alerts.png)
CPU Spike (screenshots/phase6/haweb-cpu-spike.png)
Alert Email 1 (screenshots/phase6/haweb-alert-email_1.png)
Alert Email 2 (screenshots/phase6/haweb-alert-email_2.png)
Alert Email 3 (screenshots/phase6/haweb-alert-email_3.png)

Phase 7 - Connectivity & Failover Testing

Validated end-to-end connectivity, load balancer failover, and browser access across both web servers.

Browser Success (screenshots/phase7/haweb_browser_success.png)
Curl Localhost VM Web-01 (screenshots/phase7/haweb_curl_localhost_vm-web-01.png)
Curl Localhost VM Web-02 (screenshots/phase7/haweb_curl_localhost_vm-web-02.png)
VM Web-01 Localhost Success (screenshots/phase7/haweb_vm-web-01-localhost-success.png)
VM Web-02 Localhost Success (screenshots/phase7/haweb_vm-web-02-localhost-success.png)
LB Connectivity (screenshots/phase7/haweb-lb-connectivity.png)
LB Failover Test (screenshots/phase7/haweb-lb-failover-test.png)

Phase 8 - Application Deployment

Deployed the web application and validated full stack operation through the load balancer.

LB Curl Test (screenshots/phase8/haweb-lb-curl_phs8.png)
LB Connectivity 1 (screenshots/phase8/haweb-lb-connectivity_phs8_1.png)
LB Connectivity 2 (screenshots/phase8/haweb-lb-connectivity_phs8_2.png)
VM Web-01 App (screenshots/phase8/haweb-vm-web-01-app_phs8.png)
VM Web-02 App (screenshots/phase8/haweb-vm-web-02-app_phs8.png)

Technologies Used

- Microsoft Azure (Virtual Network, Load Balancer, NAT Gateway, Azure Monitor)
- Ubuntu Linux VMs
- Nginx Web Server
- MySQL Database
- Azure Log Analytics

Author

Maurrin Carter - Cloud Engineer
GitHub (https://github.com/maxmagnac)
