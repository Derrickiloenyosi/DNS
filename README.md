# DNS
<p align="center">
<a href="https://imgur.com/qw22Ml2"><img src="https://i.imgur.com/qw22Ml2.png" title="source: imgur.com" height="80%" width="80%" /></a>
</p>
<p>


</p>

<h1>Creating A-Records and CNAME Records</h1>
This will showcase a breakdown of creating A-Records and CNAME. Through screenshots and brief summary, I will show steps to creating an A-record using 2 clients "DC-1" and "Client 1".
Then I will change the destination of the A-record to 8.8.8.8. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)



<h2>Deployment and Configuration Steps</h2>


  
<a href="https://imgur.com/QjRtke2"><img src="https://i.imgur.com/QjRtke2.png" title="source: imgur.com" height="80%" width="80%" /></a>
</p>
<p>
The image above is where one goes to create an A-Record. To get here, you go to Server Manager -> Tools -> DNS -> Forward Lookup Zones -> mydomain.com -> then right click for option box to surface -> then select New Host (A records). Once a record name is created, you can link it to an ip address. In this lab the A-Record name was "mainframe" and I linked it to the private ip address of one of the virtual machines I created named "DC-1". 
</p>
<br />










<a href="https://imgur.com/q9QV8kA"><img src="https://i.imgur.com/q9QV8kA.png" title="source: imgur.com" height="80%" width="80%"/></a>
</p>
<p>
In the image above, you will see that from "Client-1" also seen as jane, I typed the command ping mainframe and the private ip address of DC-1 shows up(10.0.0.4). This is because in the previous image, mainframe was linked to the private ip address of 10.0.0.4. 



<a href="https://imgur.com/Tt7cV6I"><img src="https://i.imgur.com/Tt7cV6I.png" title="source: imgur.com" height="80%" width="80%"/></a>
</p>
<p>
Now going back to DNS manager, the image above shows the new IP address of 8.8.8.8. that the mainframe will be assigned to. 



<a href="https://imgur.com/nMnYpRi"><img src="https://i.imgur.com/nMnYpRi.png" title="source: imgur.com" height="80%" width="80%" /></a>
</p>
<p>
The image above shows that despite linking mainframe to the new IP address of 8.8.8.8, it still shows the old IP address. This is because the old IP address is still on the cache files and the command ipconfig /flushdns is needed to reset the cache which he update the mainframe to the new IP address.



<a href="https://imgur.com/77ZGXVR"><img src="https://i.imgur.com/77ZGXVR.png" title="source: imgur.com" height="80%" width="80%"/></a>
</p>
<p>
Now that we have typed in the flush command, the mainframe now shows that it is linked to 8.8.8.8.






<a href="https://imgur.com/aEPRnaB"><img src="https://i.imgur.com/aEPRnaB.png" title="source: imgur.com" /></a>
</p>
<p>
  
The above image shows the process of changing the CNAME from the DNS Manager. The CNAME is being changed to search and will be linked to the website "www.google.com".


<a href="https://imgur.com/ILCWIxC"><img src="https://i.imgur.com/ILCWIxC.png" title="source: imgur.com" /></a>

</p>
<p>
  
The image above shows that the new CNAME of search was successfully linked to the website "www.google.com".
