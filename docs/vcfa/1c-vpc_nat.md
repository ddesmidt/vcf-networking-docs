# NAT Configuration in vCenter

Use this section to configure Network Address Translation (NAT) for your VPC workloads. NAT allows private subnets to communicate with external networks or provides a way for external users to reach internal services.

## Overview of NAT Types

| Type | Use Case |
| :--- | :--- |
| **SNAT** | Source NAT: Allows VMs on private subnets to reach the Internet. |
| **DNAT** | Destination NAT: Allows external users to reach a specific VM (e.g., a Web Server). |
| **Reflexive** | Stateless NAT: One-to-one mapping between a private and public IP. |

---

## Configuration Steps

Choose your preferred method for configuring NAT rules.

=== "vCenter UI"

    1. Log in to **vCenter Server**.
    2. Navigate to **Inventory > Networking**.
    3. Select your **VPC** from the list.
    4. Click the **Configure** tab and select **Network Services > NAT**.
    5. Click **Add Rule** and fill in the details:
        * **Name:** `Production-SNAT`
        * **Type:** `SNAT`
        * **External IP:** Select an IP from your public block.

=== "PowerVCF / CLI"

    To automate NAT creation, use the following API call structure:

    ```bash
    POST /api/v1/vpc/nat-rules
    {
        "display_name": "Production-SNAT",
        "action": "SNAT",
        "translated_network": "192.168.1.0/24",
        "public_ip": "10.0.0.50"
    }
    ```

---

!!! warning "Routing Dependency"
    Before NAT will function, ensure your **Tier-0