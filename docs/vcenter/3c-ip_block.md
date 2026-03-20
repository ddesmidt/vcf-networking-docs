<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> IP Blocks in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 60% 40%">

<div markdown>
This section describes the procedures for configuring IP Blocks using the vSphere Client.  
</div>


<div markdown>
![vCenter IP Blocks](images/3c-0-IP_Block.jpg){ width="100%" }
</div>

</div>

---

## Overview of IP Block Types

| Type | Use Case | Routing Logic |
| :--- | :--- | :--- |
| [**External**](#ext-ipblock) | Used for **VPC Subnets Public**. | External visibility is high; direct ingress/egress. |
| [**Private-TGW**](#privatetgw-ipblock)| Used for **VPC Subnets Private-TGW** | Best for shared internal services across the enterprise. |
| [**Private-VPC**](#privatevpc-ipblock)| **VPC Subnets Private-VPC**. <br> Note: Configuration in within the [VPC Gateway](1a-vpc_gateway.md). | Maximum isolation; workloads are "hidden" even from other VPCs. |

![vCenter IP Blocks Types](images/3c-0-IP_Block-Types.jpg){: .center style="width:75%" }

For more information on VPC Subnets, refer to the [VPC Subnet](1b-vpc_subnet.md) page.

---
## IP Block External {: #ext-ipblock }

This IP Block type is used for Public VPC Subnets and VLAN-backed Subnets.

* **Public VPC Subnets**: These IP Blocks must be manually defined in this section (see configuration steps below).
* **VLAN-backed Subnets**: These IP Blocks are not created here; they are configured directly within the [VPC Subnet VLAN Extension](1b-vpc_subnet.md#vlan)

### Configuration

#### Step1. Create new IP Block External
![IP Block Ext config](images/3c-1a-Create_IPBlock_Ext.jpg){ width="100%" style="display: block; margin: 0 auto;" }

* **Visibility**:  
  Set to External.

* **CIDRs/Ranges**:  
  Enter the specific CIDR(s) or IP Range(s) to be managed by this block.  
  Note the following requirements based on the intended use case:  
    . CIDR: Must be used if this block will be used for VPC-Subnet Publics  
    . Range: May be used if the block is intended only for NAT, LB-VIP, or VPN services
  
* **Excluded IP Ranges**:  
  (Optional) Specify any IP Range(s) within the CIDRs above that should be withheld from automatic allocation (e.g. IP Range used by the physical network).
  
* **Reserved for Specific Subnet**:  
  This setting is used exclusively for VLAN-backed Subnets.  
  For the creation of VPC-Subnet Public this option must be left Disabled.  
  Note: IP Blocks for VLAN-backed Subnets are created directly within the [VPC Subnet VLAN Extension](1b-vpc_subnet.md#vlan).  
  

### Monitoring
The status reflects the successful application of the configuration.

!!! info "Note"
    Because this represents a logical configuration mapping rather than an active link-state protocol, the status will typically remain Green (Healthy) once the settings are validated by the NSX Manager.

![IP Block Ext validation](images/3c-1b-Validation_IPBlock_Ext.jpg){ width="80%" style="display: block; margin: 0 auto;" }

---

## IP Block Private-TGW {: #privatetgw-ipblock }

### Configuration

This is the IP Block used for future VPC Subnets Private-TGW.

#### Step1. Create new IP Block Private-TGW
![IP Block Ext config](images/3c-2a-Create_IPBlock_Private_TGW.jpg){ width="100%" style="display: block; margin: 0 auto;" }

* **Visibility**:  
  Set to Private.

* **CIDRs/Ranges**:  
  Enter the specific CIDR block(s) to be managed by this block.  
  Do not use Range.
  
* **Excluded IP Ranges**:  
  (Optional) Specify any IP Range(s) within the CIDRs above that should be withheld from automatic allocation (e.g. IP Range used by the physical network).
  
* **Reserved for Specific Subnet**:  
  Not Applicable.

### Monitoring

#### Status
The status reflects the successful application of the configuration.

!!! info "Note"
    Because this represents a logical configuration mapping rather than an active link-state protocol, the status will typically remain Green (Healthy) once the settings are validated by the NSX Manager.

![IP Block Ext validation](images/3c-2b-Validation_IPBlock_Private_TGW.jpg){ width="80%" style="display: block; margin: 0 auto;" }

---

## IP Block Private-VPC {: #privatevpc-ipblock }

### Configuration

This is the IP Block used for future VPC Subnets Private-VPC.  
It's configuration is managed directly within the [VPC Gateway](1a-vpc_gateway.md) settings.

---

## Monitoring IP Blocks

#### Utilization
Real-time utilization metrics for IP Blocks can be monitored via the following indicators:

* **Available IPs**: The remaining number of addresses in the pool ready for allocation.

* **Used IPs**: The number of addresses currently assigned to active VPC subnets. For External IP Blocks, this also includes addresses consumed by NAT and Load Balancer Virtual VIPs.

![IP Block Statistics](images/3c-4-Statistics_IPBlock.jpg){ width="95%" style="display: block; margin: 0 auto;" }


---
