USE COMMMON SENSE IN THIS NOTE, SUBNETTING IS NOT EASY, TRY TO ACTUALLY USE YOUR BRAIN WHEN CONFUSED

Sub netting is Diving a network into sub divisions. 
In subnets, a computer that belongs to a certain sub net.
Look at this
![[Pasted image 20230920201817.png]]
"192.168.12.0/24"
The sub net mask is "255.255.255.0"
That means that there are 256 possible hosts under that stuff.
The possible IPs here are from 192.168.12.1 to 192.168.12.254
The 192.168.12.0 is the Network address while the 192.168.12.255 is the broadcast address.
So they cannot be given those IPs.

---
Now, what did I just say?
I don't know 
But I will say another thing that will hopefully lower the confusion or in IT terms, the brainfvck you're currently having

When you have a NAT Network where all of your devices are under one main ip, the traffic all comes to the same exit and this can get bad.
Sub netting will let you divide up ta traffic, so that one main ip will handle *let's say half* of your devices.

---
Aight, like this.
example - 192.168.2.64/26 ,  a subnet
"/26" - defines the subnet. 
The subnet mask for the subnet in binary (*yes, what it will be in binary is important*) will be 26 1s and the rest will be 0s.
i.e. **"11111111 11111111 11111111 11000000"** 
each section of the ip contains 8 bits (0s and 1s)
Let's list it out now
SUBNET - 192.168.2.64/26
SUBNET MASK - **11111111 11111111 11111111 11000000** or 255.255.255.192
IP ADDRESS - **11000000 10101000 00000010 01000000**
NETWORK ADDRESS - The lowest possible subnet - ***not included when counting the number of possible subnets or HOSTS if I may*** - **11000000 10101000 00000010 01000000** or **192.168.2.64**
BROADCAST ADDRESS - The highest Possible subnet - ***not included when counting the number of possible subnets or HOSTS if  I may*** -**11000000 10101000 00000010 01111111** or **192.168.2.127**

Okay so , looking at the subnet mask and the ip address in binary, the places in the subnet mask where there are ones are the places in the ip address which cannot be changed if not it will be part of a different subnet network. But the places with zeros can be changed .
i.e. if the ip changes to  **11000000 10101000 00000010 01000001** then everything is Gucci, it is a different ip but still in the same subnet mask
but if it changed to  **11000000 10101000 00000010 11000000** then it's not ok, it now in a different subnet mask

---
**OOOKAY, LET'S UNDERSTAND THE BITS BEHIND THIS NONSENSE *BELEIVE IT OR NOT, THIS IS WHERE THE HARD PART COMES***


![[Pasted image 20230920233223.png]]

Now look the image above.
In each section of the IP, there are 8 bits
The sum of the bits is 225.
Starting form 128 and then half of it which is 64, then another half and so on until 1.
When it is all added, it will equal 225.
Remember 1s and 0s are switches.
When 1 is switched on, the above number is added.
The switches are turned on from left to right.
When all the 1s are switched on, it adds up to 255
i.e.
![[Pasted image 20230920233752.png]]
Doing what this pic is doing isn't possible. It must be switched in order.

---
![[Pasted image 20230920234018.png]]

Now to see the number of available hosts we raise 2 to the power of 0s present, currently there are eight 0s present in the picture. The above one. The picture after the one directly above the one above this text.
The more 1s switched on, the less available hosts.
Look at what I mean
![[Pasted image 20230920234341.png]]
The more 1s that are on, the less hosts available in the subnet mask.

---
Okay, let's change gears now that you hopefully understand the bits.
![[Pasted image 20230920234653.png]]
That cheat sheet means something, just stay with me .
The "/24" means that there are 24 1s and the rest are 0s , so after doing the math you see that there are 256 hosts available. But two of those ae the broadcast and network IDs , so we actually have just 254 available hosts.
The "/26" means there are 26 1s and the rest are 0s, so there six 0s so there are 64 hosts available.

---
**IT'S STARTING TO MAKE SENSE**

![[Pasted image 20230921102353.png]]
Look at the above image.
Everything is about to make little sense.
- Look at the IP Range of "A", it has a "/28", so there are 28 ones and  (32-28 = 4) 4 zeros.
- The that also means there are (2^4 = 16) 16 hosts. But when you remove the highest possible host (i.e. the broadcast ID) and the lowest possible host (i.e. the Network ID) we then see that we have just 14 available hosts left.
- And for the subnet mask , lets write it in binary, 28 ones and 4 zeros. **11111111 11111111 11111111 11110000**
- Now, we know that "**11111111**" is **255**
- So the subnet mask is **255.255.255.x**
- Now, using google, i found out that **11110000** is **240**
- Sooo, the subnet mask is **255.255.255.240**

- Now, using that same logic , I need to complete the table
![[Pasted image 20230921104702.png]]
---
- So let's convert something a bit different.
- **192.168.0.0/23**
- **LOOK AT THE CHEATSHEET PLEASE**
- The sheet says that for **/23** there are **510** hosts and the **"X"** is at the second to last position on the subnet mask.
- While the number that will sub out that **x** is 254
- So, subnet mask will be , **255.255.254.0**
- And to get the NETWORK ID AND BROADCAST ID, It will be the lowest first which is **192.168.0.0** while the highest is **192.168.1.255**

- Let me explain
- The netmask is **11111111 11111111 11111110 00000000**
- So, 2^7 = 512, then 512 - 2 = 510, so there are **510** available hosts.
- Now as you can see **11111110** is 254
- Okay, you can see that the available hosts are 510 , that means that from the network id to the broadcast id, there are **510** host IPs there
- So from the example range we already know that the Network ID is **192.168.0.0**
- And to get the Broadcast ID, we will have to work with our brains now.
- In the IP sections, the possible numbers are from 0 to 256, after 256 it will ad one to the the section on the left and then start from **0** again.
- I mean like this, **192.168.0.256**
	- If we have 258 available hosts , we can divide the **258** by **256** that is one remainder 2.
	- So the netmask will be **255.255.1.1**, if you don't understand, then sorry. we did not put two at the end because we count the netmask numbers starting from 0 not 1
- Back to the explanation
- We see that there are 511 hosts (including network is and broadcast id)
- 512 divided by 256, that is 1 remainder 256
- Remember we start counting from **0**, so the ip will become **192.168.1.255**
- So we got our **BROADCAST ID** as **192.168.1.255**

---
**CHECK THE CYBER MENTOR'S COURSE ON SUBNETTING ON YOUTUBE, I HONESTLY THINK HE MADE EXPLAINED IT WELL, I'M JUST NOT PROCESSING IT PERFECTLY**