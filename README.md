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
4. [Tools Used](#tools-used)
5. [Useful Links](#useful-links)
6. [License](#license)
7. [Contributions](#contributions)

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
   - Connected to the VM using its public IP and validated the SSH connection.

---

## Screenshots

Below are the screenshots that illustrate the configurations:

1. **Virtual Network Configuration**  
   ![VNet Configuration](images/vnet_config.png)  
   *Configuration of the Virtual Network, including address spaces and subnets.*

2. **Subnet Configuration**  
   ![Subnet Configuration](images/subnet_config.png)  
   *Details of the configured subnets in the Virtual Network.*

3. **Virtual Machine Configuration**  
   ![VM Configuration](images/vm_config.png)  
   *Configuration details of the Ubuntu VM.*

4. **SSH Connection**  
   ![SSH Connection](images/ssh_connection.png)  
   *Successful SSH connection to the Ubuntu VM.*


---

## Tools Used

- **Azure Portal:** For creating and managing the Virtual Network and Virtual Machine.  
- **SSH:** For connecting to the Ubuntu VM.  
- **Azure CLI:** For managing Azure resources via the command line.  

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
