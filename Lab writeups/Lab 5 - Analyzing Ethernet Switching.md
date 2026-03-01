This lab is regarding Ethernet switching.  Both switches have an empty MAC address table, and all PCs have an empty ARP table.

![](/Screenshots/Pasted%20image%2020260301143403.png)


1. If PC1 pings to PC3, what messages will be sent over the network, and which devices will receive them?

Based on the previous lecture, until PC1 knows PC3's MAC address, it can't send the ping directly to that PC yet. 
- An ARP request is *broadcast* or sent to all devices on the network except PC1. It is dropped by any device that doesn't have the proper IP address
- An ARP reply is sent back from 192.168.1.3
- A ping request is sent from 192.168.1.1 to 192.168.1.3
-  A ping reply is sent from 192.168.1.3 as many times as a ping request is sent.


2. Send the ping and use Packet Tracer's 'simulation mode' to verify your answer.

First, I entered Simulation Mode on Packet Tracer. Then, I go to PC1 > Desktop > Command prompt and use the following command:
`ping 192.168.1.3`

In the Simulation Panel, it first shows the ARP requests being received by all devices on the network; then, it shows that PC1 gets an ARP reply. After that, notice that there is only ICMP communication between PC1 and PC3 (as well as any involved switches)

![](/Screenshots/Pasted%20image%2020260301140903.png)


3. Use pings to generate network traffic and allow the switches to learn the MAC addresses of all PCs on the network.

OK, so I've already sent a ping from PC1 to PC3, so I will use the following commands to get the switches to learn the rest:
`ping 192.168.1.2`
`ping 192.168.1.4`

After that, similar to before, first an ARP request is broadcast, then ICMP requests and replies to and from each machine I have pinged.


4. Use 'show' commands on the switches to identify the MAC address of each PC.

First, I click each switch to open them, then I go to CLI to get into Cisco IOS's terminal. From there, I run the following commands:
`enable`
`show mac address-table dynamic`

Unfortunately it didn't show anything because I was in simulation mode for some reason. I try again in realtime mode and get the following:

SW1:

![](/Screenshots/Pasted%20image%2020260301141918.png)

SW2:

![](/Screenshots/Pasted%20image%2020260301142036.png)

Curiously, it did not show one of the MAC addresses on SW2, so I pinged PC4 from PC2 and was able to get it to show. 

![](/Screenshots/Pasted%20image%2020260301142322.png)


5. Clear the dynamic MAC addresses from the MAC address table of each switch.

From here, I simply used the following commands to clear the MAC address table, then show it to make sure the clear command worked properly:

`clear mac address-table dynamic`
`show mac address-table dynamic`

And got the result below:

![](/Screenshots/Pasted%20image%2020260301143025.png)
![](/Screenshots/Pasted%20image%2020260301143039.png)