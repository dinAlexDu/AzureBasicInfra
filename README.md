# Azure Basic Infrastructure Project
---
**A Hands-on Lab for Creating Basic Infrastructure in Azure**
---

This project demonstrates the creation of a basic infrastructure in Azure, which includes a Virtual Network (VNet) with subnets and a Virtual Machine (VM) running Ubuntu Server 20.04.

---

## Table of Contents
1. [Project Objectives](#project-objectives)
2. [Steps Implemented](#steps-implemented)
3. [Screenshots](#screenshots)
4. [Test SSH Connectivity](#test-ssh-connectivity)
5. [Troubleshooting](#troubleshooting)
6. [Tools Used](#tools-used)
7. [Useful Links](#useful-links)
8. [License](#license)
9. [Contributions](#contributions)


---

## Project Objectives

- **Set up a Virtual Network (VNet):**  
  Configure a Virtual Network with custom address spaces and subnets.

- **Deploy a Virtual Machine:**  
  Create an Ubuntu VM with SSH authentication for remote access.

- **Establish Network Connectivity:**  
  Ensure secure access to the VM using SSH over port 22.

---

## Steps Implemented

1. **Create a Virtual Network (VNet)**  
   - **Address Space:** `10.0.0.0/16`  
   - **Subnets:**  
     - `default` - `10.0.0.0/24`  
     - `BasicSubnet` - `10.0.1.0/24`  

2. **Deploy a Virtual Machine (VM)**  
   - **Name:** `UbuntuVM`  
   - **Image:** Ubuntu Server 20.04 LTS  
   - **Size:** B1s (free tier)  
   - **Authentication:** SSH Key  

3. **Test SSH Connectivity**  
   - **Connect to the Virtual Machine:**  
     Use the following command to connect to the VM via SSH:
     ```bash
     ssh ubuntuadmin@<PUBLIC_IP>
     ```
     Replace `<PUBLIC_IP>` with the public IP address of the deployed VM.

   - **Verify Connectivity:**  
     Once connected, run the following command to verify the VM is operational:
     ```bash
     uptime
     ```
     This will display the system uptime, confirming the VM is running.

   - **Check Network Configuration:**  
     Use the `ifconfig` or `ip addr` command to inspect the network configuration:
     ```bash
     ip addr
     ```
     Ensure the expected private IP address from the VNet is assigned to the VM.


---

## Screenshots

Below are the screenshots that illustrate the configurations:

1. **Virtual Network Configuration**  
   ![VNet Configuration](images/vnet_config.png)  
   *This screenshot shows the configuration of the Virtual Network, including the address space and subnet settings.*

2. **Subnet Configuration**  
   ![Subnet Configuration](images/subnet_config.png)  
   *Details of the subnets created within the Virtual Network, highlighting their respective address ranges.*

3. **Virtual Machine Configuration**  
   ![VM Configuration](images/vm_config.png)  
   *This screenshot provides an overview of the VM's settings, including the selected image, size, and authentication method.*

4. **SSH Connection**  
   ![SSH Connection](images/ssh_connection.png)  
   *A successful SSH connection to the Ubuntu VM, showcasing remote access through the public IP and key authentication.*


---

## Tools Used

- **Azure Portal:** For creating and managing the Virtual Network and Virtual Machine.  
- **SSH:** For connecting to the Ubuntu VM.  
- **Azure CLI:** For managing Azure resources via the command line.  

---

## Troubleshooting

Below are common issues encountered during the lab and their resolutions:

### Public IP Not Accessible
- **Issue:** Unable to SSH into the VM using its public IP.  
- **Resolution:**  
  1. Verify that the NSG (Network Security Group) associated with the VM has an inbound rule allowing SSH (Port 22).  
  2. Ensure the VM is assigned a public IP address in the Azure Portal.

### SSH Key Authentication Fails
- **Issue:** The SSH key is not recognized during connection.  
- **Resolution:**  
  1. Check that the correct private key is being used with the `ssh` command.  
  2. Verify that the public key was correctly added during the VM creation.

### VM Is Not Accessible
- **Issue:** The VM cannot be reached even with the correct public IP and port.  
- **Resolution:**  
  1. Ensure the VM is in a running state in the Azure Portal.  
  2. Check the Azure subscription quota for public IPs or virtual machines.  
  3. Verify the VNet and Subnet configurations to ensure proper routing.

### Slow SSH Connection
- **Issue:** SSH takes a long time to connect.  
- **Resolution:**  
  Disable DNS resolution in the SSH configuration by adding `UseDNS no` in the `/etc/ssh/sshd_config` file on the VM.

If additional issues are encountered, refer to the official [Azure Troubleshooting Guide](https://learn.microsoft.com/en-us/azure/troubleshoot/overview).

---

## Useful Links

- [Azure Virtual Network Documentation](https://learn.microsoft.com/en-us/azure/virtual-network/)  
  Comprehensive guide to configuring VNets in Azure.

- [Azure Virtual Machine Documentation](https://learn.microsoft.com/en-us/azure/virtual-machines/)  
  Official documentation for deploying and managing Azure VMs.

- [SSH Basics](https://www.ssh.com/academy/ssh)  
  A beginner's guide to secure remote access using SSH.

---

## License

This project is licensed under the [MIT License](./LICENSE).  
See the LICENSE file for detailed terms and conditions.

---

## Contributions

Contributions are welcome!  
If you have suggestions for improvements or additional use cases, feel free to [fork this repository](https://github.com/dinAlexDu/AzureBasicInfra) and submit a pull request.  

Please adhere to our [Code of Conduct](./CODE_OF_CONDUCT.md) when contributing to this project.
