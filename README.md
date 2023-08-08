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

- Task 1 Create DC-1 (Domain Controller) and Client-1
- Task 2 Ping DC
- Task 3 Setup Active Directory 
- Task 4 Create Jane Doe Admin
- Task 5 login as Jane Doe
- Task 6 Change DNS
- Task 7 Import and run script for authorized users
- Task 8 cep.jum chosen from list
- Task 9 Lockout cem.kaf and unlock for test


<h2>1. Create DC-1 and Client-1<h2>

<p>
<img src="https://imgur.com/E9m0Z2o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
To begin, we are creating virtual machines through Azure for both DC1 and Client1 that will serve as the sandbox for the entire lab. Be sure to confirm that the virtual network is identical for both of the machines. 
 
  * I am working on a macbook💻. 

</p>
<br />
<h2>2. Ping DC<h2>
<p>
<img src="https://imgur.com/SnnQ7oN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Now that both virtual machines are created we are going to open up the command line and attempt to ping DC1 from the client machine. This attempt will inevitably fail. Why? The (Internet Control Message Protocol) ICMP for our DC is disabled and needs to be enabled. Navigate to the windows defender firewall, choose the inbound rules, filter for protocol and find the core diagnostics networking echo. enable it and check the ping again from the client machine. The ping should no longer time out. 


</p>
<br />
<h2>3. Setup Active Directory<h2>
<p>
<img src="https://imgur.com/qvca5tf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
After that we will setup and install Active Directory from the DC and set the domain. Open the task manager if it is not already open. Click the add roles and features option and begin the installation of Active Directory including its' extension files. During this process you will be asked to create a domain name for this network of users you are preparing to create. 

</p>
<br />

<h2>4. Create Jane Doe Admin</h2>
<p>
<img src="https://imgur.com/Gy4TarL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
At this point we are prepared to setup ADMIN and EMPLOYEE users/groups. Through the task manager navigate to the active directory users and computers option. Under your domain create two groups; one for ADMIN and another for EMPLOYEES. In the ADMIN group create a new user, this user is going to be Jane Doe.  
</p>
<br />

<h2>5. Login as Jane Doe</h2>
<p>
<img src="https://imgur.com/i367umy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>


<h2>6. Change DNS</h2>
<p>
<img src="https://imgur.com/BQf3SrN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>


<h2>7. Import and run script for authorized users</h2>
<p>
<img src="https://imgur.com/obKxi6E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>


<h2>8. cep.jum chosen from list<h2>
<p>
<img src="https://imgur.com/TdTUCHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>




<h2>9. Lockout cem.kaf and unlock for test</h2>
<p>
<img src="https://imgur.com/8a7tCcd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>

 
