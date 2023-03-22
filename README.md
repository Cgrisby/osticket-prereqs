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

- Create Virtual Machine in Microsoft Azure
- Install/Enable Internet Information Services (IIS) in Windows with CGI and download PHP Manager for IIS
- Download and Install Rewrite Module and Create directory for PHP to unzip files
- Download and Intsall VC file and MySQL
- Register PHP in IIS and reload to install osTicket v1.15.8
- Enable required extensions to continue installation of osTicket
- Install HeidiSQL to link MySQL database to osTicket

<h2>Installation Steps</h2>

<h2>Create a Virtual Machine in Microsoft Azure</h2>
<p>
<img src="https://i.imgur.com/TT8okiI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, you must create a virtual machine in Microsoft Azure and create your resource group (this is used to store all of the required resources that your virtual machine will produce). Next, name your virtual machine, choose the region, and select the operating system (Windows 10) that you want to use. You must select a virtual machine size to support the workload of the machine (4 vcpus, 16 GiB memory). This is helpful, so that your virtual machine is not moving slowly and determines the processing power, memory, and storage capacity. Also, make sure that your inbound support rules are selected to determine which ports are accessible from the internet (RDP 3389).
</p>
<br />
<h2>Install and Enable Internet Information Services (IIS) in Windows with CGI </h2>
<p>
<img src="https://i.imgur.com/34jHtDx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the virtual machine, go to the virtual machine that you created and copy the Public IP address to login to a remote desktop connection (use the username and password created, when creating your virtual machine). Once you have logged into the remote desktop connection, go to the control panel, select Programs and Turn on or off Windows features and select the following to enable IIS with CGI on Windows 10. IIS with CGI is required to have the osTicket system installed on your virtual machine.
</p>
<br />
<h2>Download and Install PHP Manager for IIS, Rewrite Module, and create the directory C:\PHP</h2>
<p>
<img src="https://i.imgur.com/7kEgub5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After enabling CGI, download and install PHP Manager for IIS and the Rewrite Module to your virtual machine. Next, create a PHP folder in the windows directory (C:).
</p>
<br />
<h2>Download and unzip PHP 7.3.8 in PHP folder </h2>
<p>
<img src="https://i.imgur.com/U8k2kuk.png" height="90%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and extract all PHP files in to the previously created PHP folder under C:.
</p>
<br />
<h2>Download and install VC_redist and MySQL </h2>
<p>
<img src="https://i.imgur.com/EbyvS5F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install Microsoft Visual C++ and MYSQL. Ensure that MySQL is downloaded for a "Typical Setup" and Launch Configuration Wizard (after insall) is checked. Continue to install as Standard Configuration, select Install as a Windows service and add a password for MySQL (remember that login for later :smile:).
</p>
<br />
<h2>Open IIS as an Admin and Register PHP in IIS </h2>
<p>
<img src="https://i.imgur.com/KdMo93q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After installing all of the required files, open IIS and run IIS as an Administrator and register PHP in IIS. Double-click on PHP --> Click on Register PHP new version. Follow the sequence in the C:\ directory, PHP -> php.cgi.exe. Once PHP has been registered make sure to restart the server, by clicking "Restart Server".
</p>
<br />
<h2>Reload IIS and Install osTicket </h2>
<p>
<img src="https://i.imgur.com/TT8okiI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After restarting the server, Install the osTicket file from the installation folder. Extract and copy the "upload folder" to c:\inetpub\wwwroot (simply dragging and dropping the file and renaming it "osTicket")
</p>
<br />
<h2>Reload IIS and Browse to *:80 to review what extensions need to be enabled </h2>
<p>
<img src="https://imgur.com/LLuHhla.png" height="9%" width="90%" alt="Disk Sanitization Steps"/>
</p>
<p>
Reopen IIS, Go to sites, default, osTicket and click on "Browse *:80" to open osTicket in a web browser.
</p>
<br />
<h2>Enabled extensions in IIS</h2>
<p>
<img src="https://imgur.com/2IQ6WR2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to IIS, sites, Defualt, osTicket, double click PHP Manager, click on Enable or Disable an extension. Enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll and observe the changes in the osTicket site on the web browser
</p>
<br />

<h2>Rename: ost-config in PHP folder </h2>
<p>
<img src="https://imgur.com/F7El4Yy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go into file explorer and remove sample from "ost-sampleconfig.php by following C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php. Rename the file to "ost-config.php
</p>
<br />

<h2>Assign Permissions in ost-config.php and continue to setup osTicket </h2>
<p>
<img src="https://imgur.com/8ax66cQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to ost-config.php, right click, select properties, select security, and select advanced. Click on everyone, click on edit, and change to only read and read and view
</p>
<br />

<h2>Download and install HeidiSQL and continue to setup osTicket in the browser </h2>
<p>
<img src="https://imgur.com/R59XQRu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and install HeidiSQL. Add in password from MySQL setup to connect the database. Once, connected to the database, continue to fill out the following information for osTicket in the web browser and click "Install Now"
</p>
<br />

<h2>Clean Up</h2>
<p>
<img src="https://imgur.com/yRw4fvm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Delete "setup" folder in osTicket file and Set permissions to Read only in ost-config.php
</p>
<br />
