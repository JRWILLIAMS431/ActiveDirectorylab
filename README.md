# Active Directory lab
This tutorial outlines the setup, installation, and use of the Active Directory within a virtual machine. Join me 🤝<br />


<h2>Video Demonstration</h2>

- ### [YouTube: Active Directory Lab](https://youtu.be/kYxOiwbWP2U)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory 
- Powershell IDE

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Task 1 Create DC-1 and Client-1
- Task 2 Ping DC
- Task 3 Setup Active Directory 
- Task 4 Create Jane Doe Admin
- Task 5 login as Jane Doe
- Task 6 Change DNS
- Task 7 Import and run script for authorized users
- Task 8 cep.jum chosen from list
- Task 9 Lockout cem.kaf and unlock for test


<h2>Create DC-1 and Client-1<h2>

<p>
<img src="https://imgur.com/E9m0Z2o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin, we are creating virtual machines through Azure for both DC1 and Client1 that will serve as the sandbox for the entire lab. Be sure to confirm that the virtual network is identical for both of the machines. 
 
  * I am working on a macbook💻. 

</p>
<br />
<h2>Ping DC<h2>
<p>
<img src="https://imgur.com/SnnQ7oN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now that both virtual machines are created we are going to open up the command line and attempt to ping DC1 from the client machine. This attempt will inevitably fail. Why? The (Internet Control Message Protocol) ICMP for our DC is disabled and needs to be enabled. Navigate to the windows defender firewall, choose the inbound rules, filter for protocol and find the core diagnostics networking echo. enable it and check the ping again from the client machine. The ping should no longer time out. 


</p>
<br />
<h2>Setup Active Directory<h2>
<p>
<img src="https://imgur.com/qvca5tf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After that we will setup and install Active Directory from the DC and set the domain. Open the task manager if it is not already open. Click the add roles and features option and begin the installation of Active Directory including its' extension files. During this process you will be asked to create a domain name for this network of users you are preparing to create. 

</p>
<br />

<p>
<img src="https://i.imgur.com/rUWsJGl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once created, your osTicket account should have all of the neccasary files uploaded and enabled to run properly. Now browse to your helpdesk login page and attempt to login to the account.   
</p>
<br />

<p>
<img src="https://i.imgur.com/6u4Vg3F.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations, you have successfully logged into your osTicket portal. Now we will finish with a bit of cleanup🧹. 

  Delete: C:\inetpub\wwwroot\osTicket\setup

  Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  
  * ( logout out of the virtual machine and delete the resource group if you want to avoid any unwanted charges to your Azure account)

</p>
<br />
