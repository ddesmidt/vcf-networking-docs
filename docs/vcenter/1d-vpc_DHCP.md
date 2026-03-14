<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> VPC DHCP Configuration in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 85% 15%">

<div markdown>

This section describes the procedures for configuring Dynamic Host Configuration Protocol (DHCP) for your VPC workloads in VPC subnets.<br><br>
DHCP is used to dynamically assign IP addresses to workloads.
</div>


<div markdown>
![vCenter VPC Connectivity](images/1d-0-VPC_DHCP.jpg){ width="100%" }
</div>

</div>

---

## Overview of DHCP Types

| Type | Use Case | Routing Logic |
| :--- | :--- | :--- |
| [**DHCP Server**](#dhcp-server) | DHCP services provided natively by the VPC Gateway. | Workload IP addressing is managed directly within the VCF networking stack. |
| [**DHCP Relay**](#dhcp-relay)| DHCP requests are forwarded to an external IPAM solution (e.g., Infoblox). | Workload IP addressing is managed by an external third-party service provider. |

![VPC NAT](images/1c-0-VPC_NAT_types.jpg){: .center style="width:90%" }

---

## DHCP Server Configuration {: #dhcp-server }

### 1. Edit VPC subnet and enable DHCP Server
![vCenter Create External IP](images/1c-1a-Create_VPC_NAT_ExtIP.jpg){ width="70%" style="display: block; margin: 0 auto;" }

Talk about:
. Reserved IP Ranges
. Classless Static Routes
. Generic DHCP Options
. Static Bindings 


Talk about where is configured the DHCP Server settings (DNS, etc).


### 2. Result - Validate DHCP Server configuration
![vCenter Result VPC Subnet](images/1c-1b-Validation_VPC_NAT_ExtIP.jpg){ width="90%" style="display: block; margin: 0 auto;" }

Talk if possible to see the DHCP leases.

---

## DHCP Relay Configuration {: #dhcp-relay }
!!! warning "Limitation"
    DHCP Relay is supported exclusively on **VPC Public Subnets**.

### 1. Edit VPC subnet and enable DHCP Relay
![vCenter Create External IP](images/1c-1a-Create_VPC_NAT_ExtIP.jpg){ width="70%" style="display: block; margin: 0 auto;" }

Talk about where is configured the DHCP Relay settings.

### 2. Result - Validate DHCP Server configuration
![vCenter Result VPC Subnet](images/1c-1b-Validation_VPC_NAT_ExtIP.jpg){ width="90%" style="display: block; margin: 0 auto;" }


---

