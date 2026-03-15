<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> VNA Configuration in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 85% 15%">

<div markdown>

This section describes the procedures for configuring NSX Virtual Network Appliances (VNA) using the vSphere Client.  

NSX Virtual Network Appliances (VNA) providing centralized network services for Distributed Transit Gateway Designs.
</div>


<div markdown>
![vCenter VNA](images/2b-0-VNA.jpg){ width="100%" }
</div>

</div>

---

xxx take the screenshots

## Configuration VNA Cluster / VNA Nodes

### 1. Create new VNA Cluster / VNA Nodes
![vCenter VNA Cluster](images/2a-1-Create_Edge.jpg){ width="80%" style="display: block; margin: 0 auto;" }

### 2. Configure VNA Cluster Identity
![vCenter VNA Cluster](images/2a-2-Create_Edge.jpg){ width="50%" style="display: block; margin: 0 auto;" }

* **Node Form Factor**:  
  Select the appliance size (vCPU / Memory) of the VNA Nodes.  
  This determines the scale and performance limits for the logical routers (VNA Gateways) hosted on the node.

### 3. Configure VNA Nodes Placement and Networking
![vCenter VNA Node](images/2a-3a-Configure_EdgeNode1.jpg){ width="80%" style="display: block; margin: 0 auto;" }

* **vSphere Cluster / Resource Pool / Host Group Affinity / Data Store**:  
  Defines the physical placement of the Edge Node VM.  
  You can optionally specify Resource Pools and Host Group Affinity to control where the VM resides within the cluster.  

* **Management Network Settings (IP Address Type / IP Assignment / Port Group)**  
  Configures the IP assignment and Port Group for the VNA Node management interface.


**Repeat these steps for the remaining VNA Nodes (2+ nodes recommended).**

<div style="margin-left: 40px; margin-right: 40px;" markdown="1">
??? info "Cloning option"
    In case other Edge Nodes have the vSphere Cluster and Uplink settings, use the cloning option.
    ![Add Edge Node2](images/2a-3c-Configure_EdgeNode2.jpg){ width="50%" style="display: block; margin: 0 auto;" }
</div>


### 4. Result - Status of VNA Cluster / VNA Nodes deployment
![vCenter VNA Status](images/2a-4-Validation_Edge.jpg){ width="90%" style="display: block; margin: 0 auto;" }

---
