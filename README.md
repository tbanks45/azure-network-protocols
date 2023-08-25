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

- Step 1: Create two virtual machines in microsoft azure
- Step 2: Observe ICMP Traffic using wireshark
- Step 3: Observe DHCP traffic using wireshark

<h2>Actions and Observations</h2>

<p>
![image](https://github.com/tbanks45/azure-network-protocols/assets/142834800/f778641c-1992-4581-9d1e-4a4de9e9bcd8)
</p>
<p>
Here in this step I setup two virtual machines with which I will send traffic back and forth. One virtual machine will be using windows 10 and the other will be using Linux (Ubuntu). They will share the same resource group and virtual network.
</p>
<br />

<p>
![image](https://github.com/tbanks45/azure-network-protocols/assets/142834800/9c904551-64b7-4b99-9980-2bde899cbc7a)
</p>
<p>
Within the Windows 10 Virtual Machine, I installed Wireshark and set the filter to observe ICMP traffic. ICMP is the protocol that is used for ping and troubleshooting. My ping was sent to the private IP address of the Ubuntu vm and it created traffic. Next I opened the Network Security Group on the Ubuntu VM and disabled incoming (inbound) ICMP traffic and saw that the traffic was stopped on wireshark.

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I set the filter on wireshark to DHCP to observe DHCP traffic. From the Windows 10 VM, I attempted to issue the VM a new IP address from the command line using the ipconfig /renew command and observed the DHCP traffic appearing in WireShark.

</p>
<br />
