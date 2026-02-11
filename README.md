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
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447358648459202743/Screenshot_2025-12-07_164509.png?ex=69696e48&is=69681cc8&hm=cf94d23aeb374cc45e9e0c71a8aab1a067c765372740561ecd91ee5616f93468" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
I assigned a static IP address range here in the router to receive traffic, subnet mask is assigned as well for each department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1445256985133187072/Screenshot_2025-12-01_213317.png?ex=693ed934&is=693d87b4&hm=5f0595a2494f0fc22670ce7619b5d8f6cd92d349a12ea83eced7f790bae32894" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br />
Sub-interfaces were created for all departments. :  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447365701143888054/Screenshot_2025-12-07_171313.png?ex=693f44d9&is=693df359&hm=e6b3f9b58e09708fe630327a3bb6d35a08a2c1c1a47912cfca9bcbf19f34451b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
DHCP service was activated, and an IP pool and DNS was created for the Admin department. The other 2 departments will be the same:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447367590166007858/Screenshot_2025-12-07_171958.png?ex=6969769c&is=6968251c&hm=a5fd1da2d6356c1ec7107d7c0fa313a0debef83863c5153500de32c775010c60" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
DHCP pools and networks were created for all departments where ip addresses should be automatically be given to each devices once DHCP is turned on:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447369945309516059/Screenshot_2025-12-07_172855.png?ex=696978cd&is=6968274d&hm=1defc3c01fcbe085b90973ffc2b8adb1cfac99ca481557ac17363bc12222761f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Successful connection to DHCP for PC1:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447370352249405560/Screenshot_2025-12-07_173229.png?ex=6969792e&is=696827ae&hm=116b26e1324093da5337142a19f10217589bfeeb8c6fe070db199d6707fee02d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Both wireless devices were also configured to connect to the WAP in adm.in department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374379859050496/Screenshot_2025-12-07_174418.png?ex=69697cef&is=69682b6f&hm=7f1e8689a3a2f5b5a6d1b535f70a64c9cd867dd3e228b82c529e1c0e06d8f405&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374380211376209/Screenshot_2025-12-07_174744.png?ex=69697cef&is=69682b6f&hm=e00726a038411974f54a819a7efad01fba65981a5931e8ca865d9150fff14c44&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Before finalizing the project, I used the command prompt to ping the smartphone in the Admin/IT department to CS/Reception PC2, and it was successful with sending 4 packets, receiving 3, and only losing 1, which only puts it at a 25% lost:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447377847525314700/Screenshot_2025-12-07_175931.png?ex=69698029&is=69682ea9&hm=019b6e1c3dcb106c9d4efac1736b34254a75c5f3bea737dd67aae7a73b439161" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
