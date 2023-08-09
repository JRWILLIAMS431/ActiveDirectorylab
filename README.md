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

<h2>2. Ping DC<h2>
<p>
<img src="https://imgur.com/SnnQ7oN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Now that both virtual machines are created we are going to open up the command line and attempt to ping DC1 from the client machine. This attempt will inevitably fail. Why? The (Internet Control Message Protocol) ICMP for our DC is disabled and needs to be enabled. Navigate to the windows defender firewall, choose the inbound rules, filter for protocol and find the core diagnostics networking echo. enable it and check the ping again from the client machine. The ping should no longer time out. 


<h2>3. Setup Active Directory<h2>
<p>
<img src="https://imgur.com/k4Fg3fo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
After that we will setup and install Active Directory from the DC and set the domain. Open the task manager if it is not already open. Click the add roles and features option and begin the installation of Active Directory including its' extension files. During this process you will be asked to create a domain name for this network of users you are preparing to create. 


<h2>4. Create Jane Doe Admin</h2>
<p>
<img src="https://imgur.com/Gy4TarL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
At this point we are prepared to setup ADMIN and EMPLOYEE users/groups. Through the task manager navigate to the active directory users and computers option. Under your domain create two groups; one for ADMIN and another for EMPLOYEES. In the ADMIN group create a new user, this user is going to be Jane Doe.  


<h2>5. Login as Jane Doe</h2>
<p>
<img src="https://imgur.com/i367umy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
After creating the Jane Doe ADMIN user, logoff of client 1 and sign back in to the vm as Jane Doe. When doing so, make sure that you attach Jane Doe to your domain when typing the username. 

<h2>6. Change DNS</h2>
<p>
<img src="https://imgur.com/BQf3SrN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
It is time to change the DNS(Domain Name System) of client 1 to match the domain controller. In the client 1 vm open up the commnad line and type ipconfig/ all  which will show further configuration details about the client 1 vm. Check the current DNS and close the vm. Navigate to the DC networking tab in the azure cloud and copy the NIC IP address. From there navigate to the client 1 DNS server tab and paste the address. SAVE IT. Log back in to the client vm and check the DNS in the command line to confirm the change. 

<h2>7. Import and run script for authorized users</h2>
<p>
<img src="https://imgur.com/obKxi6E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
The Hiring Fair has begun! The next step is to import and run a script in powershell intended to generate a few thousand names that will act as employees. Jane Doe and client 1 remain in the the ADMIN group while these new names will all be authorized EMPLOYEES with access to log into the vm. First you will copy the script provided by JOSH MADAKOR on github for this lab. Next you will open up the vm and run the script in the powershell IDE as an administrator. If excecuted correctly a list of employee names should begin generating. 

<h2>8. cep.jum chosen from list<h2>
<p>
<img src="https://imgur.com/TdTUCHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
As these names are generating in the powershell IDE they should be simultaneously streaming into the Active Directory users and computers under the EMPLOYEES tab. From this list of names choose one and attempt to log in to the client vm. In this instance I chose the name cep.jum to log in with. Also remember to attach your name to the domain created for the client vm. If this works correctly, Congrats!


<h2>9. Lockout cem.kaf and unlock for test</h2>
<p>
<img src="https://imgur.com/8a7tCcd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Finally, we will choose another name from the list and lock them out of the vm for making too many invalid login attempts. Start by logging out of the vm with the employee you previously logged in with an choose another name from the list of names that should still be streaming in. With this name go to the vm log in menu and intentionally type in the wronng password about 6 to 8 times to ensure that your account is locked out. Navigate back to the Active Directory user and computers tab and choose the name that is locked out. Right click the name and go to accounts menu. Check the unlock account box and apply the change. Click ok and attempt to log in properly with the same employee name. Congrats, your account is unlocked!
 
