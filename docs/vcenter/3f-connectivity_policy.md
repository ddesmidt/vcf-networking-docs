<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> Connectivity Policy in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 65% 35%">

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

![Ext Connectivity Types](images/3f-0-Conn_Policy_Types.jpg){: .center style="width:80%" }

---

## Network Span

### Configuration

#### Step1. Create Network Span
![vCenter Network Span config](images/3c-1a-Create_IPBlock_Ext.jpg){ width="100%" style="display: block; margin: 0 auto;" }

* **Visibility**:  
  Set to External.

* **CIDRs/Ranges**:  
  Enter the specific CIDR blocks or IP ranges to be managed by this block.
  
* **Excluded IP Ranges**:  
  (Optional) Specify any IP Range(s) within the CIDRs above that should be withheld from automatic allocation (e.g. IP Range used by the physical network).
  
* **Reserved for Specific Subnet**:  
  Enable for the Subnet-VLAN use case, otherwise disabled.

### Monitoring
The status reflects the successful application of the configuration.

!!! info "Note"
    Because this represents a logical configuration mapping rather than an active link-state protocol, the status will typically remain Green (Healthy) once the settings are validated by the NSX Manager.

![IP Block Ext validation](images/3c-1b-Validation_IPBlock_Ext.jpg){ width="80%" style="display: block; margin: 0 auto;" }


---
