<h1>
  <img src="/assets/vCenter.png" style="height:30px"; vertical-align:middle;> VPC Subnet
</h1>

<div class="grid" markdown style="grid-template-columns: 85% 15%">

<div markdown>

This section describes the procedures for configuring a VPC Subnet using the vSphere Client.
</div>


<div markdown>
![vCenter VPC Connectivity](images/1b-0-VPC_Subnet.jpg){ width="100%" }
</div>

</div>

---

## Configuration VPC Subnet Overlay

### 1. Create new VPC Subnet (Overlay)
![vCenter Create VPC](images/1b-1-Create_VPC_Subnet.jpg){ width="70%" style="display: block; margin: 0 auto;" }

### 2. Choose the VPC Subnet name (+ VLAN option + Subnet mode + IP Block & Size + Connectivity + DHCP)
![vCenter Create VPC](images/1b-2-Create_VPC_Subnet.jpg){ width="90%" style="display: block; margin: 0 auto;" }

* **VLAN Extensions**:  
  Disabled for the VPC-Subnet Overlay.
* **Access Mode**  
  Select VPC Subnet mode based (Public / Private TGW / Private VPC) on the VM access you need.
  ![VPC Subnet](images/1b-2-Create_VPC_Subnet_AccessMode.jpg){ style="width:80%; display:block; margin:0 auto;" }


[![VPC Subnet](images/1b-2-Create_VPC_Subnet_AccessMode.jpg){ style="width:80%; display:block; margin:0 auto;" }](images/1b-2-Create_VPC_Subnet_AccessMode.jpg)


* **Connectivity Policy**  
  Select the Connectivity Policy (Policy for cross-VPC communication).
  That's to allow/deny communication to other VPC subnets.

### Result - Topology
![vCenter Validation VPC](images/1a-3-Validation_VPC_Router.jpg){ width="90%" style="display: block; margin: 0 auto;" }


## Configuration VPC Subnet VLAN-Extension

[![VPC Subnet - Access Mode](images/1b-2-Create_VPC_Subnet_AccessMode.jpg){ style="width:80%; display:block; margin:0 auto;" }](images/1b-2-Create_VPC_Subnet_AccessMode.jpg)

---
