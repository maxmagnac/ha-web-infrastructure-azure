# High Availability Web Infrastructure on Azure

A hands-on cloud engineering project demonstrating the design and deployment of a production-grade, highly available web infrastructure on Microsoft Azure.

 

---

## Architecture Overview

This project provisions a fully redundant web infrastructure including virtual networks, load balancing, database servers, NAT gateway, monitoring, and application deployment across multiple availability zones.

**Resource Group Overview:**

---

## Phase 1 - Network Setup

Configured the virtual network, subnets, and network security groups to establish a secure and segmented network foundation.

---

## Phase 2 - Virtual Machine Deployment

Deployed web server VMs (vm-web-01, vm-web-02) and database server VMs (vm-db-01, vm-db-02).

---

## Phase 3 - Load Balancer Configuration

Configured the Azure Load Balancer (ha-web-lb) to distribute traffic across both web servers.

---

## Phase 4 - NAT Gateway Configuration

Deployed and configured the NAT Gateway (ha-web-nat-gateway) to manage outbound internet connectivity for private subnet resources.

---

## Phase 5 - Database Configuration

Installed and configured MySQL on the database VMs and validated connectivity from the web servers.

---

## Phase 6 - Monitoring & Alerts

Configured Azure Monitor, Log Analytics Workspace, and alert rules for CPU spikes and VM health.

---

## Phase 7 - Connectivity & Failover Testing

Validated end-to-end connectivity, load balancer failover, and browser access across both web servers.

---

## Phase 8 - Application Deployment

Deployed the web application and validated full stack operation through the load balancer.

---

## Technologies Used

- Microsoft Azure (Virtual Network, Load Balancer, NAT Gateway, Azure Monitor)
- Ubuntu Linux VMs
- Nginx Web Server
- MySQL Database
- Azure Log Analytics

---

## Author

**Maurrin Carter** - Cloud Engineer
[GitHub](https://github.com/maxmagnac "source-reference")