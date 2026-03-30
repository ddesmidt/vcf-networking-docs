<h1>
  <img src="../../assets/VCFA.png" style="height:30px"; vertical-align:middle;> VCF-A Namespace in VCF-A Tenant
</h1>

<div class="grid" markdown style="grid-template-columns: 80% 20%">

<div markdown>

This section describes the procedures for configuring a VCF-A Namespace by the VCF-A Tenant.
</div>

<div markdown>
![VCFA VPC Connectivity](images/2b-0-Namespace.jpg){ width="100%" }
</div>

</div>

---

## VCF-A Namespaces

Workloads (VMs and Kubernetes Clusters) are deployed in **VCF-A Namespaces**.  
Each VCF-A Namespace has:
* **Scope**: associated with specific **Zones** within a **Region** and linked to a VPC
* **Resource Control**: boundaries for CPU, memory, storage, and network resources for their workloads

![VCFA Namespace](images/2b-0-Namespace.jpg){: .center style="width:80%" }

**VPC Subnet Placement**
VPC Subnets can be provisioned at two different levels depending on the desired scope:

* VCF-A Namespace Level: for dedicated VCF-A Namespace VPC-Subnets
* VPC Gateway Level: for shared VPC-Subnets cross VCF-A Namespaces


**VPC Subnets** can be created in:

* **VCF-A namespaces** (which is associated to a VPC)
* **VPC Gateway**

---

