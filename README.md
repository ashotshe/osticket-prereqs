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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.) The first thing you are going to want to do is create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro, version 22H2. 
        Note, you will want to create a virtual machine with atleast 2 vcpus and 8 gbs of memory.
	
        1. Open Azure and navigate to Virtual Machines.
	
	2.	Click Create a Virtual Machine.
 ---
 
 ![ade1](https://github.com/user-attachments/assets/d4fb92ed-bfff-4a5d-8360-129bbbc8e1d6) 
 
 ---
	3.	Choose or create a Resource Group (name it as you prefer).

	4.	Select your desired Region.
 
	5.	Under Image, choose Windows 10 Pro.
 ---
 
 ![ade2](https://github.com/user-attachments/assets/4cf99ac6-b259-4c49-95f7-71f864e9f6e8)
 
 ---
	6.	Select an appropriate size—I recommend at least 2 vCPUs for better performance.
 
	7.	Create a Username and Password (e.g., labuser and Cyberlab123!).
 ---
 
 ![ade3](https://github.com/user-attachments/assets/094eb878-0b0f-474c-9902-4293cb6de831)
 
 ---
	8.	Complete the remaining settings as needed, then click Create to deploy the virtual machine.
 
	9.	Once the VM is up and running, navigate to its home screen and locate the Public IP Address.
 ---
 
 ![a4](https://github.com/user-attachments/assets/693dddb3-c309-45e4-b363-98ff9a773473)
 
 ---
	10.	Use Remote Desktop (RDP) to connect to the virtual machine using the public IP, along with the username and password you created.

---

![ade5](https://github.com/user-attachments/assets/7e0a10f7-3440-4834-ab3c-5043f76a0e0a)

---

2.) Once you have created your virtual machine you will want to conncet to it by using the public ip address the vm is setup with. You will connect using the remote desktop connection app. 
</p>
<br />

<p>
<img src="https://imgur.com/MAhXK2e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://imgur.com/Zf2jw07.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select, Turn Windows features on and off.

<p>
<img src="https://imgur.com/fGXMpx4.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/LBGkAw6.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
4.) You will want to install / enable IIS in Windows with CGI and Common HTTP Features
  - Navigate to: Internet Information Services (IIS) -> World Wide Web Services -> Application Development Features -> Check the box for [X] CGI  and [X] Common HTTP Features, then click OK.
  
<p>
<img src="https://imgur.com/LQjw9le.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/pbPeHb1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***NOTE*** Make sure all Common HTTP Features are checked.
 
 To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 
  It should look something like this. 
  
<p>
<img src="https://imgur.com/eICujoq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
5.) Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  Go through the install wizard and complete the install.
  
6.) Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
  
7.) Create a folder in the C drive called PHP.
  
8.) From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
---
![ade12](https://github.com/user-attachments/assets/ed13d3c1-cee8-494b-95b2-36945b7ef696)
![a15](https://github.com/user-attachments/assets/9609f915-8e98-4b72-97f0-61c6fba8e239)
![a16](https://github.com/user-attachments/assets/8ab6b478-9a95-4c34-bb4a-7db6d3b2c854)
---
10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  Run the setup wizard:
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

  Make the new root password: Password1
  
<p>
<img src="https://imgur.com/KxcUy7C.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Execute the process on the next page.
  
<p>
<img src="https://imgur.com/i7sn6hT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator.
  The program should look like this.
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) We will now want to register PHP from within IIS.
  Click on PHP Manager
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Register new PHP version.
  
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
You will want to provide a path to the php executable file (php-cgi.exe)). 
  Go to C Drive -> PHP -> click on php-cgi file.
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Restart the IIS server.
  
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
13.) Install osTicket v1.15.8
  -Download osTicket from the Installation Files Folder
  -Extract and copy "upload" folder to c:\inetpub\wwwroot
  -Within c:\inetpub\root, Rename "upload" to "osTicket"
---
![ade16](https://github.com/user-attachments/assets/2a23b13b-b6a8-4392-91d6-5cacddb3937e)
![ade17](https://github.com/user-attachments/assets/8679b806-a1e0-4c9c-8d73-37b7329f8836)
![ade18](https://github.com/user-attachments/assets/4ee9906a-88cd-416d-9c59-ae99587ab691)
---
  Reload IIS again.
  
14.) On IIS go to sites -> Default -> osTicket
  -On the right, click “Browse *:80”
  
![ade19](https://github.com/user-attachments/assets/49b376de-8ee2-4c60-9a86-196e72d18268)

  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://imgur.com/eJIsGTn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  To enable the extensions:
  -Go back to IIS, sites -> Default -> osTicket
  -Double click PHP manager
  -Click "Enable or disable an extension"
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We will want to enable three extensions from here.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
<img src="https://imgur.com/cOem7Nb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
15.) Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder.
  Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
  We are going to rename the ost-sampleconfig.php to ost-config.php
  
  Now that we have renamed the files, right click on the file and go to properties.
  From there click security, click on advance, and disable the inheritance.
  We will select Remove all inherited permissions from this object.
---
![ade22](https://github.com/user-attachments/assets/d4586b30-ffe6-4f49-b19f-056dba724116)
![a35](https://github.com/user-attachments/assets/40138abd-e1e7-4a4f-bfc7-3b3297031842)
![ade23](https://github.com/user-attachments/assets/ba9d74b4-dce1-43cb-916f-f15da22db145)
![ade24](https://github.com/user-attachments/assets/c9cac959-9527-415e-82bf-f01be1dcee89)
---
  Now we will add new permissions.
  
  Click Add
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Select a principal
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
 Type "Everyone" in the box.
  
<p>
<img src="https://imgur.com/F4H3ppM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://imgur.com/rbbGqwB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Click Apply and Ok.
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page.
  Fill out the page as required except the Database Settings at the bottom of the page. We will get to that. 
  
  We will want to download and install HeidiSQL from the Installation Files. 
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  When the program is open we will create a new session in it.
---
![ade26](https://github.com/user-attachments/assets/e3a567ee-c895-47d7-95c0-856b77190e2f)
---
<p>
<img src="https://imgur.com/g5M1i61.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We want to make sure the username is root and the password is Password1.
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
---
![ade27](https://github.com/user-attachments/assets/0229ac6f-8371-407b-b327-7a4f0bfb9527)
![ade28](https://github.com/user-attachments/assets/5c1a57bd-8fc5-4a61-a942-6288fe300bc0)
---
  Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.
  
  We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  The last step is to do some clean up. We will want to delete the setup folder in our system. 
  -Delete: C:\inetpub\wwwroot\osTicket\setup
  Only delete the setup folder and nothing else.
  
  We then will want to set the permissions back to "Read" only in the ost-config.php file.
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  The last step after that is to login to osTicket on the browser.
---
![ade29](https://github.com/user-attachments/assets/785e3831-02ce-4426-bce4-df0e789887df)
---
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  Congrats! You have now successfully installed and setup osTicket!
