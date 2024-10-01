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
<p><strong>Step 1</strong>: Description of Step 1. Go to the Azure Portal and log in with your credentials. Once logged in, click on "Create a Resource" and select "Virtual Machine." Name your virtual machine osTicket-Lab and select the region closest to you for optimal performance. For the image, choose Windows 10 Pro, Version 22H2, and for the size, select Standard_D2s_v3 (2 vCPUs, 8 GiB memory). Under the Administrator Account section, create a username and password for the VM (e.g., labuser as the username and osTicketPassword1! as the password). Finally, click on "Review + Create," and once validation is complete, click "Create" to deploy your virtual machine. 
<p align="center">
  <img src="https://github.com/user-attachments/assets/380a7c16-0e1f-409e-b310-4c8d1f940571" height="80%" width="80%" alt="Step 2 Image 1"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/1767900f-e9c4-4a68-a4e8-85662d264444" height="80%" width="80%" alt="Step 2 Image 2"/>
</p>
<p align="center">
  <img src="https://github.com/user-attachments/assets/ba1f3f6e-93f3-4040-9869-9fa001d50b78" height="80%" width="80%" alt="Step 2 Image 3"/>
</p>
<p><strong>Step 2</strong>: Description of Step 2. Now, you would have to wait for the VM to be deployed. Once that happens, go to the homepage and click on the VM (`osTicket-Lab`). It will display its public IP address, which we will need to connect to the VM through Remote Desktop. To connect to the VM, open the Remote Desktop app, click on "Add PC," and paste the public IP address into the "PC Name" field. Then, put `osTicket-Lab` as the friendly name and click "Add." Now, double-click the new PC and enter the username and password you created in Step 1. You should now be connected to the VM.

<p align="center">
  <img src="https://i.imgur.com/DmEXE8R.png" height="80%" width="80%" alt="Step 3 Image"/>
</p>
<p><strong>Step 3</strong>: Description of Step 3. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>

<p align="center">
  <img src="https://i.imgur.com/DmEXE8R.png" height="80%" width="80%" alt="Step 4 Image"/>
</p>
<p><strong>Step 4</strong>: Description of Step 4. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>

<p align="center">
  <img src="https://i.imgur.com/DmEXE8R.png" height="80%" width="80%" alt="Step 5 Image"/>
</p>
<p><strong>Step 5</strong>: Description of Step 5. Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
