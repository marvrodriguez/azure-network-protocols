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

- Windows 10 (22H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

<details>
<summary>
  
#### Installing Resources in Azure (Virtual Machines)
</summary>

First we need to create a resource group where we will install the 2 Virtual Machines, one running on  Windows 10 Pro (22H2) and the second one running on Ubuntu Server 20.04
To create the resource group named "RG-LAB-02" on your azure home page you can type on the search bar, or if you've previously accessed it, an icon will be on your home page.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/07ac41e2-e369-4eea-b988-ecd1d762c1bb) ![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/4fb7f95a-522e-43f4-8349-5ec735165636)

Once on the resource group page, enter the name for the resource group "RG-LAB-02" for the region I chose to use (US) WEST US 3, then click review and create.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/b155f3db-7dfc-4790-b2d2-261997a60a25)

Install Windows 10 Pro (22H2) named "VM1", to create a virtual machine, type in the search bar for virtual machine.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/0752be1b-6f3c-48d8-858a-c5ede44866bd)

At this point you can click create to start the process.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/837b12f2-bc10-484a-9d30-d48eb2edf91c)

Creating the first Virtual Machine which will be Windows 10 Pro version 22H2, for the resource group just pick the one we created which is RG-LAB-O2, virtual machine name is VM1, pick the same region you did for the resource group and for the image this is where to pick Windows 10 Pro version 22H2.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/feb15e60-d3b7-452e-acd8-d561121ae67e)

For the Size pick Standard_E2s_v3-2 vcpus, 16 Gib memory, take note of the username and password you'll create as these will be needed to login to the VM when we remote desktop to it, once all of that is filled on the bottom check the Licensing then click  Review+Create to continue.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/e03e1069-259a-407d-99d9-1652fda57f74)



</details>

<h2>Actions and Observations</h2>

