This is a service used for network scanning.
It is a part of the tools used for penetration testing in the [[Fundamental]] tools used for network attacks in cybersecurity.
It is mainly used for scanning networks and websites in order to find vulnerabilities that may be of use to you.

Before trying to read this , see [[Scanning Options]] to understand the types of tags used, or just refer to it when confused about a certain scan.
I got the [[Scanning Options]] from an incredibly reliable source, if i explain a scan in this note, check the [[Scanning Options]] to know if I was correct.

This note is just like a quick overview of nmap, refer to the rest of the notes when needed. I made this note myself, I'm only human.
The other notes are from The HackTheBox Website.

**COMMANDS**:
	Commands in kali are case sensitive.
	- One of the commands is "route" : This checks to see what network your current device is connected to
	- When running an nmap scan there are different parameters that follow the same layout when being typed.
		Layout : "sudo nmap (-PR or -PE or -PA[XX] ) -sn (x.x.x.x/xx or sample.com)"
			SUDO is to use super user do i.e. to use all the authority the device has to execute the following command
			NMAP is the service being used
			-PR is to send an ARP request :  A request to every device in the range and if a device recognizes its IP is present in the list then it replies .
			-PE is to send an echo request . Basically like using ping to ping all the devices. It is a lot more time consuming than "-PR" when scanning a large network but it is a lot better.
			-PA(xx) this sends acknowledgment packets to the  port xx to as id there is any host there 
			-sn is to disable port scanning
			x.x.x.x/xx - This scans for all ip addresses (x.x.x.x) under that router within a range of 1-xx as their ending ip number. You will specify the ip and range by yourself.
			sample.com - This scans a website for hosts
			see [[Scanning Options]] if confused.

**LAYERS OF IP SCANNING**
	In nmap thee are different layers of scanning
	 Layer 1 - "nmap 10.0.0.0/24"
		This scans for all ip addresses under that router within a range of 1-24 as their ending numbers 
		Usually this only works if the system does not have a fire wall, that make this type of scanning very weak.
	 Layer 2 - "nmap -PR -sn 10.0.0.0/24"
		 In this case it scans (-sn) the network under the range of the specified router and sends an ARP request (PR).
	 Layer 3 - "sudo nmap  -PE -sn scanme.nmap.org"
		 This will ping scanme.nmap.org to check if there is any host in the website.
		 Most times this may not return anything because there may be a firewall in the way. This will force you to use the four layer of scanning
	 Layer 4 - "sudo nmap -PA80 -sn scanme.nmap.org"
		 This does what the layer 3 does but this time it send acknowledgement packets

**PORT STATES**
 Open : This is a port that is actively accepting connections. These are the ones which are vulnerable to attacks.
 
 Closed : This shows that there is port there but it is not receiving any connections. The only thing it says id that there is a port here but you cannot do anything with it.
 
 Filtered : This is port that nmap does not know if it is open or closed . It shows that the port is not accessible. It just means "Nice try but no".
 
 Unfiltered : This mean that the port is accessible but nmap does not know if it is open or closed. It is telling you to use a different method to scan the network
 
 Open / filtered : This means that nmap does not know if this port is open or filtered.
 
 Closed / filtered : Nmap does not know if it is closed or filtered.

**PORT SCANNING COMMANDS**:
	"nmap (your ip)": 
		This is the most basic form of port scanning. It checks your device to see if there are any open ports. You can also check the ip of another device on you network When your done ip scanning. 
	"nmap -iL iplist.txt":
		Sometimes you might want to scan a whole list of the devices on your network.
	"nmap -p 22 -iL iplist"
		This scans for the specific port tat you specified. In this case it is port 22.
		It checks to see the devices that have the specified port open.
		port 22 = ssh
	"sudo nmap -sA -iL iplist"
		This one checks for those that are filtered or unfiltered.
		Sometimes a firewall may be obstructing nmap, so we use this command to look for the filtered or unfiltered ports.
		You could replace the -sA with -sU Tto search for the open UDP ports, instead of the default TCP
	"sudo nmap -sV -iL iplist"
		This checks to see the names and versions of the found ports.
		You could use that info to look for vulnerabilities available on that version. 
	"sudo nmap -O -iL iplist"
		This is to check the operating systems of the devices discovered.
		Some times a device may return with the too may finger prints response. That means that the device successfully deceived nm
	"sudo nmap -sS -iL iplist"
		This will scan the network and return with the devices connected and their ports and MAC Address.
		It is good and useful for a general scan. Like a summary of all the devices on the network and their ports
		

**Detection Avoiding:
Below are some techniques used to avoid detection**

[[SPEED CONTROL]]

**DECOY SCANNING**:
	Decoy scanning scans the device / network but it also floods it with fake ips making it very hard for the victim to find out which one is your device
	To run a decoy scan you use "(device ip) -D RND(number of decoy ips you want to use)"
	e.g sudo nmap 10.0.0.10 -D RND: 20

**RANDOM SCANNING**:
	This will make sure that the scan jumps to random ports instead of going sequentially and this makes it hard for the victim to pick up your presence
	e.g sudo nmap -iL iplist --randomize-hosts

**MAC ADDRESS SPOOFING**:
	This is to change your mac address
	e.g sudo nmap 10.0.0.10 --spoof-mac 0
	The zero at the end randomizes the address

**PACKET FRAGMENTATION**:
	This is when we break down our packets into smaller packets before we send them out.
	The smaller packets make it harder for them to be detected 
	e.g. sudo nmap 10.0.0.10 -f

**Post Scanning:
	After scanning and finding out what ever you needed to find out the next stage is to run nmap scripts to use those exploits to your advantage, you can get some pre built scripts n the nmap website but if your are using kali Linux than they are already built in, in the /usr/share/nmap/scripts directory.
	To run a script you follow the layout, sudo nmap (device or device you wish to scan) --script (script name, depending on the info you got.
	e.g. sudo nmap 10.0.0.10 --script smb-vuln-ms17-010.nse, look at the [[Categories Of Nmap Scripts]]
	or you can decide to use [[METASPLOIT]] to find the vulnerabilities available for that device **

There are other [[NMAP SCAN TYPES]] 