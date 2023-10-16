	To control the speed of a scan, use -T.
	e.g sudo nmap scanme.nmap.org -T(0-5)
	The -T takes in speeds between 0 and 5.
	- `-T 0` / `-T paranoid`
	- `-T 1` / `-T sneaky`
	- `-T 2` / `-T polite`
	- `-T 3` / `-T normal`
	- `-T 4` / `-T aggressive`
	- `-T 5` / `-T insane`
	The faster you go the less accurate the scans.
	By the way, the slower you go the less likely you are to be discovered.