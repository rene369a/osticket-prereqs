<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket, using Microsoft Azure: Virtual Machines on Mac OS.<br />


<h2>Video Demonstration</h2>

- ### [How To Install osTicket with Prerequisites](https://imgur.com/a/2cGhKHN)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Mac OS

<h2>List of Prerequisites</h2>

- Create Resource Group in Microsoft Azure and Create Windows 10 VM 4vCPUs
- Install/Enable IIS in Windows with CGI and Common HTTP features
- [Download and Install files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6), according to steps below
- After MySQL download and install, open IIS as Admin, Register PHP from within IIS, Reload IIS
- Install osTicket from files, extract copy "upload" folder to c:\inetpub\wwwroot, within c:\inetpub\wwwroot, rename "upload" folder to "osTicket"

<h2>Installation Steps</h2>

<p>
<img width="1670" alt="Screenshot 2023-08-17 at 1 36 05 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/3be3c31b-5237-4eaa-b56b-4a012ccb769b">
</p>
<p>
Start off by signing in to Miscrosoft Azure (https://portal.azure.com), so we can create a resource group for our Windows 10 Virtual Machine. Then, search for Resource Groups, click it and proceed with making a new Resource Group named "RG-osTicket". Click a region where your Resource Group will be located, in this case West US 3. After, click review+create, let validation pass and click create. Congrats on creating your Resource Group, now we can continue with our Virtual Machine.
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 08 45 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/42cd8bc2-4fc8-441e-afa7-73ff1ff9fa42">
<img width="1670" alt="Screenshot 2023-08-17 at 2 11 36 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/d465b247-3641-4203-a81f-8a2cbbee022d">
</p>
<p>
Search for Virtual Machines and once there, click on create; Azure Virtual Machine. We will be creating a Windows 10 VM 4 vCPUs into the resource group from previous step. Name it VM1 and region will be the same as your RG. Choose Windows 10 Pro, 22H2, for Image; 4 vCPUs for size, and your username and password. Don't forget to scroll down and check liscencing box. Then, click Next: Disks and Next: Networking. Allow a new Virtual Network (Vnet) to be created when making your Virtual Machine.
</p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 14 29 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/99af24f7-b3a6-4691-9095-3129cc8dc903">
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
