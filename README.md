# Network-Security-Groups-and-Inspecting-Network-Security
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

Allow Administrator account lockout. 

</p>
<br />
