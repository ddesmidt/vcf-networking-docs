<h1>
  <img src="../assets/VCFA.png" style="height:30px"; vertical-align:middle;>
  VCF Automation Network Services
</h1>

This section provides technical procedures for configuring and managing network services via the **VCF Automation**.  

---

## VCF-A Tenant
Explore the configuration guides for Tenant-Level Networking:

<div class="grid" markdown style="grid-template-columns: 25% 75%">

<div markdown>
![VCFA VPC Network Services.](images/VCFA-Tenant.jpg){ width="100%" }
</div>

<div markdown>
<div style="height:20px;"></div>

### External Connectivity & Services
* :material-transit-connection: [__Transit Gateway__](1a-transit_gateway.md)  
  Logical router connecting VPC Gateways to physical networks.
* :material-transit-connection: [__Connectivity Profile__](1b-connectivity_profile.md)  
  Defines the VPC's connection to the Region, Transit Gateway, specifies the assigned External and Private-TGW IP blocks, and determines if Outbound-SNAT is enabled.  
  Not represented in the diagram.
* :material-camera-control: ~~__Connectivity Policy__~~  
  Defines cross-VPC communication rules.  
  Not represented in the diagram.  
  Configuration not available from VCF Automation (available from vCenter or NSX).  
* :material-chart-donut: [__IP Quota Tenant__](1d-ip_quota_tenant.md)  
  IP Quota to limit the usage of External/Public IP addresses by VPCs.  
  Not represented in the diagram.

### Network Services
* :material-router: [**VPC Gateway**](2a-vpc_gateway.md)  
  Logical router.
* :material-lan: [**VPC Subnet**](2b-vpc_subnet.md)  
  Logical Subnet (for VMs/K8s connection).  
  Option to also create Subnet-VLAN.
* :material-swap-horizontal: [**NAT**](2c-vpc_nat.md)  
  External-IP (1:1 NAT)  
  or Outbound-NAT (N:1 SNAT)  
  or NAT (SNAT/DNAT)
* :material-ip-network-outline: [**DHCP**](2d-vpc_DHCP.md)  
  DHCP Server (managed by VCF)  
  or DHCP Relay (managed by 3rd party DHCP Server like Infoblox)
* :material-arrow-split-vertical: [**Load Balancer**](2e-vpc_lb.md)  
  xxx.
* :octicons-lock-16: [**VPN**](2f-vpc_vpn.md)  
  Secure Site-to-Site connectivity.
</div>

</div>
---

## VCF-A Provider
xxx Add section to talk about "Design / Educate" how customers choose between all those options.  
:material-vector-polyline-plus: xxx Add how to do the use case "Internet / DC1" ???  
:material-vector-polyline-plus: ??? How to talk about "Internet / DC1" ???  
xxx talk about Infoblox???

Explore the configuration guides for Provider-Level Networking:

<div class="grid" markdown style="grid-template-columns: 25% 75%; gap: 10px;">

<div markdown>
![VCFA VPC Connectivity](images/VCFA-Provider.jpg){ width="100%" }
</div>

<div markdown>
<div style="height:20px;"></div>

### Provider Infrastructure
* :material-layers-outline: [__Edge Cluster / Edge Node__](3a-edge.md)  
  NSX Edge appliances providing centralized network services for Central Transit Gateway Designs.
* :material-layers-outline: [__VNA Cluster / VNA Node__](3b-vna.md)  
  NSX Virtual Network appliances providing centralized network services for Distributed Transit Gateway Designs.
* :material-router: ~~__Tier-0 / BGP__~~  
  Tier-0 logical router providing connectivity between Centralized Transit Gateways and the physical network.  
  Configuration not available from VCF Automation (available from NSX).  

### External Connectivity & Services
* :fontawesome-solid-external-link: [__External Connection__](4a-external_connection.md)  
  Connection between the VPC environment and the physical network.
* :material-lan-connect: [__Subnet-VLAN__](4b-vpc_subnet_vlan.md)  
  VLAN-backed VPC subnets.
* :material-code-block-brackets: [__IP Blocks External (Infoblox) + TGW Priv.__](4c-ip_block.md)  
  IP blocks used for VPC subnet allocation.  
  Not represented in the diagram.
* :material-chart-donut: [__Provider IP Quota__](4d-ip_quota_provider.md)  
  IP Quota to limit the usage of External/Public IP addresses by Tenants.  
  Not represented in the diagram.
* :material-table-split-cell: ~~__Network Span__~~  
  Defines how VPC subnets span across vCenter clusters.  
  Not represented in the diagram.  
  Configuration not available from VCF Automation (available from vCenter or NSX).  
  VCF-Regions and Zones can be used for this use case.
</div>

</div>



---

!!! info "Document Versioning"
    This guide is updated for **VCF 9.1+**.  
    If you are running an older version, some options may not be available.

---