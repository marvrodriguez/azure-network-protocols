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

- Creating Resources
- Installing Wireshark
- Observing Different Network Protocols
<h2>Actions and Observations</h2>
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

As soon as the Virtual Machine is being created we can go back to the home page and get to creating our second Virtual Machine. The Resource group will be the same RG-LAB-02 and for the Virtual name VM2, the region will be the same as the previous one and for the image pick Ubuntu Server20.04.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/3902c53c-781b-4d8c-9711-183a738d8dcf)

For the size pick the same one as the previous virtual machine, for the  authentication type instead of SSH public key choose password and fill in the credentials and take note of them, then review+create.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/43f205bd-bb1b-4ed8-8b0f-c9ff1421b8db)

</details>

<details>

<summary>
  
   #### Install Wireshark
</summary>
We need to install Wireshark a network protocol analyzer application in our VM1 or Widnows 10 Pro Virtual machine. In order to do that we need to remote desktop into VM1 on your local machine, search for Renmote desktop connection.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/9931ed1e-0dcc-4003-9de9-ac9a9f815668)

To remote in to VM1 head back to the Virtual Machine page on Azure and click VM1 and look for its Public IP address. From there copy and paste the Public IP address and paste it in the Remote desktop application, once you do that, enter the credentials when VM1 was created.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/1682abf6-7351-47d8-81cc-69b4957747eb)

Once logged in, go to google and Download  and install Wireshark and keep the default settings.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/ee7cbc9e-da8a-4357-86d1-9cf8be40affc)

After finishing the installation of wireshark open the application and click on the small fin icon to start capturing packets.

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/63c2d9c4-1aca-415e-b158-13c5b768f772)

![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/9dfe6c51-8906-4ac8-a941-075ef9ed2f48)

</details>

<details>

  <summary>
    
   #### Observing Different Network Protocols
    
  </summary>
  
  Now that we've installed wireshark on VM1 we can start to observe different network protocols, first we can filter for `icmp` and ping VM2 and observe the following. 
  
  ![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/faa3be3e-b69a-4d79-88f1-94b4b15c95ee)

  For us to be able to poing VM2 we need to get its Private IP address which we can get on the azure page for VM2.

  ![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/f3b9626e-001f-4353-884f-594e2917eeac)

 Once you have VM2's Private IP address head back to VM1 and open either powershell/command prompt and type in ping 10.0.0.5 (type in the private IP address)

 ![image](https://github.com/marvrodriguez/azure-network-protocols/assets/141983161/029fbada-7ca5-4ab3-80df-a8094f795232)

</details>



