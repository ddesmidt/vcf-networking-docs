<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> VPC Subnet
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
  "No" for a VPC-Subnet Overlay.  
  Note: VLAN Extension is detailed in a the section below.

* **Access Mode**  
  Select VPC Subnet mode based (Public / Private TGW / Private VPC) on the VM access you need.
  <div style="text-align:center;">
  Click on image below to Zoom in.
  </div>
  [![VPC Subnet](images/1b-2-Create_VPC_Subnet_AccessMode.jpg){ style="width:80%; display:block; margin:0 auto;" }](images/1b-2-Create_VPC_Subnet_AccessMode.jpg)


* **IP Block**  
  Choose "Any", or select a specific IP Block for that VPC Subnet.

* **Auto allocate Subnet CIDR from IP Blocks**  
  "Yes" to let VCF Networking choose the VPC Subnet CIDR,  
  "No" to choose manually the CIDR to use (you can see the "Available Ranges" when clicking on "View IPs..." - not showed in the screenshot).

* **Subnet size**  
  Choose the number of IPs you'll need in that subnet to connect your workloads.  
  Keep in mind, 3 IP will be consumed by the VPC Gateway (subnet IP, default gateway, broadcast IP) + a 4th IP if you enable DHCP Server.

* **VPC Gateway Connectivity**  
  "Yes": The VPC Subnet will be connected to the VPC Gateway and so workloads connected on that VPC Subnet will have access to outside of that VPC Subnet.  
  "No": The VPC Subnet will NOT be connected to the VPC Gateway and so workloads connected on that VPC Subnet will NOT have access outside of that VPC Subnet.  

* **DHCP Config**  
  "None": No DHCP Service.  
  "DHCP Server: VPC Subnet will have a DHCP Server to offer DHCP service to the workloads connected to that VPC Subnet.  
  "DHCP Relay: VPC Gateway will forward DHCP requests for workloads connected to that VPC Subnet to an external DHCP Server. This option is not available if the VPC Gateway is connected to a Distributed Transit Gateway.


### Result - Topology
![vCenter Validation VPC](images/1a-3-Validation_VPC_Gateway.jpg){ width="90%" style="display: block; margin: 0 auto;" }


## Configuration VPC Subnet VLAN-Extension

---
