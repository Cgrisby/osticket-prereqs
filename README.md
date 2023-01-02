<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Microsoft Azure Subscription and Virtual Machine
- Install Microsoft Desktop for Mac OS
- Enable Internet Information Services (IIS)
- Install Web Platform Installer
- Add MySQL 5.5
- Add all simple versions of x86 PHP up to v7.3
- Configure Permissions & Install osTicket v1.15.8
- Reload IIS (Open IIS, Stop and Start the server)
- Enable extensions in IIS
- Refresh the osTicket site in your browser and observe the changes


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/mYQ87i2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to portal.azure.com and make a subscription. Create a resource group and virtual machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/Dkn89DR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Using MacOS download Microsoft Remote Desktop and go to "Add PC". Use the Public IP address from your Virtual Machine in Azure to name and connect your remote desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/g7412kc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install or enable IIS by opening the control panel. IIS will will enable a web server on your computer to run osTicket from the web. You can do this by typing "control panel" from your search bar within your task bar at the bottom of your desktop. Enable PHP Manager extensions and refresh the osTicket browser to observe the changes. 
</p>
<br />

<p>
<img src="blob:https://imgur.com/8901fe91-47de-4b4d-af94-ea90ed007acd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once IIS has been installed, search the internet for Microsoft Web Platform Installer and download this extension. You will need it to install the remaining software needed to install osTicket.
</p>
<br />
