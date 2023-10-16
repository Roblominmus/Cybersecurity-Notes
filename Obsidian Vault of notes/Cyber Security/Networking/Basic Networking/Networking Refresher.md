This is a quick summary of networking.

---
**CONTENTS:**
- IP Addresses
- MAC Addresses
- TCP, UDP , and Three-Way Handshake
- Common Ports and Protocols
- The OSI Models
- Subnetting
---
-  **IP ADDRESSES**
	IP Addresses are layer-3 protocols.
	IPV4 or Inet is the basic ip address that we are familiar with (192.302.30.1) , it is written in decimal format. It is made up of 32 bits (4 bytes), each section of it contains 8 bits.
	IPV6 or Inet6 is written in hexadecimal format (fe80::28c::29ff::fe0a::4205) , it is made up of 128 bits (16 bytes)
	 ![[IPV4 vs IPV6.png]]
	
	There are around 5 billion possible combinations of ipv4 addresses. And obviously the numbers should have been exhausted by now right?
	Yes. That is the reason IPV6 was created, but till this day (9/20/2023), we are still using IPV4 instead of IPV6, it works due to "[[NAT]] (Network Address Translation)"
	Now, each device has an ip address, if one person owns 10 devices, that does not mean they are taking up 10 IPV4 spaces.
	This is due to [[NAT]], with NAT, you get private ip addresses under one main public address. Your area will have one ip address which takes ups one ip address space, while the devices under that are have private IPs that do not take up the global IP Address spaces.
	
	![[Private IP vs Public IP.png]]
	Your Private IP is under your area's public IP.
	[[NAT]] allows you to have a large amount of networks but a small amount of hosts.
	On my virtual machines i use the Class A range .
	![[Parrot Terminal IPV4 AND IPV6.png]]

- **MAC ADDRESSES**
	 MAC Addresses (Media Access Control) is a layer-2 protocol.
	 It is a physical address, it is identified as "ether"
	 ![[Parrot Terminal Ether (MAC ADDRESS.png]]
	 Anything using a network will have a MAC Address.
	 The first three pairs ("08:00:27") are the identifiers in a MAC Address, it tells you the name device.
	 In my case, if I look up the device with the first three pairs it will show up as a VirtualBox host machine, since I'm running my Linux distro on VirtualBox

- **TCP, UDP AND THREE-WAY HANDSHAKE**
	TCP (Transmission Control Protocol):
		This is a connection oriented transfer protocol. It works on what is called a "THREE WAY HANDSHAKE", Your system sends a "SYN" packet (Like a "Hi, are you there?") then receives a "SYN-ACK" packet (Like a "Yeah, I'm here") , then you finally sends a "ACK" packet (like a "So i wanted to tell you..."). It connects yoir system to **a** port.
	UDP (User Datagram Protocol):
		This is a connectionless transfer protocol.
		
	![[TCP VS UDP ELABORATE.png]]
	![[TCP vs UDP.png]]

- **COMMON PORTS AND PROTOCOLS**
	- FOR TCP:
		- FTP: You can use FTP to transfer files between your computer and another computer, such as a web server. When you upload a file to a website, you are using FTP.
		- SSH: SSH allows you to securely log in to a remote computer and run commands on it. This is useful for managing servers and other network devices.
		- SMTP: SMTP is used to send email. When you send an email, it is routed through a network of SMTP servers to get to its destination.
		- DNS: DNS is like a phone book for the internet. It translates domain names, such as `www.google.com`, into IP addresses, which are the numbers computers use to communicate with each other.
		- HTTP: HTTP is used to transfer web pages and other resources over the internet. When you visit a website, your web browser uses HTTP to download the web page and all of its associated resources, such as images and CSS files.
		- POP3: POP3 is used to download email from a mail server. When you check your email in an email client, such as Outlook or Gmail, it is using POP3 to download your messages from the mail server.
		- IMAP: IMAP is like POP3, but it allows you to access and manage your email on the mail server without downloading it to your computer. This is useful if you want to access your email from multiple devices, such as your computer and phone.
		- RDP: RDP allows you to remotely control a computer. This is useful for troubleshooting problems with a remote computer or for providing technical support.
		- HTTPS: HTTPS is a secure version of HTTP that uses encryption to protect your data from being intercepted by third parties. This is important for websites that handle sensitive data, such as online banking and e-commerce websites.
		-![[Common Ports.png]]
	- FOR UDP:
		- 
		- 
		- DNS: DNS is like a phone book for the internet. It translates domain names, such as `www.google.com`, into IP addresses, which are the numbers computers use to communicate with each other.
		- DHCP: DHCP automatically assigns IP addresses and other network configuration information to devices on a network. This makes it easy to set up new devices on a network without having to manually configure them.
		- NTP: NTP synchronizes clocks between devices on a network. This is important for applications such as streaming video and audio, which require accurate timing.
		- BGP: BGP is used by routers to exchange routing information between networks. This allows routers to find the best path to send traffic to other networks.
		- ISAKMP: ISAKMP is used to establish secure communication channels between devices on a network. This is useful for applications such as VPNs and VoIP.
		- SMTP: SMTP is used to send email. When you send an email, it is routed through a network of SMTP servers to get to its destination.
		![[UDP Protocols.png]]

- **OSI MODEL**
	The Open Systems Interconnection (OSI) model is a model that describes how data is communicated over a network. It is divided into seven layers, each of which has a specific function.
	Use This MNEMONIC "All People Seem To Need Data Processing". APSTNDP
	When we **receive** data it goes from Physical to Application
	When we **send** data it goes from Application layer to the Physical layer
	When **troubleshooting** it's always best to start from physical to application layer.
	
	- **Application layer:** This layer is responsible for providing network services to applications, such as email, file transfer, and web browsing e.g. HTTP, SMTP. ( **LAYER 7** )
	- **Presentation layer:** This layer is responsible for formatting data so that it can be understood by the receiving application e.g. JPEG, MP4. ( **LAYER 6** )
	- **Session layer:** This layer is responsible for establishing and managing communication sessions between applications. ( **LAYER 5** )
	- **Transport layer:** This layer is responsible for providing reliable end-to-end communication between applications e.g. TCP and UDP. ( **LAYER 4** )
	- **Network layer:** This layer is responsible for routing packets between different networks e.g. IP Addresses, Routing. ( **LAYER 3** )
	- **Data link layer:** This layer is responsible for framing bits into packets and detecting and correcting errors in transmitted data e.g. MAC Addresses. ( **LAYER 2** )
	- **Physical layer:** This layer is responsible for the transmission of bits via a  physical medium, such as a data cable ,copper wire or fiber optic cable. ( **LAYER 1** )

- **SUBNETTING**
	**BROOOOO, WHAT IS THIS?!
	WHY IS IT SOO DIFFICULT?**
	I'll try to explain it in the most simple terms I can think of
	check [[Subnetting Simplified ( I think)]]
