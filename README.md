a# Network-Security-Groups-and-Inspecting-Network-Security
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
  
![image](https://github.com/user-attachments/assets/e88572f4-08ad-42da-b511-30f2d28abcc5)

![image](https://github.com/user-attachments/assets/5596545f-cb78-4642-9863-a2f4492b0647)

![image](https://github.com/user-attachments/assets/6d907a89-9b16-40c1-8104-9ab3345d30d6)

![image](https://github.com/user-attachments/assets/7ff45db4-019e-4c70-8b82-5aec5a5282c2)

</p>
<p>
Right-click the "Start" menu and click on "Run". Type "gpmc.msc" to open the Group Policy Management console. Navigate to the Default Group Policy section. 

</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/da8fc31c-c17b-4fe4-9ed8-99a8f6c624eb)

![image](https://github.com/user-attachments/assets/36c9de5d-21ea-4f1c-9776-1a09f784f7e3)

![image](https://github.com/user-attachments/assets/2004aa0f-81a3-45b2-b172-0d359ee6dc9b)

![image](https://github.com/user-attachments/assets/4d2cd197-b53c-42c4-b658-8002b0ed1a63)


</p>
<p>
In the Group Policy Management Editor, expand the following: Computer Configuration --> Policies --> Windows Settings --> Account Policies --> Account Lockout Policies.  
</p>
<br />

<h2> Configure the Group Policy </h2>

<p>

![image](https://github.com/user-attachments/assets/55577f20-f69b-47e0-aae4-5da08f3eb76b)

</p>

<p>
Set Account Lockout Duration to 30 minutes. 

</p>

<p>
  
![image](https://github.com/user-attachments/assets/f9d0d8e1-634a-4488-b23a-78e7f8af1aff)

</p>

<p>

Configure the account lockout threshold. 

</p>


<p>

![image](https://github.com/user-attachments/assets/b998b93a-32fa-4658-b8fa-b83788ece103)

<p/>

<p>

Enable Administrator account lockout. 

</p>

<p>

![image](https://github.com/user-attachments/assets/65cb3744-bb1d-4471-a81f-e98a94f7f31f)

</p>
<br />

<h2> Force the Group Policy Update from Client-1 </h2>

<p>

![image](https://github.com/user-attachments/assets/2a021545-7eaa-4e6e-9d18-c628270905d8)

![image](https://github.com/user-attachments/assets/1cfcd449-e607-47cb-8877-28da3576c91d)

</p>

<p>
To force the Group Policy Update, log into client-1 and enter "gpupdate \force" in the Command Line.
</p>

<p>
  
![image](https://github.com/user-attachments/assets/23a99db5-35e4-4fa3-83f2-915a369b1f7e)

![image](https://github.com/user-attachments/assets/f66a4c9e-e516-4276-a3dd-f801b7e859dd)

</p>

<p>

Enter "result \r" in the Command Line as administrator to verify if the group policy has been successfully updated. 

</p>

<h2> Observe the Group Policy </h2>

<p>
  
![image](https://github.com/user-attachments/assets/91647efb-cdb4-4c6d-8dd7-5ea44cd1134a)

</p>

<p>
I logged in to the client account babe.mexo with a false password for five times. The account ended up being locked out. 

</p>

<p>
  
![image](https://github.com/user-attachments/assets/5ebcc9be-ed0e-480f-ad99-16e5b483b729)

![image](https://github.com/user-attachments/assets/4f4749ab-afab-4f8e-bca8-4bbd04ea4694)

![image](https://github.com/user-attachments/assets/43ec5ac9-fec6-4e10-9167-017fe9d27db1)

![image](https://github.com/user-attachments/assets/6cc7ce96-94f2-453d-ba31-25139462d9bc)

</p>

<p>

To unlock the client account, log in to the domain controller. Open Active Directory Users and Computers, right-click "mydomain.com" and select "Find." Search for "babe.mexo". Once the account pops up, right-click it and select "Properties" from the menu. Navigate to the "Account" tab and check "Unlock account". Log back into the account with the default password "Password1."

</p>

![image](https://github.com/user-attachments/assets/df60d511-bf73-4019-a068-567a9280f0aa)

![image](https://github.com/user-attachments/assets/c51482a6-f59f-4a10-b2ad-f4eadade9aa4)

<p>

<p>
Reset password. 
</P>
</br>
<p>
  
![image](https://github.com/user-attachments/assets/c8c35dcf-f2d4-4c44-9bf7-55640e6b1799)

![image](https://github.com/user-attachments/assets/bc8ec419-f436-41fd-9127-05f1b082067e)


</p>

<p>
In Active Directory Users and Computers, right-click "mydomain.com" and select "Find" from the menu. Search for "babe.mexo". Once this account pops up, right-click it and select "Disable Account."
</p>

<p>
  
![image](https://github.com/user-attachments/assets/f6660ed8-b122-4ecd-9281-34db4168d83f)

</p>

<p>
Attempt to log into client-1 with the account "babe.mexo". The login will not be successful, and you will get a message saying the account has been disabled. 
</p>
