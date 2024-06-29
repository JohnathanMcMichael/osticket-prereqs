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

- Item 1: Virtual Machine in Azure
- Item 2: PHP Manager for IIS
- Item 3: Rewrite Module
- Item 4: PHP 7.3.8
- Item 5: VC_redist.x86.exe
- Item 6: MySQL 5.5.62
- Item 7: osTicket v1.15.8
- Item 8: HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/wpgrLTk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create an Azure Virtual Machine running Windows 10, 4 vCPUs. 
</p>
<br />

<p>
<img src="https://i.imgur.com/9NEWxb8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/LhkoGvC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open Installation Files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 . 
We will use these files to install osTicket and some of the dependencies. 
Install / Enable IIS in Windows WITH CGI and Common HTTP Features and IIS Management Console. 
<br />

<p>
<img src="https://i.imgur.com/zJKyizQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/vXjuudq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module (rewrite_amd64_en-US.msi). 
</p>
<br />

<p>
<img src="https://i.imgur.com/KTsjXK7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP. 
</p>
<br />

<p>
<img src="https://i.imgur.com/QCsoc3z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
</p>
<br />

<p>
<img src="https://i.imgur.com/EC2Yd3N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download and install VC_redist.x86.exe.
</p>
<br />

<p>
<img src="https://i.imgur.com/gb3r23Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). 
Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Password1 . 
</p>
<br />

<p>
<img src="https://i.imgur.com/H16HPgV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin. Register PHP from within IIS. Reload IIS (Open IIS, Stop and Start the server). 
</p>
<br />

<p>
<img src="https://i.imgur.com/nsLrBgk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download and install osTicket v1.15.8. 
Extract and copy “upload” folder to c:\inetpub\wwwroot. 
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”. 
Reload IIS (Open IIS, Stop and Start the server). 
</p>
<br />

<p>
<img src="https://i.imgur.com/rSMCabj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket. 
On the right, click “Browse *:80”. 
Note that some extensions are not enabled. 
</p>
<p>
<img src="https://i.imgur.com/j1PkNSA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
Go back to IIS, sites -> Default -> osTicket. 
Double-click PHP Manager. 
Click “Enable or disable an extension”. 
Enable: php_imap.dll. 
Enable: php_intl.dll. 
Enable: php_opcache.dll. 
</p>
<p>
<img src="https://i.imgur.com/4ywOFzr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Refresh the osTicket site in your browser, observe the changes. 
</p>
<br />

<p>
<img src="https://i.imgur.com/kJZM19d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename: ost-config.php : 
</p>
<p>
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
</p>
<p>
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
<img src="https://i.imgur.com/kfKBPmi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign Permissions: ost-config.php. 
Disable inheritance -> Remove All. 
New Permissions -> Everyone -> All. 
</p>
<br />

<p>
<img src="https://i.imgur.com/aGm4M3H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osTicket in the browser (click Continue). 
(Your Name) Helpdesk. 
Default email (receives email from customers). 
</p>
<br />

<p>
<img src="https://i.imgur.com/klZ8mAG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files, download and install HeidiSQL. 
Open Heidi SQL. 
Create a new session, root/Password1. 
Connect to the session. 
Create a database called “osTicket”. 
</p>
<br />

<p>
<img src="https://i.imgur.com/TcwoO5b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue Setting up osticket in the browser. 
MySQL Database: osTicket. 
MySQL Username: root. 
MySQL Password: Password1. 
Click “Install Now!”. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ycRHDZo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/cLKLOzu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, hopefully it is installed with no errors! 
Browse to your help desk login page: http://localhost/osTicket/scp/login.php . 
End Users osTicket URL: 
http://localhost/osTicket/ 
</p>
<br />

<p>
<img src="https://i.imgur.com/zwOXZMQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/vBQHx9J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Clean up: 
Delete: C:\inetpub\wwwroot\osTicket\setup . 
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php . 
</p>
<br />
