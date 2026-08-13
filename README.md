# High Availability Web Infrastructure on Microsoft Azure

A resilient, multi-tier web infrastructure deployed on Microsoft Azure featuring segmented virtual networks, secure private database backends, load balancing, NAT gateways, and automated monitoring/alerts.

---

## Phase 1: Virtual Network & Network Security Groups (NSGs)
Configured the foundational networking environment, including the Virtual Network (VNet), public and private subnets, and Network Security Groups to control inbound and outbound traffic securely.

* **VNet Overview:**
  ![VNet Overview](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/hawebvnet_overview.png)
* **Subnets (Public & Private):**
  ![Subnets Private and Public](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/hawebvnet_subnets_priv_pub.png)
* **NSG Overview:**
  ![NSGs](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/hawebNSGs.png)
* **Public NSG Inbound Rules:**
  ![Public NSG Inbound Rules](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/hawebNSGs_public-nsg%20inbound%20rules.png)
* **Private NSG Inbound Rules:**
  ![Private NSG Inbound Rules](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/haweb_private-nsg%20inbound%20rules.png)
* **Private NSG Subnets:**
  ![Private NSG Subnets](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/haweb_private-nsg%20subnets.png)
* **Public NSG Subnets:**
  ![Public NSG Subnets](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase1/haweb_public-nsg%20subnets.png)

---

## Phase 2: Compute Provisioning & Web Server Configuration
Provisioned web and database virtual machines across the environment, configured their instance settings, and installed the Nginx web server on the web nodes.

* **Both VMs Overview:**
  ![Both VMs Overview](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Both%20VMs%20overview.png)
* **Both VMs Responding Test:**
  ![Both VMs Responding Test](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Both%20VMs_responding_test.png)
* **VM1 and VM2 Side-by-Side:**
  ![VM1 and VM2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm1%20and%20vm2.png)
* **VM1 Settings Part 1:**
  ![VM1 Settings 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm1_settings1.png)
* **VM1 Settings Part 2:**
  ![VM1 Settings 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm1_settings2.png)
* **VM2 Settings Part 1:**
  ![VM2 Settings 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm2_settings1.png)
* **VM2 Settings Part 2:**
  ![VM2 Settings 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm2_settings2.png)
* **Database VM (vm-db-01):**
  ![VM DB 01](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm-db-01.png)
* **Database VM 1 Settings Part 1:**
  ![VM DB 01 Settings 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm-db-01_settings1.png)
* **Database VM 1 Settings Part 2:**
  ![VM DB 01 Settings 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm-db-01_settings2.png)
* **Database VM 2 Settings Part 1:**
  ![VM DB 02 Settings 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm-db-02_settings1.png)
* **Database VM 2 Settings Part 2:**
  ![VM DB 02 Settings 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_vm-db-02_settings2.png)
* **Nginx Install Output (vm-web-01):**
  ![Nginx Install Output VM Web 01](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Nginx%20install_output_%20vm-web-01.png)
* **Nginx Install Output (vm-web-02):**
  ![Nginx Install Output VM Web 02](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Nginx_install_output_vm-web-02.png)
* **Nginx Status (vm-web-01):**
  ![Nginx Status VM Web 01](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Nginx_status_vm-web-01.png)
* **Nginx Status (vm-web-02):**
  ![Nginx Status VM Web 02](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase2/haweb_Nginx_status_vm-web-02.png)

---

## Phase 3: Load Balancer Setup & Health Probes
Implemented an Azure Load Balancer to distribute incoming traffic evenly across backend web virtual machines, configuring health probes and backend pool associations.

* **Load Balancer Overview:**
  ![LB Overview](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb_overview.png)
* **Load Balancer Deployment Success:**
  ![LB Deployment Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb_deploysuccess.png)
* **Load Balancer Settings Part 1:**
  ![LB Settings 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb_settings1.png)
* **Load Balancer Settings Part 2:**
  ![LB Settings 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb_settings2.png)
* **Load Balancer VM Health:**
  ![LB VM Health](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb_vm_health.png)
* **Load Balancer Test Success (vm-web-01):**
  ![LB VM Web 01 Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb-vm-web-01-success.png)
* **Load Balancer Test Success (vm-web-02):**
  ![LB VM Web 02 Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase3/haweb_lb-vm-web-02-success.png)

---

## Phase 4: NAT Gateway Integration
Configured an Azure NAT Gateway and associated it with private subnets to enable secure outbound internet connectivity for resources without public IP addresses.

* **NAT Gateway Overview:**
  ![NAT Gateway Overview](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase4/haweb_natgateway_overview.png)
* **NAT Gateway Subnet Association:**
  ![NAT Gateway Subnet Association](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase4/haweb_natgateway_subnet_association.png)
* **NAT Gateway Subnets Associated:**
  ![NAT Gateway Subnets Associated](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase4/haweb_natgateway_subnets_associated.png)
* **VNet Subnets Private & Public Reference:**
  ![VNet Subnets Private and Public](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase4/hawebvnet_subnets_priv_pub.png)

---

## Phase 5: Database Tier Configuration & Connectivity
Deployed and configured MySQL on database backend instances, established internal database connectivity, and tested queries from the web servers.

* **Database Connectivity Verification:**
  ![DB Connectivity](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb-db-connectivity.png)
* **MySQL Install Output (vm-db-01):**
  ![MySQL Install Output](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb_mysql_install_output_vm-db-01.png)
* **MySQL Status (vm-db-01):**
  ![MySQL Status](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb_mysql_status_vm-db-01.png)
* **MySQL Monitor Prompt from vm-web-01:**
  ![MySQL Monitor Prompt VM Web 01](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb_MySQL%20monitor%20prompt%20from%20vm-web-01.png)
* **MySQL Monitor Prompt from vm-web-02:**
  ![MySQL Monitor Prompt VM Web 02](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb_MySQL%20monitor%20prompt%20from%20vm-web-02.png)
* **Database VMs (vm-db-01 and db-02):**
  ![VM DB 01 and DB 02](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase5/haweb_vm-db-01_and_db-02.png)

---

## Phase 6: Monitoring, Metrics, & Alerts
Set up a Log Analytics Workspace, configured alert rules for the load balancer and virtual machines, simulated a CPU load spike, and validated notification email delivery.

* **Log Analytics Workspace:**
  ![Log Analytics Workspace](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-log-analytics-workspace.png)
* **Load Balancer Alert Overview:**
  ![LB Alert Overview](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-lb-alert-overview.png)
* **VM Web 01 Alerts:**
  ![VM Web 01 Alerts](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-vm-web-01-alerts.png)
* **VM Web 02 Alerts:**
  ![VM Web 02 Alerts](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-vm-web-02-alerts.png)
* **VM DB 01 Alerts:**
  ![VM DB 01 Alerts](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-vm-db-01-alerts.png)
* **CPU Spike Simulation:**
  ![CPU Spike](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-cpu-spike.png)
* **Alert Email Notification 1:**
  ![Alert Email 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-alert-email_1.png)
* **Alert Email Notification 2:**
  ![Alert Email 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-alert-email_2.png)
* **Alert Email Notification 3:**
  ![Alert Email 3](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase6/haweb-alert-email_3.png)

---

## Phase 7: Local Validation & Failover Testing
Performed local `curl` tests against individual web nodes, validated browser response successes, and conducted load balancer failover tests to ensure high availability.

* **Browser Success Verification:**
  ![Browser Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb_browser_success.png)
* **Curl Localhost (vm-web-01):**
  ![Curl Localhost VM Web 01](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb_curl_localhost_vm-web-01.png)
* **Curl Localhost (vm-web-02):**
  ![Curl Localhost VM Web 02](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb_curl_localhost_vm-web-02.png)
* **VM Web 01 Localhost Success:**
  ![VM Web 01 Localhost Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb_vm-web-01-localhost-success.png)
* **VM Web 02 Localhost Success:**
  ![VM Web 02 Localhost Success](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb_vm-web-02-localhost-success.png)
* **Load Balancer Connectivity Test:**
  ![LB Connectivity](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb-lb-connectivity.png)
* **Load Balancer Failover Test:**
  ![LB Failover Test](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase7/haweb-lb-failover-test.png)

---

## Phase 8: End-to-End Application Validation
Conducted final end-to-end testing of the deployed web application through the load balancer, verifying multi-node response handling and stable application behavior.

* **Load Balancer Curl (Phase 8):**
  ![LB Curl Phase 8](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase8/haweb-lb-curl_phs8.png)
* **Load Balancer Connectivity (Phase 8 - 1):**
  ![LB Connectivity Phase 8 1](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase8/haweb-lb-connectivity_phs8_1.png)
* **Load Balancer Connectivity (Phase 8 - 2):**
  ![LB Connectivity Phase 8 2](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase8/haweb-lb-connectivity_phs8_2.png)
* **VM Web 01 Application View (Phase 8):**
  ![VM Web 01 App Phase 8](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase8/haweb-vm-web-01-app_phs8.png)
* **VM Web 02 Application View (Phase 8):**
  ![VM Web 02 App Phase 8](https://raw.githubusercontent.com/maxmagnac/ha-web-infrastructure-azure/main/screenshots/phase8/haweb-vm-web-02-app_phs8.png)
