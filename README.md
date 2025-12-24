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
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447331431809417296/Screenshot_2025-12-07_145124.png?ex=693f24ef&is=693dd36f&hm=d3f371176c4253190475df4ab5771bd158a22bb998283b96b300cf42014debbc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Configured network access for the switch to the ADMIN/IT department and configured a VLAN for the department as well. The same is repeated for the other 2 departments:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447350586994462970/Screenshot_2025-12-07_161011.png?ex=693f36c6&is=693de546&hm=fc6da7ed5968e2c3e0f8165564a236ad9afc26de97a923613fe2b41af6576ff0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447358648459202743/Screenshot_2025-12-07_164509.png?ex=693f3e48&is=693decc8&hm=1f578099b7cf397f70d82bfe4801e8938366461b510d8cf0d56e0c1aa32ce8d6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
I assigned a static IP address range here in the router to receive traffic, subnet mask is assigned as well for each department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1445256985133187072/Screenshot_2025-12-01_213317.png?ex=693ed934&is=693d87b4&hm=5f0595a2494f0fc22670ce7619b5d8f6cd92d349a12ea83eced7f790bae32894" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br />
Sub-interfaces were created for all departments. :  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447365701143888054/Screenshot_2025-12-07_171313.png?ex=693f44d9&is=693df359&hm=e6b3f9b58e09708fe630327a3bb6d35a08a2c1c1a47912cfca9bcbf19f34451b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
DHCP service was activated, and an IP pool and DNS was created for the Admin department. The other 2 departments will be the same:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447367590166007858/Screenshot_2025-12-07_171958.png?ex=693f469c&is=693df51c&hm=7f3e7f2f788e3df1afd822634aa4fd1b13eaba5184a093072bd1ab78737e2fa9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
DHCP pools and networks were created for all departments where ip addresses should be automatically be given to each devices once DHCP is turned on:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447369945309516059/Screenshot_2025-12-07_172855.png?ex=69409a4d&is=693f48cd&hm=081d49c339b06eedba3f5c4c29af9eeabd464f499f7ccfdd931f58734d9a073b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Successful connection to DHCP for PC1:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447370352249405560/Screenshot_2025-12-07_173229.png?ex=69409aae&is=693f492e&hm=60dad3fb1a8273dbf8d8ee596b6914efc650facdca351266af9072cf9938ef76" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Both wireless devices were also configured to connect to the WAP in admin department:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374379859050496/Screenshot_2025-12-07_174418.png?ex=69409e6f&is=693f4cef&hm=354c8a4c63629a688354486348e86f04b454fd77ece950deac699895e414a4d9&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447374380211376209/Screenshot_2025-12-07_174744.png?ex=69409e6f&is=693f4cef&hm=6fa9bf0c8780849c965f13c9306e084ad005b3d36cb042048442a26cf2a478e0&" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /> 
<br/>
Before finalizing the project, I used the command prompt to ping the smartphone in the Admin/IT department to CS/Reception PC2, and it was successful with sending 4 packets, receiving 3, and only losing 1, which only puts it at a 25% lost:  <br/>
<img src="https://cdn.discordapp.com/attachments/1445251151896248323/1447370352249405560/Screenshot_2025-12-07_173229.png?ex=69409aae&is=693f492e&hm=60dad3fb1a8273dbf8d8ee596b6914efc650facdca351266af9072cf9938ef76" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
