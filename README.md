
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
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
The first step is to create a virtual machine on Azure. 
Choose the image or base operating machine as Windows 10 Pro, version 22H2.</p>
<p>
<img width="800" src="https://imgur.com/7KWTlha.png">

<p>
</p>
<p>
<strong> NOTE: Make sure to set the size to either 2 or 4 vcpus and 16 GiB memory. 
And confirm that RDP (3389) is allowed in "Select inbound ports" in order to allow Remote Desktop access to the VM.</strong> </p>
<p>
<img width="750" src="https://imgur.com/0cSzcOF.png">



</p>
<br />

<p>
</p>
<p>
<h3>&#9313; Review and Create </h3>
<p>Click on the last check box to confirm an eligible Windows 10 license, then proceed to "Review + Create". A validation process will occur then once it has passed, continue to create.</p>

</p>
<br>
<h3>&#9314; Find your VM's public IP address</h3>
<p></p>Allow some time for your deployment to complete, then find your VM's public IP address and copy it.</p>
<p>
<img width="700" src="https://imgur.com/N8uWjI4.png">


</p>
<p>
<h3>&#9315; Connect to your VM using the Remote Desktop Connection app</h3>
<p>Open your Remote Desktop Connection app and paste the VM's IP and login with the same login credentials used to create the VM.</p>
<p>
<img width="700" src="https://imgur.com/YGLRE3X.png">


</p>
<br />
<h3>&#9316; Enable IIS </h3>
<p> Once the VM is open, we will have to install / enable IIS. Go to the Control Panel and open the programs applet. Under programs, select "Turn Windows features on or off".</p>
<p> <img width="750" src="https://imgur.com/2PPYmYx.png">

  
</p>
<p>Next, you will have to enable and expand the following features:</p>
<p><img width="400" src="https://imgur.com/pMlyKR0.png">
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
<p> <strong> NOTE: To quickly test if the changes were applied succesfully, simply type 127.0.0.1 on your browser and the page below should appear. </strong></p>
<img width="900" src="https://imgur.com/nqv8e9h.png">
<br> <br>
<h3>&#9317; Download and Install PHP Manager</h3>
<p> Simply download and install PHP manager from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>(PHPManagerForIIS_V1.5.0.msi) 
</p> <br>
<p><img width="386" src="https://imgur.com/DbU0lk6.png">
</p> 
<br>
<h3>&#9318; Download and Install the Rewrite Module</h3>
<p> Download and install the rewrite module (rewrite_amd64_en-US.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> </p>
<p><img width="386" alt="rewrite module" src="https://imgur.com/dM5GWpc.png"></p>
<h3>&#9319; Create a new directory</h3>
<p>Proceed to File Explorer and create the directory C:\PHP </p>
<img width="647" alt="PHP" src="https://imgur.com/o6lzV8L.png">
<br>
<br>
<h3>&#9320; Download and install php-7.3.8-nts-Win32-VC15-x86.zip </h3>
<p> Download and install php-7.3.8-nts-Win32-VC15-x86.zip from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a> and unzip the contents into the newly created C:\PHP </p>
<img width="720" alt="PHP zip" src="https://imgur.com/qTk4Jvs.png">
<br>
<h3>&#9321; Download and install VC_redist.x86.exe </h3>
<br>
<h3>&#9322; Download and install MySQL 5.5.62 </h3>
<p> Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> installation files </a>  and select the following configurations; </p>
<p> [X] Typical Setup</p>
<p>[X] Launch Configuration Wizard after install </p>
<p>[X]Standard Configuration 
</p>
<br>
<img width="420" alt="mysql" src="https://imgur.com/7bAjTu8.png">
<br>
<h3>&#9323; Launch IIS as an administrator</h3>
<p> Search for IIS in the windows search bar and right click it and select open as administrator</p>
<br>
<h3>&#9324; Register PHP Manager </h3>
<br>
<img width="720" alt="PHP registration 2" src="https://imgur.com/TqBGNXk.png">

<br>
<br>
<p><strong> NOTE: Registration will require you to provide a path to "php-cgie.exe". Simply lead it to the PHP folder previously created and you will find the file it is asking for. 
</strong></p>
<br>
<img width="700" alt="PHP path " src="https://imgur.com/XhTcV2b.png">

<br>
<p>
</p> 
<h3>&#9325; Restart the IIS server</h3>
<p> The restart button can be found on the right side of the window.</p>
<br>
<img width="623" alt="Restart IIS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/89c60a3c-2556-4909-ad78-4ae501b38da1">
<br>
<br>
<h3>&#9326; Download and install osTicket</h3>
<p> Download and install osTicket v1.15.8 from the installation files and extract the contents to c:\inetpub\wwwroot </p>
<br>
<img width="547" alt="inetpub" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/bea57cd3-27f4-4564-9cb4-1bfd7492b6ca">
<p> Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”</p>
<br>
<br>
<h3>&#9327; Restart the IIS server again.</h3>
<img width="623" alt="Restart IIS" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/89c60a3c-2556-4909-ad78-4ae501b38da1">
<br>
<br>
<h3>&#9328; Launch osTicket </h3>
<p>On the left hand side of IIS, Expand on the VM name -> Sites - > Default Website -> osTicket </p>
<img width="623" alt="osTicket" src="https://imgur.com/xcY5ZMu.png">
<p></p>
<p><strong>NOTE: Make sure to click on osTicket</strong></p>
<p><strong>.</strong></p>
<p><strong>.</strong></p>
<p><strong>.</strong></p>
<h3>&#9329; Click on Browse *80 to launch osTicket</h3>
<p> On the right side of the window, click on browse *80 </p>
<img width="623" alt="browse80" src="https://imgur.com/VrPM2ii.png">
<br>
<br>
<br>
<p><strong>This should then lead to your browser opening osTicket</strong>.</p>
<br>
<br>
<img width="664" alt="osTicket browser" src="https://imgur.com/yOa0Jy8.png">
<br>
<br>
<br>
<h3>&#9330; Enable extensions</h3>
<p>Open IIS and click on PHP Manager and select "enable or disable extension". </p>
<p>Enable the following extensions:</p>
<p>[X]Enable: php_imap.dll</p>
<p>[X]Enable: php_intl.dll</p>
<p>[X]Enable: php_opcache.dll</p>
<img width="273" alt="php enable 2" src="https://imgur.com/zEFHkoN.png">
<br>
<br>
<br>
<h3>&#9331; Refresh osTicket</h3>

<p>Refresh the osTicket page on the browser and notice some extensions will now appear active.</p>
<img width="608" alt="OSticket changes" src="https://imgur.com/bdJ05kP.png">
<br>
<br>
<br>

<h3>&#12881; Rename ost-config.ph</h3>

<p> Under C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename "ost-sampleconfig.ph" to "ost-config.ph"</p>
<img width="527" alt="ostconfig rename" src="https://imgur.com/yP1YTT0.png">
<br>
<br>
<br>

<h3>&#12882; Change ost-config.ph permissions</h3>

<p>Change ost-config.php permissions by right clicking and selecting</p>
<p>Properties -> Security -> Advance -> Disable inheritance</p> 
<p>Select remove all inherited permissions and add everyone as a principal. Select all boxes to ensure all permissions are granted. </p>
<img width="571" alt="Permissions" src="https://imgur.com/mANNCMT.png">
<p><strong>.</strong></p>
<p><strong>.</strong></p>

<h3>&#12883; Continue osTicket installation</h3>

<p> Continue the osTicket installer on your browser by filling the first half of the page.</p>
<img width="611" alt="osticket signup" src="https://imgur.com/m7WratO.png">
<br>
<br>
<p><strong>NOTE: Don't worry about the database credentials. We'll fill those out later.</strong> </p>
<br>
<p><strong>.</strong></p>
<p><strong>.</strong></p>

<h3>&#12884; Download and install Heidi SQL from the installation files</h3>

<p>Open Heidi SQL and create a new session. Make sure to fill in the username as root and create a password. After filling up your credentials now click open and a new session should show up.
</p>
<p><strong>.</strong></p>
<p><strong>.</strong></p>
<p><strong>.</strong></p>

<h3>&#12885; Create new database </h3>

<p>On the left side of the window, right click on "Unnamed" and click create new database and name it "osTicket".</p>
<img width="512" alt="SQL" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/eaa5aa61-2eea-4406-a7d7-fa77616dbe16">
<br>
<br>
<p><strong>.</strong></p>
<p><strong>.</strong></p>

<h3>&#12886; Finish signing up</h3>

<p>Then go back to your osTicket browser and fill up the missing credentials. 
It should look something like this.</p>
<img width="308" alt="osticket final signup" src="https://github.com/kirkgacias/osticket-prereqs/assets/158519921/a185574b-775a-49fb-9468-c5d82033e823">
<p><strong>.</strong></p>
<p><strong>.</strong></p>

<h3>&#12887; Finalize osTicket installation</h3>

<p>Click install and osTicket should begin setting up. </p>


<br>
<br>
<h1>Congratulations!! &#127881; you just installed osTicket</h1>



































