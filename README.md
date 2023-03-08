<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
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
<img src="https://i.imgur.com/U7Fn3fr.png"80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
                                                                                        
<p>
<img src="https://i.imgur.com/vppA5Ns.png"80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>                                                                                        
First, you must create a virtual machine in Microsoft Azure and create your resource group (this is used to store all of the required resources that your virtual machine will produce). Next, name your virtual machine, choose the region, and select the operating system (Windows 10) that you want to use. You must select a virtual machine size to support the workload of the machine (4 vcpus, 16 GiB memory). This is helpful, so that your virtual machine is not moving slowly and determines the processing power, memory, and storage capacity. Also, make sure that your inbound support rules are selected to determine which ports are accessible from the internet (RDP 3389).
</p>
<br />

<p>
<img src="https://i.imgur.com/h4MrtTX.png"80" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the virtual machine, go to the virtual machine that you created and copy the Public IP address to login to a remote desktop connection (use the username and password created, when creating your virtual machine). Once you have logged into the remote desktop connection, go to the control panel, select Programs and Turn on or off Windows features and select the following to enable IIS with CGI on Windows 10. IIS with CGI is required to have the osTicket system installed on your virtual machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/S1p4Kt4.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install or enable IIS by opening the control panel. IIS will enable a web server on your computer to run osTicket from the web. You can do this by typing "control panel" from your search bar within your task bar at the bottom of your desktop. After enabling CGI, download and install PHP Manager for IIS and the Rewrite Module to your virtual machine. Next, create a PHP folder in the windows directory (C:).
</p>
<br />

<p>
<img src="https://i.imgur.com/BLY2Pmm.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<img src="https://i.imgur.com/bpvqQUV.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
Search the web and install: "Web Platform Installer" & open "Web Platform Installer". In the dialog box, search Web Platform Installer to add "MySQL 5.5" & search to add all simple versions of (x86) PHP up until 7.3.
</p>
<br />

<p>
<img src="https://i.imgur.com/aE4Rp7k.png"80%" width="80%" alt="Disk Sanitization Steps"/>
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
<img src="https://i.imgur.com/GhNcnlI.png"80%" alt="Disk Sanitization Steps"/>
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

<p>
<img src="https://i.imgur.com/m3x8NEE.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To create a database, you will need the username and password that was used to install MySQL. Create a new database by right-clicking on SSS-->New-->Database-->> name your database osTicket and click Ok.
</p>
<br />
                                                                                        
<p>
<img src="https://i.imgur.com/yPLDcqP.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to your osTicket installer in your browser tab and fill out the following information in the fields. --> System Settings-->Admin User-->Database Settings--> Click on "Install Now"
</p>
<br />                                                                                        
                                                                                        
<p>
<img src="https://i.imgur.com/rScwuIc.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This screen will show a successful installation of osTicket
</p>
<br /> 
                                                                                        
<p>
<img src="https://i.imgur.com/iloV0Ab.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lastly, we will clean up some files during installation to prevent future performance issues with osTicket. Go to your C:-->inetpub-->wwwroog-->osTicket and delete the setup file
</p>
<br /> 

<p>
<img src="https://i.imgur.com/ivJtdUI.png"80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to C:-->Inetpub-->wwwroot-->osTicket-->inlclude and right click on ost-config.php and select securities tab-->advanced-->click edit to change permissions for everyone to only have read & execute by deselecting the radio buttons. Click on apply-->Ok
</p>
<br /> 

                                                                                        
