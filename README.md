<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

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

- Create Resource Group and virtual Machines
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/IuZ4L0m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I created a resource group and two virtual machines. One virtual machines was created with windows 10 and the other with Linux (Ubuntu). I connected to the Windows 10 VM with the public IP address and the Ubuntu VM with the private IP address.
</p>
<br />

<p>
<img src="https://i.imgur.com/QHYHjxT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After connecting to the Windows 10 virtual machine I installed Wireshark. Within wireshark I tested the ICMP traffic and observed. On the Windows 10 virtal machine I attempted to ping the private IP address of the Ubuntu virtual machine. Then, I opened Powershell and attempted to ping a public website. Lastly, I initiated a perpetual ping from my windows 10 virtual machine to my Ubuntu Virtual machine and observed in Windows 10.
</p>
<br />

<p>
<img src="https://i.imgur.com/H0CeC4W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Going back to wireshark, I filtered for SSH traffic only. From the Windows 10 virtual machine I typed commands into the Linux SSH connection and observe SSH traffic spam in WireShark
</p>

<p>
<img src="https://i.imgur.com/H0CeC4W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Going back to wireshark, I filtered for DHCP traffic only. From the Windows 10 virtual machine I attempted to issue my virtual machine a new IP address from the command line and observed the DHCP traffic in Wireshark.
</p
<br />

<p>
<img src="https://i.imgur.com/Zae6MIu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Going back to wireshark, I filtered for DNS traffic only. From the Windows 10 virtual machine on a command line used nslookup to see what the IP address of google.com and disney.com were, then observed the DNS traffic shown in wireshark.
</p>

<p>
</p>
<p>
Going back to wireshark, I filtered for RDP traffic only. The result was non-stop spamming of traffic due to the RDP showing a live stream from one computer to another.
</p>
