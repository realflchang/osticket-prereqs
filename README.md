<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket on an Azure Virtual Machine running Windows 10.<br />

<!---
<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com) -->

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
- rewrite amd64 - which allows some url rewriting within osTicket [https://download.microsoft.com/download/D/8/1/D81E5DD6-1ABB-46B0-9B4B-21894E18B77F/rewrite_x86_en-US.msi]
- VC redist x86 [https://aka.ms/vs/17/release/vc_redist.x86.exe]
- PHP (v8.1) [https://windows.php.net/downloads/releases/php-8.1.29-nts-Win32-vs16-x64.zip]
- MySQL 5.5.62 [https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.62-win32.msi]
- HeidiSQL [https://www.heidisql.com/installers/HeidiSQL_12.8.0.6908_Setup.exe]
- osTicket (v1.17 as of 9/2024) [https://drive.google.com/file/d/1EYs5chYmyalfk49vtw-jpuVkntDPsYRg/view?usp=sharing]

<h2>Installation Steps</h2>

<p>1. Have an Azure Virtual Machine (VM) up and running Windows 10 Pro or later. Note the Public IP address assigned.</p>
<img src="https://github.com/user-attachments/assets/57a2a1f2-4d60-4c2c-bc7e-bfd405a39f72" alt="VM machine in Azure" />
<br /><br />

<p>2. Connect to the VM with Microsoft Remote Desktop Connection by entering the IP of the VM:</p>
<img src="https://github.com/user-attachments/assets/2275a1ad-9096-4c6c-8d66-4edf80215b15" alt="Remote Desktop Connection log in" />
<br /><br />

<p>3. Sign in again using the credentials set up with the VM:</p>
<img src="https://github.com/user-attachments/assets/e53d147e-2ab7-4c7f-8286-1c075f78aefe" alt="Windows Security log in" />
<br /><br />

<p>4. Successful signing in to the VM:</p>
<img src="https://github.com/user-attachments/assets/abad74f4-c2cd-455b-a1b0-39e9d1a33dc6" alt="Initial screen after signing in to VM" />
<br /><br />

<p>5. Enable IIS on the VM, by going to Control Panel, then clicking on Programs, then "Turn Windows features on or off".  IIS or Internet Information Services, allows the VM to act as a web server and host our osTicket application.</p>
<img src="https://github.com/user-attachments/assets/44877038-4cc2-4f42-962d-ce0274c0b9b3" alt="Control Panel Turn Windows features on or off" />
<br /><br />

<p>6. Enable IIS Management Console</p>
<img src="https://github.com/user-attachments/assets/5703cdc7-069c-4da0-805e-8cc189f581da" alt="Enable IIS Management Console" />
<br /><br />

<p>7. Enable IIS CGI handling, and Common HTTP Features</p>
<img src="https://github.com/user-attachments/assets/b7bd73c4-c592-41cf-80a5-9000b1a3d178" alt="Enable IIS CGI and Common HTTP Features" />
<br /><br />

<p>8. Install our PHP Manager for IIS</p>
<img src="https://github.com/user-attachments/assets/a780f775-8974-4bd9-ada6-b630bfee98d7" alt="Install PHP Manager for IIS" />
<img src="https://github.com/user-attachments/assets/1268f23d-ed70-406b-ad52-5ca266bab5bb" alt="Install PHP Manager for IIS" />
<br /><br />

<p>9. Install our rewrite module</p>
<img src="https://github.com/user-attachments/assets/8db46a31-3aff-4d7e-86f6-622c7614c87f" alt="Done installing the rewrite module" />
<br /><br />

<p>10. Install our PHP engine. We will need to extract the contents of our PHP...zip file, into a new folder C:\PHP:</p>
<img src="https://github.com/user-attachments/assets/3ccc0b72-b697-4d10-8bab-d97dcbf2e1c6" alt="Contents of C:\PHP folder" />
<br /><br />

<p>11. Install our Visual C++ Redistributable:</p>
<img src="https://github.com/user-attachments/assets/3400b770-03c0-41ea-99c3-64a25f5f0191" alt="Done installing Visual C++ Redistributable" />
<br /><br />

<p>12. Install MySQL, and note the database username/pwd you are setting up with:</p>
<img src="https://github.com/user-attachments/assets/ee27ee5e-068a-48ce-86fb-9ece3dd8053b" alt="Done MySQL installation" />
<img src="https://github.com/user-attachments/assets/559ac738-69d4-4700-b62e-9da9350459eb" alt="Done MySQL installation" />
<br /><br />

<p>13. Verify that IIS is running, by going to the Edge browser and entering the localhost IP 127.0.0.1:</p>
<img src="https://github.com/user-attachments/assets/86fcd429-d4e9-45c8-8133-dd7ebb0ebb50" alt="IIS is running in browser" />
<br /><br />

<p>14. Let's go to the IIS Manager (Management Console) to update some settings:</p>
<img src="https://github.com/user-attachments/assets/fb45aa59-b5b9-4b6b-8731-6be1028b2348" alt="Opening IIS Manager" />
<br /><br />

<p>15. Go to PHP Manager:</p>
<img src="https://github.com/user-attachments/assets/fc98b481-e3fc-4d4d-9b03-f72ae76de0c2" alt="IIS Manager showing PHP Manager icon" /?
<img src="https://github.com/user-attachments/assets/1aa9d9c6-caf1-4eee-b10c-bde373eb3a5b" alt="PHP Manager" />
<br /><br />

<p>16. Register our PHP by clicking on the "Register new PHP version" link, and browse to our C:\PHP\php_cgi.exe file:</p>
<img src="https://github.com/user-attachments/assets/7077f51e-4005-4c9a-bede-132bd7bac906" alt="PHP Manager after registering PHP" />
<br /><br />

<p>17. Enable these PHP extensions. Below the previous "Register new PHP version" link, will be a "Enable or disable an extension" link:
  - php_imap – allows php access to a imap/pop/nntp server
  - php_intl – for internationalization functions
  - php_opcache – allows faster subsequent webpage loading
</p>
<img src="https://github.com/user-attachments/assets/28aeb469-3016-4763-97e5-4206cef5758a" alt="Link for PHP Extensions" />
<img src="https://github.com/user-attachments/assets/34174548-4c4a-4e08-a3df-b4a3073db793" alt="PHP Extensions after enabling 3 extensions" />
<br /><br />

<p>18. Begin installing our osTicket. Open the osTicket zip file, and extract the "upload" folder into C:\inetpub\wwwroot:</p>
<img src="https://github.com/user-attachments/assets/3d2f21ca-a82c-4b40-be8a-326c0b9f7f5b" alt="Extracting osTicket" />
<img src="https://github.com/user-attachments/assets/07006ca3-becc-459a-bbd2-3217c62bd0ac" alt="Extracting osTicket" />
<br /><br />

<p>19. Rename the "upload" folder to "osTicket"</p>
<img src="https://github.com/user-attachments/assets/d2494c7c-1a4b-42e2-912a-08f51fae5001" alt="Rename folder to osTicket" />
<br /><br />

<p>20. Verify that osTicket is running in IIS Manager:</p>
<img src="https://github.com/user-attachments/assets/6a5ac809-d93e-4556-a1a2-9dadb2026b3a" alt="osTicket shows in IIS Manager" />
<br /><br />

<p>21. Click on "Browse *.80 (http) from the right side panel:</p>
<img src="https://github.com/user-attachments/assets/158455e1-fa71-458a-8ec4-80dedc9ab216" alt="Click on Browse 80 http" />
<br /><br />

<p>22. If successful, we should have the following Thank You page:</p>
<img src="https://github.com/user-attachments/assets/954834b8-bc08-4638-8006-6f9673e0594e" alt="Successful osTicket page" />
<br /><br />

** We will continue into the next section: [osTicket: Post-Installation Configuration](https://github.com/realflchang/post-install-config).


