# Scaling Network Enterprise



<h2>Description</h2>
Here I am establishing a network for a company that is growing fast in Louisiana, with more than 2 million customers nationwide. The company deals with selling and buying food items, which are basically operated from the headquarters. The company wants to open a branch in Baton Rouge, LA, pretty soon, and requires me to design the network for the branch. The network is intended to operate separately from the HQ network. With the base IP being a class C address, the subnet will  be 255.255.255.0.

1.) one router and one switch to be used (all Cisco products)    

2.) 3 departments are made (Admin/IT, Finance/HR, and Customer Service/Reception)    

3.) Each department is required to have a different VLAN  

4.) Each department requires to have wireless network for the users.  

5.) Host devices in the network are required to obtain an IPv4 address automatically.  

6.) Devices in all the departments are required to communicate with each other.
ISP gave out a base network of 192.168.1.0
<br />


<h2>Languages and Utilities Used</h2>

- <b>Command Line</b> 


<h2>Environments Used </h2>

- <b>CISCO packet tracer</b>

<h2>Program walk-through:</h2>

<p align="center">
Establish placement of devices for this network: <br/>
<img width="2546" height="1277" alt="Screenshot 2025-12-07 145124" src="https://github.com/user-attachments/assets/82ac7b8d-284f-42f9-89e9-49debbf7d5fb" />
<br />
<br />
Configured network access for the switch to the ADMIN/IT department and configured a VLAN for the department as well. The same is repeated for the other 2 departments:  <br/>
<img width="1238" height="659" alt="Screenshot 2025-12-07 161011" src="https://github.com/user-attachments/assets/b3911aba-9f8c-45c9-9af2-c303e4b45fc9" />
<br />
<br />
All ethernet connections are connected to VLAN 10,20,30 as shown: <br/>
<img width="2535" height="1230" alt="Screenshot 2025-12-07 162126" src="https://github.com/user-attachments/assets/0534bb19-c359-404d-b6ca-f257bc8b1f52" />
<br />
<br />
configured access port for WAP (ADMIN/IT), changing SSID and authentication is set to WPA2-PSK:  <br/>
<img width="2198" height="1038" alt="Screenshot 2025-12-07 162718" src="https://github.com/user-attachments/assets/2a730895-f417-4203-9211-5a5532c80b4e" />
<br />
<br />
Configured switch into trunk before configuring router:  <br/>
<img width="2031" height="1005" alt="Screenshot 2025-12-07 164054" src="https://github.com/user-attachments/assets/68834419-ba27-4ed0-8420-f9a547b0553e" />
<br />
<br />
Router is now configed, as you can see by  the green arrows that are on the ethernet cable. Ip addresses will be issued next and create sub sub-interface. 
:  <br/>
<img width="2096" height="985" alt="Screenshot 2025-12-07 164509" src="https://github.com/user-attachments/assets/c2362c74-b7f3-4b7f-916f-658b4932efb9" />
<br/>
<br /> 
<br />
Sub-interfaces were created for all departments. :  <br/>
<img width="2126" height="1061" alt="Screenshot 2025-12-07 171313" src="https://github.com/user-attachments/assets/d2225a4e-43e5-4cf9-b0e7-bb266a7e1e3b" />
<br />
DHCP service was activated, and an IP pool and DNS was created for the Admin department. The other 2 departments will be the same:  <br/>
<img width="2036" height="951" alt="Screenshot 2025-12-07 171958" src="https://github.com/user-attachments/assets/2d2e7c77-3172-4f1b-8f3a-b9f6a084fde8" />
<br />
<br/>
DHCP pools and networks were created for all departments where ip addresses should be automatically be given to each devices once DHCP is turned on:  <br/>
<img width="2000" height="950" alt="Screenshot 2025-12-07 172855" src="https://github.com/user-attachments/assets/e2fb4385-8b7c-448d-b468-7ab9d317bf97" />
<br /> 
<br/>
Successful connection to DHCP for PC1:  <br/>
<img width="1578" height="849" alt="Screenshot 2025-12-07 173229" src="https://github.com/user-attachments/assets/6371474c-6c4b-4b88-9349-704b2549501e" />
<br /> 
<br/>
Both wireless devices were also configured to connect to the WAP in the admin department:  <br/>
<img width="1749" height="923" alt="Screenshot 2025-12-07 173907" src="https://github.com/user-attachments/assets/b06c5ab9-753e-4a0b-b155-34fa35c53716" />
<img width="1680" height="875" alt="Screenshot 2025-12-07 174744" src="https://github.com/user-attachments/assets/dcdbcb26-7ce9-4988-baf8-b4258bb7fecb" />
<br /> 
<br/>
Before finalizing the project, I used the command prompt to ping the smartphone in the Admin/IT department to CS/Reception PC2, and it was successful with sending 4 packets, receiving 3, and only losing 1, which only puts it at a 25% lost:  <br/>
<img width="1787" height="1003" alt="Screenshot 2025-12-07 175931" src="https://github.com/user-attachments/assets/e9c2196c-6ece-4af4-9643-0c7e2241ac00" />
<br /> 
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
