<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This project outlines a quick overview of the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Downloadable files for this tutorial
- Instructions on how to create this lab
- A way to practice creating and solving tickets


<h2>Installation Steps</h2>


<p>
<img src="https://imgur.com/eGoyUbx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
These are the files that will needed to be installed to get osTicket up and running 
</p>
<br />

<p>
<img src="https://imgur.com/g8VQEZs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First we'll install IIS in windows
  To do this we need to go to control panel and click on programs
</p>
<br />

<p>
<img src="https://imgur.com/XYz6RyB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on turn features on or off
<br />


<p>
<img src="https://imgur.com/8zVti4y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
World Wide Web Services -> Application Development Features ->
check all boxes for Common HTTP Features
<br />


<p>
<img src="https://imgur.com/82OFAj5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console

<br />


<p>
<img src="https://imgur.com/ApIpnEc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here's some quick instructions when installing MySQL Server : 
  Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1. Not a best practice but simple to remember for a lab.

<br />


<p>
<img src="https://imgur.com/oIh8fXp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and the php file 
<br />


<p>
<img src="https://imgur.com/swGhqzH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Create a new folder inside c:drive for php then, move the intial php file to the c:drive php folder
<br />


<p>
<img src="https://imgur.com/yf5J6lL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

<br />


<p>
<img src="https://imgur.com/oAUDYxd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install osTicket v1.15.8
Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

<br />


<p>
<img src="https://imgur.com/ffpev3l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
oad IIS (Open IIS, Stop and Start the server)

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

<br />


<p>
<img src="https://imgur.com/J66wfSh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse, observe the changes



<br />


<p>
<img src="https://imgur.com/x7Y1txS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<br />


<p>
<img src="https://imgur.com/BVBRwX0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All


<br />


<p>
<img src="https://imgur.com/JNmMLwR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Im going to skip some steps since this has gotten quite long... you can look for the rest of the installation files on youtube. For now we'll get to running osTicket. 
  However, you will need to : 
  Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”

Continue Setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”
Use this link to get to osTicket http://localhost/osTicket/scp/login.php

<br />


<p>
<img src="https://imgur.com/HeBssxs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can configure Configure Roles
Admin Panel -> Agents -> Roles
Supreme Admin


<br />


<p>
<img src="https://imgur.com/beagSMS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Departments
Admin Panel -> Agents -> Departments
System Administrators

<br />



<p>
<img src="https://imgur.com/ub9uJqh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Teams
Admin Panel -> Agents -> Teams
Level I Support
Level II Support


<br />



<p>
<img src="https://imgur.com/zqHh3Wz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Agents (workers)
Admin Panel -> Agents -> Add New
Jane
John



<br />




<p>
<img src="https://imgur.com/qbIS4Dq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Users (customers)
Agent Panel -> Users -> Add New
Karen
Ken


<br />



<p>
<img src="https://imgur.com/nj0HytB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure SLA
Admin Panel -> Manage -> SLA
Sev-A (1 hour, 24/7)
Sev-B (4 hours, 24/7)
Sev-C (8 hours, business hours)


<br />



<p>
<img src="https://imgur.com/MW419YK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure Help Topics
Admin Panel -> Manage -> Help Topics
Business Critical Outage
Personal Computer Issues
Equipment Request
Password Reset



<br />



<p>
<img src="https://imgur.com/nj0HytB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Configure SLA
Admin Panel -> Manage -> SLA
Sev-A (1 hour, 24/7)
Sev-B (4 hours, 24/7)
Sev-C (8 hours, business hours)


<br />


<p>
<img src="https://imgur.com/tEsdVRS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we can practice creating and solving tickets 
Link to that site is here http://localhost/osTicket/


<br />



<p>
<img src="https://imgur.com/SB27sJP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here's an example of some tickets that were solved and closed


<br />


<p>
*Special note I forgot* You can give permissions Allow anyone to create tickets
Admin Panel -> Settings -> User Settings
Registration Required: Require registration and login to create tickets

</p>
<p>
Here's an example of some tickets that were solved and closed


<br />
