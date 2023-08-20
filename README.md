<p align="center">
  <img src="https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/94a4f6b4-2beb-4108-94c0-33f01f0de76f"height="70%" width="70%"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

<details>
<summary>
  
#### Installing Resources in Azure (Virtual Machines)
</summary>

First we need to create a resource group where we will install the 2 Virtual Machines, one running on  Windows 10 Pro and the second one running on Ubuntu Server 20.04
To create the resource group named "RG-LAB2" on your azure home page you can type on the search bar, or if you've previously accessed it, an icon will be on your home page

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/07ac41e2-e369-4eea-b988-ecd1d762c1bb) ![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/4fb7f95a-522e-43f4-8349-5ec735165636)


</details>

<h2>Actions and Observations</h2>

