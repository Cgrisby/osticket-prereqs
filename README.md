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
<img src="https://i.imgur.com/i8PWjfk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/f87Ja2o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Search the web and install: "Web Platform Installer" & open "Web Platform Installer". In the dialog box, search Web Platform Installer to add "MySQL 5.5" & search to add all simple versions of (x86) PHP up until 7.3.
</p>
<br />

<p>
<img src="https://i.imgur.com/zGzDaHG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Web installer will attempt to finish installing all of the prerequistes that are checked (some of the downloads will fail, just manually download C++ redistribuable & PHP Manager via files found online). Continue to finish with installation. Find and install "PHP Manager" version 7.3.8 & version 1.5.0.
</p>
<br />

<p>
<img src="https://i.imgur.com/JOMLIss.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Microsoft Visual C++ and PHP Manager. Installation errors should be fixed at this point. Download and install the osTicket software. You will need to extract the zip file once downloaded.
</p>
<br />

<p>
<img src="https://i.imgur.com/jB5NeB0.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once osTicket has been installed, open the download folder and copy it into your wwwroot folder that was created from IIS and rename the folder from upload to osTicket. filepath ThisPC/Windows (C:)/inetpub/wwwroot
</p>
<br />

<p>
<img src="https://i.imgur.com/b256sAE.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to -->Taskbar-->Type IIS in the searchbar and open the program-->You will need to restart the web server by selecting the browse 80 folder in the connections folder. -->Sites-->osTicket-->browse80-->stop-->restart
</p>
<br />
                                                                                        
<p>
<img src="https://i.imgur.com/J0gLMkd.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
If the program was properly installed, you will see this prerequesite screen. If not, please go back and install the missing php, C++, or php manager. We will now enable extensions.
</p>
<br />

<p>
<img src="https://i.imgur.com/KqJumLf.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable the following extenions, php_imap.dll, php_intl.dll, and php_opcache. Please refresh the osTicket site and oberve the changes.
</p>
<br />                                                                                       
                                               
<p>
<img src="https://i.imgur.com/o6CgugC.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to C:-->inetpub-->wwwroot-->osTicket-->include and right-click the ost-sampleconfig.php file and rename it to ost-config.php
</p>
<br />                                                 
                                               
<p>
<img src="https://i.imgur.com/Q3SIcBn.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable automatic permissions for everyone in this file by right-clicking on the file and select -->Properties-->Advanced-->Disable inheritance-->type everyone in the next dialog box-->selct the Full Access radio button-->Select the Apply button-->Select the Ok button
</p>
<br />
                                                                                        
<p>
<img src="https://i.imgur.com/Vci5OV7.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install HeidiSQL for osTicket to have a client database that connects to MySQL that was installed previously.
</p>
<br />



