
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Prerequisites and Installation</h1>
This guide outlines the essential requirements and procedures for installing osTicket, an open-source help desk ticketing system.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- IIS
- PHP Manager
- Rewrite Module
- VC_redistx86
- MySQL 5.5.62
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
<h3>&#9312; Create a Virtual Machine on Azure</h3>
The first step is to create a Virtual Machine (VM) on Azure. 
Choose the image or base operating machine as Windows 10 Pro, version 22H2.</p>
<p>
<img width="800" src="https://imgur.com/INXIICl.png">

<p>
</p>
<p>
<strong> NOTE: Make sure to set the size to either 2 or 4 vcpus and 16 GiB memory. 
Confirm that RDP (3389) is allowed in "Select inbound ports" to allow Remote Desktop access to the VM.</strong> </p>
<p>
<img width="750" src="https://imgur.com/aTcFD7k.png">



</p>
<br />

<p>
</p>
<p>
<h3>&#9313; Review and Create </h3>
<p>Click on the last check box to confirm an eligible Windows 10 license, then proceed to "Review + Create". A validation process will occur before being able to create.</p>

</p>
<br>
<h3>&#9314; Find your VM's public IP address</h3>
<p></p>Allow a small time window for your deployment to complete, then locate your VM's public IP address and copy it.</p>
<p>
<img width="700" src="https://imgur.com/9HWXoRu.png">


</p>
<p>
<h3>&#9315; Connect to your VM using the Remote Desktop Connection app</h3>
<p>Open your Remote Desktop Connection app and paste the VM's IP address, then login credentials used to create the VM.</p>
<p>
<img width="700" src="https://imgur.com/TL41GIq.png">


</p>
<br />
<h3>&#9316; Enable IIS </h3>
<p> Once the VM is open, we will need to install/enable IIS. Open Control Panel -> Programs -> Turn Windows features on or off</p>
<p> <img width="750" src="https://imgur.com/Llx72Yj.png">

  
</p>
<p>Enable and expand the following features:</p>
<p><img width="400" src="https://imgur.com/DdrwoVU.png">
</p>
<p> [X] Internet Information Services</p>
<p>[X] Web Management Tools </p>
<p>[X] IIS Management Console </p>
<p>[X] World Wide Web Services  </p>
<p>[X] Application Development Features </p>
<p>[X] CGI</p>
<p>[X] Common HTTP Features</p>
<br>
<p> Click okay and the features should be enabled.</p>
<br>
<p> <strong> NOTE: To test if the changes were applied succesfully, type "127.0.0.1" on your browser and this page below should appear. </strong></p>
<img width="900" src="https://imgur.com/nqv8e9h.png">
<br> <br>
<h3>&#9317; Download and Install PHP Manager</h3>
<p> Download and install PHP manager from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>(PHPManagerForIIS_V1.5.0.msi) 
</p> <br>
<p><img width="386" src="https://imgur.com/DbU0lk6.png">
</p> 
<br>
<h3>&#9318; Download and Install the Rewrite Module</h3>
<p> Download and install the rewrite module (rewrite_amd64_en-US.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> </p>
<p><img width="386" alt="rewrite module" src="https://imgur.com/dM5GWpc.png"></p>
<h3>&#9319; Create a new directory</h3>
<p>Proceed to File Explorer and create the directory in "C:" naming the new folder "PHP" </p>
<img width="647" alt="PHP" src="https://imgur.com/AP3sxXs.png">
<br>
<br>
<h3>&#9320; Download and install PHP 7.3.8 </h3>
<p> Download and install php-7.3.8-nts-Win32-VC15-x86.zip from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> and extract the contents into the newly created PHP folder </p>
<img width="720" alt="PHP zip" src="https://imgur.com/AgERChE.png">
<br>
<h3>&#9321; Download and install VC_redist.x86.exe </h3>
<br>
<h3>&#9322; Download and install MySQL 5.5.62 </h3>
<p> Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>  and select the following configurations:</p>
<p> Typical Setup -> Launch Configuration Wizard after install -> Standard Configuration
</p>
<br>
<img width="420" alt="mysql" src="https://imgur.com/UXdU64D.png">
<br>
<h3>&#9323; Launch IIS as an administrator</h3>
<p> Search IIS in the Windows search bar, then right click and select "Open as Administrator"</p>
<br>
<h3>&#9324; Register PHP Manager </h3>
<br>
<img width="720" alt="PHP registration 2" src="https://imgur.com/BEmvAuY.png">

<br>
<br>
<p><strong> NOTE: Registration will require you to provide a path to "php-cgie.exe". Lead it to the PHP folder previously created and you will find the file "php-cgi"
</strong></p>
<br>
<img width="700" alt="PHP path " src="https://imgur.com/Pewjk2r.png">

<br>
<p>
</p> 
<h3>&#9325; Restart the IIS server</h3>
<p> The restart button can be found on the right side of the window under Actions -> Manage Server.</p>
<br>
<img width="623" alt="Restart IIS" src="https://imgur.com/KHl2nlC.png">
<br>
<br>
<h3>&#9326; Download and install osTicket</h3>
<p> Download and install osTicket v1.15.8 from the installation files and extract the contents to c:\inetpub\wwwroot </p>
<br>
<img width="547" alt="inetpub" src="https://imgur.com/KqDNCsS.png">
<br>
<br>
<p> Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</p>
<br>
<h3>&#9327; Restart the IIS Again.</h3>
<img width="623" alt="Restart IIS" src="https://imgur.com/KHl2nlC.png">
<br>
<br>
<h3>&#9328; Launch osTicket </h3>
<p>Under Connections in IIS, VM-osTicket -> Sites -> Default Web Site -> osTicket</p>
<img width="623" alt="osTicket" src="https://imgur.com/bgZrJzV.png">
<p></p>
<p><strong>NOTE: Click on osTicket</strong></p>

<h3>&#9329; Select Browse *80 to launch osTicket</h3>
<p> On the right side of the window, under Actions -> Manage Folder -> Click on Browse *:80 (http) </p>
<img width="623" alt="browse80" src="https://imgur.com/yiQjEcK.png">
<br>
<br>
<p><strong>This should lead to osTicket opening in a separate Windows broswer</strong>.</p>
<br>
<br>
<img width="664" alt="osTicket browser" src="https://imgur.com/yOa0Jy8.png">
<br>
<br>
<h3>&#9330; Enable extensions</h3>
<p>Open IIS -> PHP Manager -> Select "Enable or Disable Extension". </p>
<p>Enable the following extensions:</p>
<p>[X]Enable: php_imap.dll</p>
<p>[X]Enable: php_intl.dll</p>
<p>[X]Enable: php_opcache.dll</p>
<img width="273" alt="php enable 2" src="https://imgur.com/8QO0yIO.png">
<br>
<br>
<h3>&#9331; Refresh osTicket</h3>

<p>After refreshing your web browser on osTicket, notice how more features are now available to use.</p>
<img width="608" alt="OSticket changes" src="https://imgur.com/bdJ05kP.png">
<br>
<br>

<h3>&#12881; Rename ost-config.php</h3>

<p> Under c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename "ost-sampleconfig.php" to "ost-config.php"</p>
<img width="527" alt="ostconfig rename" src="https://imgur.com/yP1YTT0.png">
<br>
<br>

<h3>&#12882; Change ost-config.php permissions</h3>

<p>Change ost-config.php permissions (right click)</p>
<p>Properties -> Security -> Advance -> Disable Inheritance</p> 
<p>Select "remove all inherited permissions" and add everyone as a principal. Select all boxes to ensure all permissions are granted. </p>
<img width="571" alt="Permissions" src="https://imgur.com/mANNCMT.png">

<h3>&#12883; Continue osTicket installation</h3>

<p> Continue through osTicket filling out only the first half of the page to this point.</p>
<img width="611" alt="osticket signup" src="https://imgur.com/m7WratO.png">
<br>
<br>
<p><strong>NOTE: The database credentials we'll fill out later.</strong> </p>
<br>

<h3>&#12884; Download and install Heidi SQL from the installation files</h3>

<p>Open Heidi SQL and create a new session. Make sure to fill in the username as root and create a password. After filling up your credentials now click open and a new session should show up.
</p>

<h3>&#12885; Create new database </h3>

<p>On the left side of the window, right click on "Unnamed" and create a new database named "osTicket".</p>
<img width="512" alt="SQL" src="https://imgur.com/AbElzBn.png">
<br>
<br>

<h3>&#12886; Finish osTicket Sign-Up</h3>

<p>Revert back to your osTicket browser and fill out the incomplete credentials.</p>
<img width="375" alt="osticket final signup" src="https://imgur.com/B2A1SMM.png">


<h3>&#12887; Finalize osTicket installation</h3>

<p>Click install and osTicket should begin to setup. </p>


<br>
<br>
<h1>Congratulations!! &#127881; you just installed osTicket</h1>



































