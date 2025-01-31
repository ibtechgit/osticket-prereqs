<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
To begin, create a Virtual Machine using the Microsoft Azure portal. For the protection of your personal computer, you will use the VM as a failsafe incase irriversible changes are accidentally made during the lab. The VM will provide a workstation that allows room to make mistakes while performing lab steps. 
  
Create a resource group within the Azure portal and title it "osTicket". Afterwards create a VM with 4 vcpus. (Be sure that all regions are corresponding - this example's location is East US)

  ![0](https://github.com/user-attachments/assets/3aa11e2b-6314-46c7-be93-47bbfac55461)




</p>
<br />
<p>
</p>
<p>Connect to your new VM by copying and pasting your VM's public IPv4 address into Remote Desktop Connection on Windows (Click start and search Remote Desktop Connection).
  Mac users will need to download Microsoft Remote Desktop. 
</p>
<img src="https://i.imgur.com/uLVKzxS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>
After connecting to your new VM you will need to enable IIS. You accomplish that by navigating to your computer's Control Panel, selecting "uninstall a program", choosing "Turn windows features on or off" and from the list that opens you enable "Internet Information Services"
</p>  
<img src="https://i.imgur.com/qtEnuWu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
</p>
<p>
Next, you need to install Web Platform Installer from the following link: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
  (All required downloads for the rest of the setup are in the link provided)
</p>
<img src="https://i.imgur.com/AxHCfQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
Open Web Installer Platform and from within the application you need to install MySQL 5.5. Next. install the (x86) PHP 7.3.
</p>
<img src="https://i.imgur.com/JJ8bZeJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
Download osTicket, then extract and copy the "upload" folder into c:\inetpub\wwwroot. Rename the "upload" folder to "osTicket"
</P>
<img src="https://i.imgur.com/TUGiSKi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>
Open IIS Manager (run as admin) and restart the server. Go to Sites > Default > osTicket. Click "Browse*.80" and osTicket webserver should open
</p>
<img src="https://i.imgur.com/4AkTkV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
In IIS manager be sure to enable the extensions that are marked with a red "X". To do this you have to go to Site > Default > osTicket and double click on PHP manager. Click on "Disable or enable an extension" and enable "php_intl.dll" & "php_opcache.dll". Finally, refresh the osTicket webserver. "Intl Extension" should now be enabled. 
</p>
<img src="https://i.imgur.com/APZgUTT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Navigate to "c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" and rename the file to "c:\inetpub\wwwroot\osTicket\include\ost-config.php".
Assign permissions to ost-config.php and Disable inheritance->Removeall.
New Permissions > Everyone > all
</p>
<img src="https://i.imgur.com/1nYaYGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Name the Helpdesk and provide an email that will receive emails from users who submit tickets. 
</p>
<img src="https://i.imgur.com/RmVk3q5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<p>Continue setting up osticket in the browser using the MySQL Database. osTicket MySQL Username: "root" MySQL Password: "root" Click “Install Now!”
This should complete your install and hopefully without any errors!
Then finally clean up (in Azure, either delete resource group and VM or be sure to hit "stop" so no costs are being incurred).

