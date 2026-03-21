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

Network Span defines how VPC subnets span across vCenter clusters.

### Configuration

#### Step1. Create Network Span
![vCenter Network Span config](images/3d-1a-Create_Network_Span.jpg){ width="95%" style="display: block; margin: 0 auto;" }


### Monitoring

#### Status
The status reflects the successful application of the configuration.

!!! info "Note"
    Because this represents a logical configuration mapping rather than an active link-state protocol, the status will typically remain Green (Healthy) once the settings are validated by the NSX Manager.

![vCenter Network Span validation](images/3d-1b-Validation_Network_Span.jpg){ width="95%" style="display: block; margin: 0 auto;" }


---
