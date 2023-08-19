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
- Start off by creating a Resource Group (RG) for our Windows 10 Virtual Machine on Microsoft Azure.  
  
  - Name your new Rg, "RG-osTicket".
  - Click a region server will be located, in this case West US 3.
  - Click review+create, let validation pass and click create.
  - Continue with creating your Windows 10 Virtual Machine.
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 08 45 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/42cd8bc2-4fc8-441e-afa7-73ff1ff9fa42">
<img width="1670" alt="Screenshot 2023-08-17 at 2 11 36 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/d465b247-3641-4203-a81f-8a2cbbee022d">
</p>
<p>
- Sear Virtual Machine (VM) in searchbar and create a Windows 10 VM 4 vCPUs into the resource group from previous step. 
  
  - Name it VM1
  - Region will be the same as your RG.
  - Create your username and password, so we can RDP into it later.
  - Don't forget to scroll down and check liscencing box.
  - Click Next: Disks and Next: Networking.
  - Allow a new Virtual Network (Vnet) to be created when making your Virtual Machine.
</p>
<img width="1670" alt="Screenshot 2023-08-17 at 2 14 29 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/99af24f7-b3a6-4691-9095-3129cc8dc903">
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 15 13 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/583c4e34-ce5e-4af8-a19e-28400ec3e84b">
</p>
<p>
- We will use remote desktop to connect to our VM after it is done creating.
  
  - Grab the public IP address and paste it into Microsoft Remote Desktop (on Mac OS download it)
  - Connect to it using our username and password we created.
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
- Search run in your Windows VM, type control and open programs.
  
  - Click "Turn Windows features on or off"
  - Install / Enable IIS in Windows WITH CGI and Common HTTP Features
  - IIS Management Console
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
- Using the installtion files from above, we can install the pre-requisites. 
  
  - Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 47 08 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/dc04f7c4-91cc-4a40-bdf6-b2658e841897">
</p>
<p>
- Download and install the Rewrite Module (rewrite_amd64_en-US.msi).
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 48 58 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/6f439f5f-503e-4bf2-933a-39445c60a135">
</p>
<p>
- Create the directory C:\PHP
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 52 55 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/db7e42ad-e629-4005-bad4-d544d33ee450">
</p>
<p>
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 2 57 11 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/ccd1acd6-bcda-498a-b095-7bcebf3debf0">
</p>
<p>
- Download and install VC_redist.x86.exe.
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 01 06 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/be305502-a49a-429e-9341-a78353e050ae">
</p>
<p>
- Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi), 
  
  - Typical Setup
  - Launch Configuration Wizard (after install)
  - Standard Configuration
  - Create a password.
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 02 03 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/05b61400-6b15-4cbc-9973-35b837659169">
  <img width="1670" alt="Screenshot 2023-08-18 at 3 02 22 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/e1e42342-83a6-43c6-ba3d-8053e863a3c1">
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 05 04 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/3bd8b4a0-a305-47b3-a184-b93c96e96f92">
</p>
<p>
- Open IIS as an Admin
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 06 40 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/50e0a482-3b1e-49b9-86e2-60bab82a966f">
<img width="1670" alt="Screenshot 2023-08-18 at 3 07 40 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/21c594fa-b5c8-46d8-b03c-c8a17cd2c8a1">

</p>
<p>
- Register PHP from within IIS
  
  - Restart IIS.
</p>
<P>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 08 01 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/834d366b-0fcd-4089-93ea-5941172e7922">
</P>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 15 55 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/e973fb29-ec0e-43fe-aae1-f0c62a45e936">
</p>
<p>
- Download/install osTicket v1.15.8 from files
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 08 01 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/a3c5facc-4571-4b18-ba8e-779912bb3bc0">
</p>
<p>
- Restart IIS
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 19 30 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/ea927d41-1bc4-4b5b-a1b5-f04a59efe4e3">
</p>
<p>
- Go to sites -> Default -> osTicket
  
  - On the right, click “Browse *:80”
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 21 29 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/35e19aea-79d4-4473-aa7d-d640d06931f7">
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-18 at 3 23 22 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/d531ec57-236f-4b0c-af2e-8877e0da5832">
</p>
<p>
- Note that some extensions are not enabled.
  
  - Go back to IIS, sites -> Default -> osTicket, double-click PHP Manager
  - Click “Enable or disable an extension”
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 23 59 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/1c2cb1f3-f06b-416d-bd75-c5ba6abf7255">
</p>
<p>
- Enable: 
  
  - php_imap.dll
  - php_intl.dll
  - php_opcache.dll,
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 27 14 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/4dc30329-bb26-48c9-bb06-f3ef4b41c0a3">
</p>
<p>
- Refresh the osTicket site in your browse, observe the changes
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-18 at 3 29 00 PM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/e7b04036-cfa8-49e6-9b64-6ef0d196275b">
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-19 at 10 22 07 AM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/371aad37-406f-4f11-ad3a-ba71d8cb8cd9">
</p>
<p>
- Before continuing, rename; ost-config.php. 
  
  - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
<img width="1670" alt="Screenshot 2023-08-19 at 10 27 58 AM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/54493c91-89fb-4a12-b182-d0d702f1a3b8">
</p>
<p>
- Assign Permissions: ost-config.php

  - Disable inheritance -> Remove All
  - New Permissions -> Everyone -> All
</p>
<p>
  <img width="1670" alt="Screenshot 2023-08-19 at 10 31 26 AM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/3fba080b-6367-4066-b6a1-7dffc4ae8a9a">
  <img width="1670" alt="Screenshot 2023-08-19 at 10 31 41 AM" src="https://github.com/rene369a/osticket-prereqs/assets/142533276/774714c3-c5bd-4454-ba3d-219ac8ac55c5">
</p>
<p>
- Give full control and apply permissions.
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
