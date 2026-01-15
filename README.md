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
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447331431809417296/Screenshot_2025-12-07_145124.png?ex=696954ef&is=6968036f&hm=6766368b9f775425091bec0348eba3bd785ec6714b6ed75b86d8abbfaaa710bb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configured network access for the switch to the ADMIN/IT department and configured a VLAN for the department as well. The same is repeated for the other 2 departments:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447350586994462970/Screenshot_2025-12-07_161011.png?ex=696966c6&is=69681546&hm=d937e03db0857a599643724ae5ca86b4e834f87ceae3277b1f6882aceb6efdbe" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
All ethernet connections are connected to VLAN 10,20,30 as shown: <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447352842280112250/Screenshot_2025-12-07_162312.png?ex=696968e0&is=69681760&hm=1227f6dcb3211c3af530a96c219137a946e79480bfc93c08727e2119845a1222" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
configured access port for WAP (ADMIN/IT) changing SSID and authentication is set to WPA2-PSK:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447354310584434768/Screenshot_2025-12-07_162718.png?ex=69696a3e&is=696818be&hm=c6645495e89c12071772b885e7ec761aeda410c534e33c93ab10cb8492759570" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configured switch into trunk before configuring router:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447357630736502885/Screenshot_2025-12-07_164054.png?ex=69696d55&is=69681bd5&hm=a12d5ceda0b83f2357ca2d52601e95dc5b16d85221c6df3f7248b0fdbea38377" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
