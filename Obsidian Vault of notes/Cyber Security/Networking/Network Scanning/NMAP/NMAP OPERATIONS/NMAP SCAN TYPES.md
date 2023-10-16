## How to use a different scan type in nmap

To use a different scan type in [[NMAP]], you can use the `-s` option. The `-s` option takes a scan type as an argument. The following are some of the available scan types:

- `-sS`: TCP SYN scan (half-open scan)
- `-sT`: TCP connect scan (full-open scan)
- `-sU`: UDP scan
- `-sN`: TCP Null scan
- `-sF`: TCP FIN scan
- `-sX`: TCP Xmas scan

For example, to perform a TCP connect scan on the IP address 192.168.1.1, you would use the following command:

nmap -sT 192.168.1.1

To get a list of all the available scan types, you can use the `-h` option.

Here is a table that summarizes the different scan types and their characteristics:

|Scan Type|Description|
|---|---|
|`-sS`|TCP SYN scan (half-open scan). This is the default scan type. It is a stealthy scan that does not establish a full connection with the target port.|
|`-sT`|TCP connect scan (full-open scan). This scan establishes a full connection with the target port. It is less stealthy than a SYN scan, but it can give you more accurate results.|
|`-sU`|UDP scan. This scan is used to scan UDP ports. UDP scans are less reliable than TCP scans, but they can sometimes be used to detect open ports that are not visible to TCP scans.|
|`-sN`|TCP Null scan. This scan sends a TCP packet with no flags set. It is a stealthy scan that can be used to bypass some firewalls.|
|`-sF`|TCP FIN scan. This scan sends a TCP packet with the FIN flag set. It is a stealthy scan that can be used to bypass some firewalls.|
|`-sX`|TCP Xmas scan. This scan sends a TCP packet with the FIN, PSH, and URG flags set. It is a stealthy scan that can be used to bypass some firewalls.|