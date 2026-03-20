<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> Connectivity Policy in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 70% 30%">

<div markdown>
This section describes the procedures for configuring Connectivity Policy using the vSphere Client.  
</div>


<div markdown>
![vCenter Conn Policy](images/3f-0-Conn_Policy.jpg){ width="100%" }
</div>

</div>

---

## Overview of Connectivity Policy Types

| Type | Use Case | Routing Logic |
| :--- | :--- | :--- |
| [**Community**](#community) | Permits communication between VPCs within the same defined group. Ideal for application-tier connectivity within a specific division. | VPCs can communicate with other **Community** peers in their group and all **Promiscuous** VPCs. |
| [**Isolated**](#isolated)| Strictly blocks communication to all other VPCs. Best for highly sensitive or standalone application workloads. | VPCs are restricted to communicating only with **Promiscuous** VPCs (Shared Services). |
| [**Promiscuous**](#promiscuous)| Provides universal connectivity across the environment. Ideal for shared  services (e.g., Backup, DNS, NTP). | VPCs have unrestricted communication with **all** other VPCs in the environment. |

![vCenter Conn Policy Types](images/3f-0-Conn_Policy_Types.jpg){: .center style="width:80%" }

---

## Connectivity Policy

### Configuration

#### Step1. Create Connectivity Policy
![vCenter Conn Policy config](images/3f-1a-Create_ConnPolicy.jpg){ width="100%" style="display: block; margin: 0 auto;" }

* **Visibility**:  
  Set to External.

* **CIDRs/Ranges**:  
  Enter the specific CIDR blocks or IP ranges to be managed by this block.  

  
* **Excluded IP Ranges**:  
  (Optional) Specify any IP Range(s) within the CIDRs above that should be withheld from automatic allocation (e.g. IP Range used by the physical network).
  
* **Reserved for Specific Subnet**:  
  Enable for the Subnet-VLAN use case, otherwise disabled.

### Monitoring

#### Other VPCs with connectivity with yours

![vCenter Conn Policy validation](images/3f-1b-Validation_ConnPolicy_Members.jpg){ width="80%" style="display: block; margin: 0 auto;" }

#### VPCs who belong to no Community

![vCenter Conn Policy validation](images/3f-1b-Validation_VPC_NoConnPolicy.jpg){ width="80%" style="display: block; margin: 0 auto;" }

---
