<h1>
  <img src="../../assets/vCenter.png" style="height:30px"; vertical-align:middle;> Network Span in vCenter
</h1>

<div class="grid" markdown style="grid-template-columns: 20% 80%">

<div markdown>
This section describes the procedures for configuring Network Span using the vSphere Client.  
</div>


<div markdown>
![vCenter Network Span](images/3d-0-Network_Span.jpg){ width="100%" }
</div>

</div>

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
