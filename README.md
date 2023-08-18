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

- Install/Enable IIS in Windows with CGI and Common HTTP features
- Install Web Platform Installer
- Install MySQL, set up username and password
- Configure permissions and install osTicket
- Enable osTicket extensions: php_imap.dll, php_intl.dll, php_opcache.dll

<h2>Installation Steps</h2>

<p>
<img width="1670" alt="Screenshot 2023-08-17 at 1 36 05 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/3be3c31b-5237-4eaa-b56b-4a012ccb769b">
</p>
<p>
- Start off by creating a Resource Group (RG) for our Windows 10 Virtual Machine on Microsoft Azure.  Name your new Rg, "RG-osTicket". Click a region server will be located, in this case West US 3. After, click review+create, let validation pass and click create. Now we can continue with our Virtual Machine.
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 08 45 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/42cd8bc2-4fc8-441e-afa7-73ff1ff9fa42">
<img width="1670" alt="Screenshot 2023-08-17 at 2 11 36 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/d465b247-3641-4203-a81f-8a2cbbee022d">
</p>
<p>
- Sear Virtual Machine (VM) in searchbar and create a Windows 10 VM 4 vCPUs into the resource group from previous step. Name it VM1 and region will be the same as your RG. Create your username and password, so we can RDP into it later. Don't forget to scroll down and check liscencing box. Click Next: Disks and Next: Networking. Allow a new Virtual Network (Vnet) to be created when making your Virtual Machine.
</p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 14 29 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/99af24f7-b3a6-4691-9095-3129cc8dc903">
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 15 13 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/583c4e34-ce5e-4af8-a19e-28400ec3e84b">
</p>
<p>
- We will use remote desktop to connect to our VM after it is done creating. Grab the public IP address and paste it into Microsoft Remote Desktop (on Mac OS download it) and connect to it using our username and password we created.
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 2 17 03 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/c530701c-827c-4c0d-bb77-1c9f9b93e304">
</p>
<p>
- Click continue on the certification and use https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 to install prerequisites.
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 30 30 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/0fa8c48e-c0c4-4cdb-aaee-d02f1f330dd4">
</p>
<p>
- Search run in your Windows VM, type control and open programs. From there, click "Turn Windows features on or off" and Install / Enable IIS in Windows WITH CGI and Common HTTP Features and IIS Management Console
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 2 37 00 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/96a45dfc-f16b-4167-89a6-94ff1f147ef9">
</p>
<p>
- If done correctly, open up your web browser and type 127.0.0.1 and it should redirect you IIS "page"
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 41 56 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/4a65b8f0-c9ac-4a87-a9db-f8f4926f5870">
</p>
<p>
- Using the installtion files from above, we can install the pre-requisites, so we can install osTicket to your VM. Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
