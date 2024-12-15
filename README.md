# Point-To-Site_Architecture_AZ-104



# Configuring a Point-to-Site (P2S) VPN in Azure

This repository contains a step-by-step guide for setting up a Point-to-Site (P2S) VPN connection in Azure. This configuration enables secure remote access to Azure resources using a VPN client.


---


## **Project Overview**

The objective is to create a P2S VPN connection that allows a remote machine to securely access an Azure virtual machine using its private IP address.


---


## **Steps to Configure Point-to-Site VPN**

### **1. Create a Resource Group**
- **Name**: `Project-5`
- **Location**: Canada Central

### **2. Set Up a Virtual Network (VNet)**
- **VNet Name**: `Vnet-1`
- **Location**: Canada Central
- **Address Space**: `10.0.0.0/16`
- **Subnets**:
  - **Subnet-1**: `10.0.1.0/24`
  - **GatewaySubnet**: `10.0.2.0/24`

### **3. Create a Virtual Machine (VM)**
- **Name**: `VM-1`
- **Location**: Canada Central
- **Public IP Address**: `20.200.125.218`
- **Private IP Address**: `10.0.1.4`
- **OS Image**: Windows Server 2022
- **Subnet Association**: `Subnet-1`

### **4. Create a VPN Gateway**
- **Name**: `VPN-GATEWAY`
- **Location**: Canada Central
- **SKU**: `VpnGw1`
- **Subnet Association**: `GatewaySubnet`

### **5. Configure Point-to-Site VPN**
- **Address Pool**: `192.168.1.0/24`
- **Tunnel Type**: SSTP
- **Client Certificates**:
  - Generate and export the P2S client certificate.
  - Upload the root certificate to the Azure VPN Gateway.

### **6. Download and Configure VPN Client**
- Download the VPN client configuration from the Azure VPN Gateway.
- Import the configuration to the remote machine.

### **7. Connect to Azure VPN**
- Use the VPN client to establish a connection to the Azure VPN.

### **8. Connect to Azure VM**
- Connect to `VM-1` using its private IP address `10.0.1.4` from the remote machine.

---

## **Benefits of Using Point-to-Site (P2S) VPN**

1. **Secure Remote Access**: Encrypts data to ensure secure communication.
2. **No Dedicated Hardware Required**: Eliminates the need for on-premises VPN devices.
3. **Cost-Effective**: Pay-as-you-go pricing.
4. **Scalable**: Supports multiple simultaneous connections.
5. **Flexible Authentication**: Supports certificates and Azure Active Directory.
6. **Seamless Access to Azure Resources**: Enables access to private Azure resources.
7. **Multi-Platform Support**: Works with Windows, macOS, and Linux.

---

## **Usage**

1. Clone this repository for reference.
2. Follow the steps outlined in the guide to configure your P2S VPN setup.

---

## **Contributing**

Contributions are welcome! Please create a pull request with your updates or suggestions.

---

## **Contact**

For questions or feedback, please open an issue in this repository.
