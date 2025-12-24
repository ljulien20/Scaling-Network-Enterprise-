# Scaling Network Enterprise



<h2>Description</h2>
Here I am establishing a network for a company that is growing fast in Texas, with more than 2 million customers nationwide. The company deals with selling and buying food items, which are basically operated from the headquarters. The company wants to open a branch in Austin, TX, pretty soon, and requires me to design the network for the branch. The network is intended to operate separately from the HQ network. With the base IP being a class C address, the subnet will  be 255.255.255.0.

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
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447331431809417296/Screenshot_2025-12-07_145124.png?ex=694c53ef&is=694b026f&hm=fb92d00f8fbd041932fcfea394030f18bc214b5d12b9d85af695239030c6040f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configured network access for the switch to the ADMIN/IT department and configured a VLAN for the department as well. The same is repeated for the other 2 departments:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447350586994462970/Screenshot_2025-12-07_161011.png?ex=694c65c6&is=694b1446&hm=f4a706d7a09700d1562d99eebd0966ebce8ca853b889cd7cdac2db11b3de26aa" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
All ethernet connections are connected to VLAN 10,20,30 as shown: <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447352842280112250/Screenshot_2025-12-07_162312.png?ex=693f38e0&is=693de760&hm=ff47b44be0e313c428bd7fcd594546a68dacf7050a21c2665c4d5744b8e77f22" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
configured access port for WAP (ADMIN/IT) changing SSID and authentication is set to WPA2-PSK:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447354310584434768/Screenshot_2025-12-07_162718.png?ex=693f3a3e&is=693de8be&hm=f227147c10607b7336a78fe578d7fd078e409ee58db19ad98c78d225824394ed" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configured switch into trunk before configuring router:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447357630736502885/Screenshot_2025-12-07_164054.png?ex=693f3d55&is=693debd5&hm=acf314235237aad26de9dc2c63339d34f80e2a0d8a40bf0adbba6610a8b7d99c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Router is now configed, as you can see by  the green arrows that are on the ethernet cable. Ip addresses will be issued next and create sub sub-interface. 
:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447358648459202743/Screenshot_2025-12-07_164509.png?ex=694c6d48&is=694b1bc8&hm=dcc9bb01547ca037f5b8ba397c70febc3fecbe6c4c918fb745a50157ccd419c1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
I assigned a static IP address range here in the router to receive traffic, subnet mask is assigned as well for each department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1445256985133187072/Screenshot_2025-12-01_213317.png?ex=693ed934&is=693d87b4&hm=5f0595a2494f0fc22670ce7619b5d8f6cd92d349a12ea83eced7f790bae32894" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br />
Sub-interfaces were created for all departments. :  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447365701143888054/Screenshot_2025-12-07_171313.png?ex=693f44d9&is=693df359&hm=e6b3f9b58e09708fe630327a3bb6d35a08a2c1c1a47912cfca9bcbf19f34451b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
DHCP service was activated, and an IP pool and DNS was created for the Admin department. The other 2 departments will be the same:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447367590166007858/Screenshot_2025-12-07_171958.png?ex=694c759c&is=694b241c&hm=0b9cbdab0aba13e6175c1e88c6b4a743fd9373cf8dcf2099f2d372053fe39223" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
DHCP pools and networks were created for all departments where ip addresses should be automatically be given to each devices once DHCP is turned on:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447369945309516059/Screenshot_2025-12-07_172855.png?ex=694c77cd&is=694b264d&hm=e95eec84b980067a5bc168e1023bd42eea7d588834615073be2d5cb72b814a76" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Successful connection to DHCP for PC1:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447370352249405560/Screenshot_2025-12-07_173229.png?ex=694c782e&is=694b26ae&hm=21ce0dcf25fb6d646f0d7a15511ddfbf33225e67845ff7488e64b6924b88f052" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Both wireless devices were also configured to connect to the WAP in admin department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374379859050496/Screenshot_2025-12-07_174418.png?ex=694c7bef&is=694b2a6f&hm=8e972fc13525ed0d767d2b12701cbf178160326a503d770dbf300325931db1da&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374380211376209/Screenshot_2025-12-07_174744.png?ex=694c7bef&is=694b2a6f&hm=7b672d4f8aaeed77b705699f5706d883b87f4552bfcc1aec4c3b3b4880e55266&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Before finalizing the project, I used the command prompt to ping the smartphone in the Admin/IT department to CS/Reception PC2, and it was successful with sending 4 packets, receiving 3, and only losing 1, which only puts it at a 25% lost:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447377847525314700/Screenshot_2025-12-07_175931.png?ex=694c7f29&is=694b2da9&hm=ccee847545eaaf6b17b412b6140340768753fe9468c750fd13f0d2583fd5f48c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
