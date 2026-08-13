# High Availability Web Infrastructure on Microsoft Azure

A resilient, multi-tier web infrastructure deployed on Microsoft Azure featuring segmented virtual networks, secure private database backends, load balancing, NAT gateways, and automated monitoring/alerts.

---

## Phase 1: Virtual Network & Network Security Groups (NSGs)
Configured the foundational networking environment, including the Virtual Network (VNet), public and private subnets, and Network Security Groups to control inbound and outbound traffic securely.

* **VNet Overview:**
  <img src="screenshots/phase1/hawebvnet_overview.png" alt="VNet Overview" width="700">

* **Subnets (Public & Private):**
  <img src="screenshots/phase1/hawebvnet_subnets_priv_pub.png" alt="Subnets Private and Public" width="700">

* **NSG Overview:**
  <img src="screenshots/phase1/hawebNSGs.png" alt="NSGs" width="700">

* **Public NSG Inbound Rules:**
  <img src="screenshots/phase1/hawebNSGs_public-nsg inbound rules.png" alt="Public NSG Inbound Rules" width="700">

* **Private NSG Inbound Rules:**
  <img src="screenshots/phase1/haweb_private-nsg inbound rules.png" alt="Private NSG Inbound Rules" width="700">

* **Private NSG Subnets:**
  <img src="screenshots/phase1/haweb_private-nsg subnets.png" alt="Private NSG Subnets" width="700">

* **Public NSG Subnets:**
  <img src="screenshots/phase1/haweb_public-nsg subnets.png" alt="Public NSG Subnets" width="700">

---

## Phase 2: Compute Provisioning & Web Server Configuration
Provisioned web and database virtual machines across the environment, configured their instance settings, and installed the Nginx web server on the web nodes.

* **Both VMs Overview:**
  <img src="screenshots/phase2/haweb_Both VMs overview.png" alt="Both VMs Overview" width="700">

* **Both VMs Responding Test:**
  <img src="screenshots/phase2/haweb_Both VMs_responding_test.png" alt="Both VMs Responding Test" width="700">

* **VM1 and VM2 Side-by-Side:**
  <img src="screenshots/phase2/haweb_vm1 and vm2.png" alt="VM1 and VM2" width="700">

* **VM1 Settings Part 1:**
  <img src="screenshots/phase2/haweb_vm1_settings1.png" alt="VM1 Settings 1" width="700">

* **VM1 Settings Part 2:**
  <img src="screenshots/phase2/haweb_vm1_settings2.png" alt="VM1 Settings 2" width="700">

* **VM2 Settings Part 1:**
  <img src="screenshots/phase2/haweb_vm2_settings1.png" alt="VM2 Settings 1" width="700">

* **VM2 Settings Part 2:**
  <img src="screenshots/phase2/haweb_vm2_settings2.png" alt="VM2 Settings 2" width="700">

* **Database VM (vm-db-01):**
  <img src="screenshots/phase2/haweb_vm-db-01.png" alt="VM DB 01" width="700">

* **Database VM 1 Settings Part 1:**
  <img src="screenshots/phase2/haweb_vm-db-01_settings1.png" alt="VM DB 01 Settings 1" width="700">

* **Database VM 1 Settings Part 2:**
  <img src="screenshots/phase2/haweb_vm-db-01_settings2.png" alt="VM DB 01 Settings 2" width="700">

* **Database VM 2 Settings Part 1:**
  <img src="screenshots/phase2/haweb_vm-db-02_settings1.png" alt="VM DB 02 Settings 1" width="700">

* **Database VM 2 Settings Part 2:**
  <img src="screenshots/phase2/haweb_vm-db-02_settings2.png" alt="VM DB 02 Settings 2" width="700">

* **Nginx Install Output (vm-web-01):**
  <img src="screenshots/phase2/haweb_Nginx install_output_ vm-web-01.png" alt="Nginx Install Output VM Web 01" width="700">

* **Nginx Install Output (vm-web-02):**
  <img src="screenshots/phase2/haweb_Nginx_install_output_vm-web-02.png" alt="Nginx Install Output VM Web 02" width="700">

* **Nginx Status (vm-web-01):**
  <img src="screenshots/phase2/haweb_Nginx_status_vm-web-01.png" alt="Nginx Status VM Web 01" width="700">

* **Nginx Status (vm-web-02):**
  <img src="screenshots/phase2/haweb_Nginx_status_vm-web-02.png" alt="Nginx Status VM Web 02" width="700">

---

## Phase 3: Load Balancer Setup & Health Probes
Implemented an Azure Load Balancer to distribute incoming traffic evenly across backend web virtual machines, configuring health probes and backend pool associations.

* **Load Balancer Overview:**
  <img src="screenshots/phase3/haweb_lb_overview.png" alt="LB Overview" width="700">

* **Load Balancer Deployment Success:**
  <img src="screenshots/phase3/haweb_lb_deploysuccess.png" alt="LB Deployment Success" width="700">

* **Load Balancer Settings Part 1:**
  <img src="screenshots/phase3/haweb_lb_settings1.png" alt="LB Settings 1" width="700">

* **Load Balancer Settings Part 2:**
  <img src="screenshots/phase3/haweb_lb_settings2.png" alt="LB Settings 2" width="700">

* **Load Balancer VM Health:**
  <img src="screenshots/phase3/haweb_lb_vm_health.png" alt="LB VM Health" width="700">

* **Load Balancer Test Success (vm-web-01):**
  <img src="screenshots/phase3/haweb_lb-vm-web-01-success.png" alt="LB VM Web 01 Success" width="700">

* **Load Balancer Test Success (vm-web-02):**
  <img src="screenshots/phase3/haweb_lb-vm-web-02-success.png" alt="LB VM Web 02 Success" width="700">

---

## Phase 4: NAT Gateway Integration
Configured an Azure NAT Gateway and associated it with private subnets to enable secure outbound internet connectivity for resources without public IP addresses.

* **NAT Gateway Overview:**
  <img src="screenshots/phase4/haweb_natgateway_overview.png" alt="NAT Gateway Overview" width="700">

* **NAT Gateway Subnet Association:**
  <img src="screenshots/phase4/haweb_natgateway_subnet_association.png" alt="NAT Gateway Subnet Association" width="700">

* **NAT Gateway Subnets Associated:**
  <img src="screenshots/phase4/haweb_natgateway_subnets_associated.png" alt="NAT Gateway Subnets Associated" width="700">

* **VNet Subnets Private & Public Reference:**
  <img src="screenshots/phase4/hawebvnet_subnets_priv_pub.png" alt="VNet Subnets Private and Public" width="700">

---

## Phase 5: Database Tier Configuration & Connectivity
Deployed and configured MySQL on database backend instances, established internal database connectivity, and tested queries from the web servers.

* **Database Connectivity Verification:**
  <img src="screenshots/phase5/haweb-db-connectivity.png" alt="DB Connectivity" width="700">

* **MySQL Install Output (vm-db-01):**
  <img src="screenshots/phase5/haweb_mysql_install_output_vm-db-01.png" alt="MySQL Install Output" width="700">

* **MySQL Status (vm-db-01):**
  <img src="screenshots/phase5/haweb_mysql_status_vm-db-01.png" alt="MySQL Status" width="700">

* **MySQL Monitor Prompt from vm-web-01:**
  <img src="screenshots/phase5/haweb_MySQL monitor prompt from vm-web-01.png" alt="MySQL Monitor Prompt VM Web 01" width="700">

* **MySQL Monitor Prompt from vm-web-02:**
  <img src="screenshots/phase5/haweb_MySQL monitor prompt from vm-web-02.png" alt="MySQL Monitor Prompt VM Web 02" width="700">

* **Database VMs (vm-db-01 and db-02):**
  <img src="screenshots/phase5/haweb_vm-db-01_and_db-02.png" alt="VM DB 01 and DB 02" width="700">

---

## Phase 6: Monitoring, Metrics, & Alerts
Set up a Log Analytics Workspace, configured alert rules for the load balancer and virtual machines, simulated a CPU load spike, and validated notification email delivery.

* **Log Analytics Workspace:**
  <img src="screenshots/phase6/haweb-log-analytics-workspace.png" alt="Log Analytics Workspace" width="700">

* **Load Balancer Alert Overview:**
  <img src="screenshots/phase6/haweb-lb-alert-overview.png" alt="LB Alert Overview" width="700">

* **VM Web 01 Alerts:**
  <img src="screenshots/phase6/haweb-vm-web-01-alerts.png" alt="VM Web 01 Alerts" width="700">

* **VM Web 02 Alerts:**
  <img src="screenshots/phase6/haweb-vm-web-02-alerts.png" alt="VM Web 02 Alerts" width="700">

* **VM DB 01 Alerts:**
  <img src="screenshots/phase6/haweb-vm-db-01-alerts.png" alt="VM DB 01 Alerts" width="700">

* **CPU Spike Simulation:**
  <img src="screenshots/phase6/haweb-cpu-spike.png" alt="CPU Spike" width="700">

* **Alert Email Notification 1:**
  <img src="screenshots/phase6/haweb-alert-email_1.png" alt="Alert Email 1" width="700">

* **Alert Email Notification 2:**
  <img src="screenshots/phase6/haweb-alert-email_2.png" alt="Alert Email 2" width="700">

* **Alert Email Notification 3:**
  <img src="screenshots/phase6/haweb-alert-email_3.png" alt="Alert Email 3" width="700">

---

## Phase 7: Local Validation & Failover Testing
Performed local `curl` tests against individual web nodes, validated browser response successes, and conducted load balancer failover tests to ensure high availability.

* **Browser Success Verification:**
  <img src="screenshots/phase7/haweb_browser_success.png" alt="Browser Success" width="700">

* **Curl Localhost (vm-web-01):**
  <img src="screenshots/phase7/haweb_curl_localhost_vm-web-01.png" alt="Curl Localhost VM Web 01" width="700">

* **Curl Localhost (vm-web-02):**
  <img src="screenshots/phase7/haweb_curl_localhost_vm-web-02.png" alt="Curl Localhost VM Web 02" width="700">

* **VM Web 01 Localhost Success:**
  <img src="screenshots/phase7/haweb_vm-web-01-localhost-success.png" alt="VM Web 01 Localhost Success" width="700">

* **VM Web 02 Localhost Success:**
  <img src="screenshots/phase7/haweb_vm-web-02-localhost-success.png" alt="VM Web 02 Localhost Success" width="700">

* **Load Balancer Connectivity Test:**
  <img src="screenshots/phase7/haweb-lb-connectivity.png" alt="LB Connectivity" width="700">

* **Load Balancer Failover Test:**
  <img src="screenshots/phase7/haweb-lb-failover-test.png" alt="LB Failover Test" width="700">

---

## Phase 8: End-to-End Application Validation
Conducted final end-to-end testing of the deployed web application through the load balancer, verifying multi-node response handling and stable application behavior.

* **Load Balancer Curl (Phase 8):**
  <img src="screenshots/phase8/haweb-lb-curl_phs8.png" alt="LB Curl Phase 8" width="700">

* **Load Balancer Connectivity (Phase 8 - 1):**
  <img src="screenshots/phase8/haweb-lb-connectivity_phs8_1.png" alt="LB Connectivity Phase 8 1" width="700">

* **Load Balancer Connectivity (Phase 8 - 2):**
  <img src="screenshots/phase8/haweb-lb-connectivity_phs8_2.png" alt="LB Connectivity Phase 8 2" width="700">

* **VM Web 01 Application View (Phase 8):**
  <img src="screenshots/phase8/haweb-vm-web-01-app_phs8.png" alt="VM Web 01 App Phase 8" width="700">

* **VM Web 02 Application View (Phase 8):**
  <img src="screenshots/phase8/haweb-vm-web-02-app_phs8.png" alt="VM Web 02 App Phase 8" width="700">
