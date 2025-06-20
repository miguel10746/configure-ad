<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)


<h2>Deployment and Configuration Steps</h2>

![image](https://github.com/user-attachments/assets/5cf4c097-a4b5-47c8-9745-5f3b8280ab39)
<p>
I created two VM through Azure. One had Windows Server 2022 and the other one was running Windows 10.
</p>

![image](https://github.com/user-attachments/assets/2803ab42-6735-485d-be5b-4c5e1d3caeae)
<p>
I set up a new forest name mydomain.com.
</p>

![image](https://github.com/user-attachments/assets/fb5d91a6-3938-4ddc-a78e-12202fb6bd13)
<p>
I active Active Directory Domain Services, to provide identity and access management in my new create windows domain network.
</p>

![image](https://github.com/user-attachments/assets/5d3dbffe-df65-4d32-927a-574033779be7)
<p>
Once it has been set up, the system need to restart.
</p>


![image](https://github.com/user-attachments/assets/00f3c3a9-1824-4caf-963f-4306e6c14ab6)
![image](https://github.com/user-attachments/assets/deea973f-dec9-49f4-99be-72edf645e158)
<p>
In this step, I set my Windows Server VM NIC to static IP address. Once that was set in Azure. I went into the second VM to sent the DNS server to the IP address of my Windows Server VM.
</p>

![image](https://github.com/user-attachments/assets/4d140808-7ff7-4a51-95a3-e225258a256e)
![image](https://github.com/user-attachments/assets/97a7bd27-ef5f-4c53-bdec-73677f873126)

<p>To make sure it set. I log into the Windows 10 VM to ping the private IP of the Window Server VM. I check the ipconfig to make sure the DNS is set to the IP of the Server VM aswell.</p>

![image](https://github.com/user-attachments/assets/cc14274d-8f89-446c-8dac-fde31f19419a)
![image](https://github.com/user-attachments/assets/aef4b5c3-328d-4fe3-9bf5-9edac502d537)
<p>
I log into the Windows 10 VM to connect to the my domain. I open system, then open rename this pc. Once in there I clicked change, to change the domain. Since, I set the DNS setting to point to the Windows Server VM it able to located it right away. It ask me to sign in and I put the information of one of the create admin I made to conncet to my domain.
</p>

![image](https://github.com/user-attachments/assets/566f0e87-72bb-40b7-9aaf-0de93c5d5a48)
<p>I check in my AD and my VM appears now as a Computer.</p>

![image](https://github.com/user-attachments/assets/ac964d0c-79c7-478d-993e-31c9e84ecfbd)
![image](https://github.com/user-attachments/assets/eb39a71d-d8a1-400f-9f12-f06ed86053f4)
![image](https://github.com/user-attachments/assets/eecd57dc-e03e-46b3-afcd-0454fa1add74)
<p>
I set up remote desktop for all domain users in my domain. I went into systems, then clicked remote desktop. In the page I clicked User Accounts and select users that can remotely access this PC. Then wrote domain user and clicked check names and it appears and I applied changes and press okay.
</p>

![image](https://github.com/user-attachments/assets/cc14c6e0-48dc-42f4-ad7c-85a91167e11e)
![image](https://github.com/user-attachments/assets/22a41637-2840-4c87-842e-2ff2b8959772)
<p>Once back in AD Users and Computers I create two OU which were admins, employees. </p>

![image](https://github.com/user-attachments/assets/345a5799-6512-477d-9f5b-f35872a867b3)
![image](https://github.com/user-attachments/assets/914f42ed-306a-4602-91a6-a7d392448ea1)
<p>In the admin group I add my fake user Jane.</p>

![image](https://github.com/user-attachments/assets/e4db374e-2926-4b87-88b3-4ee40623d0a3)
![image](https://github.com/user-attachments/assets/833b349f-116b-4489-8458-c9f9c0ad4136)
<p> I ran a script that would create fake users accounts to play around with AD.</p>



