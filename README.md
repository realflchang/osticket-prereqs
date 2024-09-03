<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket on an Azure Virtual Machine running Windows 10.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop Connection
- Internet Information Services (IIS)
- PHP & its extensions and dependencies
- MySQL & database client
- osTicket open source software

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Computer running Windows or Mac
- Microsoft Remote Desktop Connection from App Store on a Mac.  Windows should have it preinstalled

  <b>The following installation files are to be downloaded onto our Azure Virtual Machine:</b>
- PHP Manager for IIS - for managing one or many PHP installations compatible with the latest version of IIS - 10 [https://drive.google.com/file/d/1ny1YCitkjJ1LjuydfF0ips04FmTGK4iH/view?usp=sharing]
- rewrite amd64 [https://download.microsoft.com/download/D/8/1/D81E5DD6-1ABB-46B0-9B4B-21894E18B77F/rewrite_x86_en-US.msi]
- VC redist x86 [https://aka.ms/vs/17/release/vc_redist.x86.exe]
- PHP (v8.1) [https://windows.php.net/downloads/releases/php-8.1.29-nts-Win32-vs16-x64.zip]
- MySQL 5.5.62 [https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.62-win32.msi]
- HeidiSQL [https://www.heidisql.com/installers/HeidiSQL_12.8.0.6908_Setup.exe]
- osTicket (v1.17 as of 9/2024) [https://drive.google.com/file/d/1EYs5chYmyalfk49vtw-jpuVkntDPsYRg/view?usp=sharing]

<h2>Installation Steps</h2>

<p>1. Have an Azure Virtual Machine (VM) up and running Windows 10 Pro or later. Note the Public IP address assigned.</p>
<img src="https://github.com/user-attachments/assets/66e4f4ad-fc93-4cd8-a458-abf61bd97d09" alt="VM machine in Azure" />

<p>2. Connect to the VM with Microsoft Remote Desktop Connection by entering the IP of the VM:</p>
<img src="https://github.com/user-attachments/assets/2275a1ad-9096-4c6c-8d66-4edf80215b15" alt="Remote Desktop Connection log in" />

<p>3. Sign in again using the credentials set up with the VM:</p>
<img src="https://github.com/user-attachments/assets/e53d147e-2ab7-4c7f-8286-1c075f78aefe" alt="Windows Security log in" />

<p>4. Successful signing in to the VM:</p>
<img src="https://github.com/user-attachments/assets/abad74f4-c2cd-455b-a1b0-39e9d1a33dc6" alt="Initial screen after signing in to VM" />

<p>5. Enable IIS on the VM, by going to Control Panel, then clicking on Programs, then "Turn Windows features on or off".  IIS or Internet Information Services, allows the VM to act as a web server and host our osTicket application.</p>
<img src="https://github.com/user-attachments/assets/44877038-4cc2-4f42-962d-ce0274c0b9b3" alt="Control Panel Turn Windows features on or off" />

<p>6. Enable IIS Management Console</p>
<img src="https://github.com/user-attachments/assets/5703cdc7-069c-4da0-805e-8cc189f581da" alt="Enable IIS Management Console" />

<p>7. Enable IIS CGI handling, and Common HTTP Features</p>
<img src="https://github.com/user-attachments/assets/b7bd73c4-c592-41cf-80a5-9000b1a3d178" alt="Enable IIS CGI and Common HTTP Features" />


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
