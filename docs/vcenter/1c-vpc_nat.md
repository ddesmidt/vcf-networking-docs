<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> VPC NAT Configuration in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 85% 15%">

<div markdown>

This section describes the procedures for configuring Network Address Translation (NAT) for your VPC workloads in private subnets.<br><br>
NAT allows private subnets to communicate with external networks or provides a way for external users to reach private VPC workloads.
</div>


<div markdown>
![vCenter VPC Connectivity](images/1c-0-VPC_NAT.jpg){ width="100%" }
</div>

</div>

---

## Overview of NAT Types

| Type | Use Case |
| :--- | :--- |
| **External-IP (1:1 NAT)** | Allows communication between Workloads on Private VPC and Private TGW subnets and external networks. |
| **Outbound-NAT (N:1 NAT)** | Allows communication from Destination NAT: Workloads on Private VPC and Private TGW subnets and external networks. |
| **NAT (SNAT/DNAT)** | Stateful Layer4 NAT for flexible communication between Workloads on Private VPC and Private TGW subnets and external networks.  |
<div style="text-align:center;">
Click on image below to Zoom in.
</div>
[![VPC Subnet](images/1c-0-VPC_NAT_types.jpg){ style="width:80%; display:block; margin:0 auto;" }](images/1c-0-VPC_NAT_types.jpg)

---

## Configuration External-IP (1:1 NAT)

### 1. Create new VPC Subnet (Overlay)
![vCenter Create VPC](images/1b-1-Create_VPC_Subnet.jpg){ width="70%" style="display: block; margin: 0 auto;" }


## Configuration Outbound-IP (N:1 NAT)

### 1. Create new VPC Subnet (Overlay)
![vCenter Create VPC](images/1b-1-Create_VPC_Subnet.jpg){ width="70%" style="display: block; margin: 0 auto;" }


## Configuration NAT (SNAT/DNAT)

### 1. Create new VPC Subnet (Overlay)
![vCenter Create VPC](images/1b-1-Create_VPC_Subnet.jpg){ width="70%" style="display: block; margin: 0 auto;" }




---

