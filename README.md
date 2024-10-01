<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo">
</p>

<h1>osTicket - Prerequisites and Installation</h1>

<p>This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.</p>

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used</h2>

- Windows 10 (22H2)

<h2>List of Prerequisites</h2>

<h2>List of Prerequisites</h2>

<ul>
  <li><strong>Azure Virtual Machine:</strong> A Windows 10 VM with 4 vCPUs created in Microsoft Azure.</li>
  <li><strong>Remote Desktop Connection (RDP):</strong> Ability to connect to the VM using Remote Desktop.</li>
  <li><strong>Internet Information Services (IIS):</strong> IIS installed and configured on the Windows 10 VM to serve web applications.</li>
  <li><strong>PHP and PHP Manager:</strong> PHP installed and configured with PHP Manager on IIS to support osTicket.</li>
  <li><strong>MySQL Database:</strong> MySQL installed to store osTicket data.</li>
  <li><strong>osTicket Installation Files:</strong> osTicket files downloaded and extracted for installation.</li>
  
</ul>


<h2>Installation Steps</h2>

<p align="center">
  <img src="https://github.com/user-attachments/assets/6c31d47e-1923-4e56-bc96-a61b28f5a84f" height="80%" width="80%" alt="Step 1 Image"/>
</p>
<p><strong>Create a Virtual Machine on Azure Step 1</strong>: Go to the Azure Portal and log in with your credentials. Once logged in, click on "Create a Resource" and select "Virtual Machine." Name your virtual machine osTicket-Lab and select the region closest to you for optimal performance. For the image, choose Windows 10 Pro, Version 22H2, and for the size, select Standard_D2s_v3 (2 vCPUs, 8 GiB memory). Under the Administrator Account section, create a username and password for the VM (e.g., labuser as the username and osTicketPassword1! as the password). Finally, click on "Review + Create," and once validation is complete, click "Create" to deploy your virtual machine. 

<p align="center">
  <img src="https://github.com/user-attachments/assets/380a7c16-0e1f-409e-b310-4c8d1f940571" height="80%" width="80%" alt="Step 2 Image 1"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/1767900f-e9c4-4a68-a4e8-85662d264444" height="80%" width="80%" alt="Step 2 Image 2"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/ba1f3f6e-93f3-4040-9869-9fa001d50b78" height="80%" width="80%" alt="Step 2 Image 3"/>
</p>
<p><strong>Connect to the VM Step 2</strong>: Now, you would have to wait for the VM to be deployed. Once that happens, go to the homepage and click on the VM (`osTicket-Lab`). It will display its public IP address, which we will need to connect to the VM through Remote Desktop. To connect to the VM, open the Remote Desktop app, click on "Add PC," and paste the public IP address into the "PC Name" field. Then, put `osTicket-Lab` as the friendly name and click "Add." Now, double-click the new PC and enter the username and password you created in Step 1. You should now be connected to the VM.


<p align="center">
  <img src="https://github.com/user-attachments/assets/b08600d3-ebd4-4f9b-9f9a-3d9b96b3e152" height="80%" width="80%" alt="Step 3 Image 1"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/a4bacaef-7d17-4e36-be19-14eae8ed71ff" height="80%" width="80%" alt="Step 3 Image 2"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/567195ac-1795-4d92-9e55-dcf8c9655ec6" height="80%" width="80%" alt="Step 3 Image 3"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/c04864ae-49fb-40b7-899b-2f6d307881e4" height="80%" width="80%" alt="Step 3 Image 4"/>
</p>
<p><strong>Enable IIS and CGI Step 3</strong>:   To enable IIS and CGI in Windows, go to the Control Panel, click on "Programs," and then on the left-hand side, click on "Turn Windows features on or off." Check the box next to <strong>Internet Information Services (IIS)</strong> to enable it. To enable CGI, click the dropdown arrow next to <strong>World Wide Web Services</strong>, expand <strong>Application Development Features</strong>, and check the box next to <strong>CGI</strong> to enable it.</p>



<img width="1440" alt="Screenshot 2024-10-01 at 2 49 31 AM" src="https://github.com/user-attachments/assets/53569c66-a2e2-4411-9df9-d45db24bb9f8">
<img width="1440" alt="Screenshot 2024-10-01 at 2 50 09 AM" src="https://github.com/user-attachments/assets/81c994c2-3988-43c7-9e85-a5af83aa43d9">
<img width="1440" alt="Screenshot 2024-10-01 at 2 50 47 AM" src="https://github.com/user-attachments/assets/4219006b-a312-4f94-9c75-631534bf758a">
<img width="1440" alt="Screenshot 2024-10-01 at 2 53 15 AM" src="https://github.com/user-attachments/assets/696bc314-5b8a-4abd-a585-603061cacfb7">
<img width="1440" alt="Screenshot 2024-10-01 at 2 54 19 AM" src="https://github.com/user-attachments/assets/a5c9f991-5e1b-40b1-ade3-3889f438122f">
<img width="1440" alt="Screenshot 2024-10-01 at 2 54 23 AM" src="https://github.com/user-attachments/assets/f73428ec-8e15-41db-9db5-73c29ea32f80">
<img width="1440" alt="Screenshot 2024-10-01 at 2 55 36 AM" src="https://github.com/user-attachments/assets/0fd3e42d-8a2a-4d6b-9305-b0d38622f5f9">


<p><strong>Installing PHP, Rewrite Module, and VC_redist Step 4</strong>: Within the VM, navigate to the `osTicket-Installation-Files` folder on your desktop. Install **PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)** and the **Rewrite Module (rewrite_amd64_en-US.msi)** from the folder. Then, create a directory named `C:\PHP`. Next, unzip **PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)** into the `C:\PHP` folder. After that, install the **VC_redist.x86.exe** (Microsoft Visual C++ Redistributable) to ensure that all the necessary runtime libraries are available.</p> 


<img width="1440" alt="Screenshot 2024-10-01 at 3 09 08 AM" src="https://github.com/user-attachments/assets/d096f314-b664-4f76-8ab2-975c74c45d9b">
<img width="1440" alt="Screenshot 2024-10-01 at 3 10 54 AM" src="https://github.com/user-attachments/assets/f89575e9-52be-4e42-a760-b8f35e1110d8">
<img width="1440" alt="Screenshot 2024-10-01 at 3 13 09 AM" src="https://github.com/user-attachments/assets/fd3b5900-70e4-47bc-a8ab-c52c8fac2847">



<p><strong>Installing MySQL Step 5</strong>: Description of Step 5. From the `osTicket-Installation-Files` folder, install **MySQL 5.5.62 (mysql-5.5.62-win32.msi)** using the Typical Setup. After the installation is complete, launch the Configuration Wizard. Select "Standard Configuration," and set the MySQL root username and password to whatever I just put `root` for both.</p>

<p align="center">
  <img src="https://i.imgur.com/DmEXE8R.png" height="80%" width="80%" alt="Step 5 Image"/>
</p>
<p><strong>Step 6</strong>: Open IIS as an administrator by searching for "IIS Manager" and selecting "Run as Administrator." Next, register PHP in IIS by navigating to "PHP Manager" and setting the path to "C:\PHP\php-cgi.exe". Once PHP is registered, reload IIS by stopping and starting the server through IIS Manager.</p>

<p>Afterward, install osTicket v1.15.8. Go to the "osTicket-Installation-Files" folder on your desktop, unzip "osTicket-v1.15.8.zip," and copy the "upload" folder into "C:\inetpub\wwwroot." Rename the "upload" folder to "osTicket." Once renamed, reload IIS again by stopping and starting the server.</p>

<p>Now, access osTicket by going to IIS Manager, navigating to "Sites" -> "Default Website" -> "osTicket", and clicking "Browse *:80" on the right-hand side. This should open osTicket in your browser. If certain PHP extensions are not enabled, return to IIS Manager, navigate to "Sites" -> "Default Website" -> "osTicket", double-click "PHP Manager", and then click "Enable or disable an extension". Enable the following extensions: "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Refresh the osTicket site in your browser after enabling the extensions.</p>

<p>Next, rename the configuration file. Go to "C:\inetpub\wwwroot\osTicket\include", and rename "ost-sampleconfig.php" to "ost-config.php". Set permissions for the "ost-config.php" file by disabling inheritance. Right-click the file, select "Properties", go to the "Security" tab, click "Advanced", then select "Disable inheritance" and remove all inherited permissions. Add new permissions by assigning "Everyone" full control over the file.</p>


<p align="center">
  <img src="https://i.imgur.com/DmEXE8R.png" height="80%" width="80%" alt="Step 5 Image"/>
</p>
<p><strong>Step 7</strong>: Description of Step 7. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
