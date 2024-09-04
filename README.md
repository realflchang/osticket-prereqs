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
- rewrite amd64 - which allows some url rewriting within osTicket [https://download.microsoft.com/download/D/8/1/D81E5DD6-1ABB-46B0-9B4B-21894E18B77F/rewrite_x86_en-US.msi]
- VC redist x86 [https://aka.ms/vs/17/release/vc_redist.x86.exe]
- PHP (v8.1) [https://windows.php.net/downloads/releases/php-8.1.29-nts-Win32-vs16-x64.zip]
- MySQL 5.5.62 [https://downloads.mysql.com/archives/get/p/23/file/mysql-5.5.62-win32.msi]
- HeidiSQL [https://www.heidisql.com/installers/HeidiSQL_12.8.0.6908_Setup.exe]
- osTicket (v1.17 as of 9/2024) [https://drive.google.com/file/d/1EYs5chYmyalfk49vtw-jpuVkntDPsYRg/view?usp=sharing]

<h2>Installation Steps</h2>

<p>1. Have an Azure Virtual Machine (VM) up and running Windows 10 Pro or later. Note the Public IP address assigned.</p>
<img src="https://github.com/user-attachments/assets/57a2a1f2-4d60-4c2c-bc7e-bfd405a39f72" alt="VM machine in Azure" />

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

<p>8. Install our PHP Manager for IIS</p>
<img src="https://github.com/user-attachments/assets/a780f775-8974-4bd9-ada6-b630bfee98d7" alt="Install PHP Manager for IIS" />
<img src="https://github.com/user-attachments/assets/1268f23d-ed70-406b-ad52-5ca266bab5bb" alt="Install PHP Manager for IIS" />

<p>9. Install our rewrite module</p>
<img src="https://github.com/user-attachments/assets/8db46a31-3aff-4d7e-86f6-622c7614c87f" alt="Done installing the rewrite module" />

<p>10. Install our PHP engine. We will need to extract the contents of our PHP...zip file, into a new folder C:\PHP:</p>
<img src="https://github.com/user-attachments/assets/3ccc0b72-b697-4d10-8bab-d97dcbf2e1c6" alt="Contents of C:\PHP folder" />

<p>11. Install our Visual C++ Redistributable:</p>
<img src="https://github.com/user-attachments/assets/3400b770-03c0-41ea-99c3-64a25f5f0191" alt="Done installing Visual C++ Redistributable" />

<p>12. Install MySQL, and note the database username/pwd you are setting up with:</p>
<img src="https://github.com/user-attachments/assets/ee27ee5e-068a-48ce-86fb-9ece3dd8053b" alt="Done MySQL installation" />
<img src="https://github.com/user-attachments/assets/559ac738-69d4-4700-b62e-9da9350459eb" alt="Done MySQL installation" />

<p>13. Verify that IIS is running, by going to the Edge browser and entering the localhost IP 127.0.0.1:</p>
<img src="https://github.com/user-attachments/assets/86fcd429-d4e9-45c8-8133-dd7ebb0ebb50" alt="IIS is running in browser" />

<p>14. Let's go to the IIS Manager (Management Console) to update some settings:</p>
<img src="https://github.com/user-attachments/assets/fb45aa59-b5b9-4b6b-8731-6be1028b2348" alt="Opening IIS Manager" />

<p>15. Go to PHP Manager:</p>
<img src="https://github.com/user-attachments/assets/fc98b481-e3fc-4d4d-9b03-f72ae76de0c2" alt="IIS Manager showing PHP Manager icon" /?
<img src="https://github.com/user-attachments/assets/1aa9d9c6-caf1-4eee-b10c-bde373eb3a5b" alt="PHP Manager" />

<p>16. Register our PHP by clicking on the "Register new PHP version" link, and browse to our C:\PHP\php_cgi.exe file:</p>
<img src="https://github.com/user-attachments/assets/7077f51e-4005-4c9a-bede-132bd7bac906" alt="PHP Manager after registering PHP" />

<p>17. Enable these PHP extensions. Below the previous "Register new PHP version" link, will be a "Enable or disable an extension" link:
  - php_imap – allows php access to a imap/pop/nntp server
  - php_intl – for internationalization functions
  - php_opcache – allows faster subsequent webpage loading
</p>
<img src="https://github.com/user-attachments/assets/28aeb469-3016-4763-97e5-4206cef5758a" alt="Link for PHP Extensions" />
<img src="https://github.com/user-attachments/assets/34174548-4c4a-4e08-a3df-b4a3073db793" alt="PHP Extensions after enabling 3 extensions" />

<p>18. Begin installing our osTicket. Open the osTicket zip file, and extract the "upload" folder into C:\inetpub\wwwroot:</p>
<img src="https://github.com/user-attachments/assets/3d2f21ca-a82c-4b40-be8a-326c0b9f7f5b" alt="Extracting osTicket" />
<img src="https://github.com/user-attachments/assets/07006ca3-becc-459a-bbd2-3217c62bd0ac" alt="Extracting osTicket" />

<p>19. Rename the "upload" folder to "osTicket"</p>
<img src="https://github.com/user-attachments/assets/d2494c7c-1a4b-42e2-912a-08f51fae5001" alt="Rename folder to osTicket" />

<p>20. Verify that osTicket is running in IIS Manager:</p>
<img src="https://github.com/user-attachments/assets/6a5ac809-d93e-4556-a1a2-9dadb2026b3a" alt="osTicket shows in IIS Manager" />

<p>21. Click on "Browse *.80 (http) from the right side panel:</p>
<img src="https://github.com/user-attachments/assets/158455e1-fa71-458a-8ec4-80dedc9ab216" alt="Click on Browse 80 http" />

<p>22. If successful, we should have the following Thank You page:</p>
<img src="https://github.com/user-attachments/assets/954834b8-bc08-4638-8006-6f9673e0594e" alt="Successful osTicket page" />



<p>1. Begin osTicket Configuration.  In Windows Explorer, browse to C:\inetpub\wwwroot\osTicket\include\ and look for ost-sampleconfig.php, and rename this file to ost-config.php:</p>
<img src="https://github.com/user-attachments/assets/c4909882-3676-4fc1-baad-51f3e9babfa8" alt="Browse to our ost-sampleconfig.php file" />
<img src="https://github.com/user-attachments/assets/eac577d5-61e6-4989-84da-b35bed03a802" alt="And rename it to ost-config.php" />

<p>2. Temporarily reassign security permissions to "Everyone" with read and write access for ost-config.php:</p>
<img src="https://github.com/user-attachments/assets/1eb5c203-c11f-494a-a2e0-adadb3abf5de" alt="RW permissions to ost-config.php" />

<p>3. Install HeidiSQL, which is our MySQL database client that allows sending SQL commands to MySQL</p>
<img src="https://github.com/user-attachments/assets/731e738c-ede6-4bc8-babd-5da016766f41" alt="Done HeidiSQL" />
<img src="https://github.com/user-attachments/assets/24e5ce7a-76ce-42ee-a2a2-74e1b54727fa" alt="Done HeidiSQL" />

<p>4. Click New and connect to MySQL:</p>
<img src="https://github.com/user-attachments/assets/a86c6c76-a741-4349-b721-5e2b375691e6" alt="Connect to MySQL" />

<p>5. Create a new MySQL database called "osTicket". All of our osTicket activities will be stored in this database:</p>
<img src="https://github.com/user-attachments/assets/f51257d1-31b6-4ff1-a728-e28db337c671" alt="Create a database called osTicket" />

<p>6. Continue our osTicket installation and configuration. At the previous "Thank You" page at the bottom is a "Continue" button. Complete the fields as appropriate</p>
<img src="https://github.com/user-attachments/assets/a0b14417-6334-48ce-8933-f2fc054eca94" alt="Thank You page with Continue button" />
<img src="https://github.com/user-attachments/assets/43b340d3-1645-4607-8a5f-413a693bee8c" alt="osTicket Begin Installation page" />

<p>7. Once done, we will have this Congratulations page. Note our links to the Admin and Agent portals:</p>
<img src="https://github.com/user-attachments/assets/63d9b66e-3a91-4427-aca3-ceb7d1fb1081" alt="Congratulations on installing osTicket" />

<p>8. Go back to our ost-config.php in Windows Explorer, and change the permissions to Read only:</p>
<img src="https://github.com/user-attachments/assets/12c0ad5f-2a55-466b-91d9-8dc897006086" alt="Read only for ost-config.php" />

<p>9. In a browser window, go to the link for our Admin portal:</p>
<img src="https://github.com/user-attachments/assets/a5eae3d9-f401-463c-8af8-6be92817faf3" alt="Going to our Admin portal" />
<img src="https://github.com/user-attachments/assets/42889592-cc3c-4579-97be-4aa173af4153" alt="Going to our Admin portal" />

<p>10. We can then make any other configurations as appropriate.</p>
<img src="https://github.com/user-attachments/assets/53dec451-25d6-4094-83d6-ae0865360a4d" alt="Super Admin Role" />
<img src="https://github.com/user-attachments/assets/005d0884-5df1-4f37-b8f7-7b9b6a162e17" alt="System Administrators Department" />
<img src="https://github.com/user-attachments/assets/a0f299d2-445e-4d35-bf2f-ed6a9b20a5c2" alt="Level II Support Team" />
<img src="https://github.com/user-attachments/assets/82d360e2-98e2-4414-ba93-c92520db9892" alt="Creating Users" />
<img src="https://github.com/user-attachments/assets/50baa259-e63b-47cc-a8f3-9bd2f7f4030d" alt="Creating SLAs" />
<img src="https://github.com/user-attachments/assets/f565bd61-b863-4d9c-82ac-6ec249f17f68" alt="Adding Help Topic" />


  
