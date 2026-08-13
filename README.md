# High Availability Web Infrastructure on Microsoft Azure

A resilient, multi-tier web infrastructure deployed on Microsoft Azure featuring segmented virtual networks, secure private database backends, load balancing, NAT gateways, and automated monitoring/alerts.

---

## Phase 1: Virtual Network & Network Security Groups (NSGs)

Configured the foundational networking environment, including the Virtual Network (VNet), public and private subnets, and Network Security Groups to control inbound and outbound traffic securely.

* **VNet Overview:**

* **Subnets (Public & Private):**

* **NSG Overview:**

* **Public NSG Inbound Rules:**

* **Private NSG Inbound Rules:**

* **Private NSG Subnets:**

* **Public NSG Subnets:**


---

## Phase 2: Compute Provisioning & Web Server Configuration

Provisioned web and database virtual machines across the environment, configured their instance settings, and installed the Nginx web server on the web nodes.

* **Both VMs Overview:**

* **Both VMs Responding Test:**

* **VM1 and VM2 Side-by-Side:**

* **VM1 Settings Part 1:**

* **VM1 Settings Part 2:**

* **VM2 Settings Part 1:**

* **VM2 Settings Part 2:**

* **Database VM (vm-db-01):**

* **Database VM 1 Settings Part 1:**

* **Database VM 1 Settings Part 2:**

* **Database VM 2 Settings Part 1:**

* **Database VM 2 Settings Part 2:**

* **Nginx Install Output (vm-web-01):**

* **Nginx Install Output (vm-web-02):**

* **Nginx Status (vm-web-01):**

* **Nginx Status (vm-web-02):**


---

## Phase 3: Load Balancer Setup & Health Probes

Implemented an Azure Load Balancer to distribute incoming traffic evenly across backend web virtual machines, configuring health probes and backend pool associations.

* **Load Balancer Overview:**

* **Load Balancer Deployment Success:**

* **Load Balancer Settings Part 1:**

* **Load Balancer Settings Part 2:**

* **Load Balancer VM Health:**

* **Load Balancer Test Success (vm-web-01):**

* **Load Balancer Test Success (vm-web-02):**


---

## Phase 4: NAT Gateway Integration

Configured an Azure NAT Gateway and associated it with private subnets to enable secure outbound internet connectivity for resources without public IP addresses.

* **NAT Gateway Overview:**

* **NAT Gateway Subnet Association:**

* **NAT Gateway Subnets Associated:**

* **VNet Subnets Private & Public Reference:**


---

## Phase 5: Database Tier Configuration & Connectivity

Deployed and configured MySQL on database backend instances, established internal database connectivity, and tested queries from the web servers.

* **Database Connectivity Verification:**

* **MySQL Install Output (vm-db-01):**

* **MySQL Status (vm-db-01):**

* **MySQL Monitor Prompt from vm-web-01:**

* **MySQL Monitor Prompt from vm-web-02:**

* **Database VMs (vm-db-01 and db-02):**


---

## Phase 6: Monitoring, Metrics, & Alerts

Set up a Log Analytics Workspace, configured alert rules for the load balancer and virtual machines, simulated a CPU load spike, and validated notification email delivery.

* **Log Analytics Workspace:**

* **Load Balancer Alert Overview:**

* **VM Web 01 Alerts:**

* **VM Web 02 Alerts:**

* **VM DB 01 Alerts:**

* **CPU Spike Simulation:**

* **Alert Email Notification 1:**

* **Alert Email Notification 2:**

* **Alert Email Notification 3:**


---

## Phase 7: Local Validation & Failover Testing

Performed local `curl` tests against individual web nodes, validated browser response successes, and conducted load balancer failover tests to ensure high availability.

* **Browser Success Verification:**

* **Curl Localhost (vm-web-01):**

* **Curl Localhost (vm-web-02):**

* **VM Web 01 Localhost Success:**

* **VM Web 02 Localhost Success:**

* **Load Balancer Connectivity Test:**

* **Load Balancer Failover Test:**


---

## Phase 8: End-to-End Application Validation

Conducted final end-to-end testing of the deployed web application through the load balancer, verifying multi-node response handling and stable application behavior.

* **Load Balancer Curl (Phase 8):**

* **Load Balancer Connectivity (Phase 8 - 1):**

* **Load Balancer Connectivity (Phase 8 - 2):**

* **VM Web 01 Application View (Phase 8):**

* **VM Web 02 Application View (Phase 8):**
