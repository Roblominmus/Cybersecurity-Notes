**IP ADDRESSES**
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
