This is the lab for Jeremy's IT Lab - Free CCNA Day 9.

1. Configure the hostname of R1, SW1, and SW2

OK, this one should be easy. For each device, I'm going to click them and use the following commands:

`enable`

`conf t`

R1: `hostname R1`

SW1: `hostname SW1`

SW2: `hostname SW2`

![](/Screenshots/Pasted%20image%2020260304180622.png)

![](/Screenshots/Pasted%20image%2020260304180635.png)

![](/Screenshots/Pasted%20image%2020260304180643.png)

2. Configure the appropriate IP addresses on R1, PC1, PC2, PC3, PC4

IPs should be:
- R1: 172.16.255.254
- PC1: 172.16.0.1
- PC2: 172.16.0.2
- PC3: 172.16.0.3
- PC1: 172.16.0.4

For R1, I need to go back into the CLI (I did not leave global configuration mode from the previous task) and use the following commands:

`int g0/0`

`ip add 172.16.255.254 255.255.0.0`

![](/Screenshots/Pasted%20image%2020260304181816.png)

Then on each of the PCs, I went to the device > Config > FastEthernet0 and set their IP address under the IPv4 address field.

![](/Screenshots/Pasted%20image%2020260304182015.png)


3. Manually configure the speed and duplex on interfaces connected to other networking devices (not end hosts)

So for R1, I use the following commands (still from global configuration mode):

`int g0/0`

`speed 1000
`
`duplex full`

![](/Screenshots/Pasted%20image%2020260304181649.png)

Then on SW1:

`int g0/1`

`speed 1000`

`duplex full`

`int g0/2`

`speed 1000`

`duplex full`

![](/Screenshots/Pasted%20image%2020260304181714.png)

Then on SW2:

`int g0/1`

`speed 1000`

`duplex full`

![](/Screenshots/Pasted%20image%2020260304181731.png)

4. Configure appropriate descriptions on each interface
For the router R1, I used the following commands:

`int g0/0`

`desc ## To SW1 ##`

Then on SW1:

`int g0/1`

`desc ## To R1 ##`

`int g0/2`

`desc ## To SW2 ##`

Then on SW2:

`int g0/1`

`desc ## To SW1 ##`

5. Disable interfaces which are not connected to other devices
For R1, it's not necessary to do this, since devices are administratively down by default. 

For SW1 and SW2, I used the following command to check the status:

`show interfaces status`

Below, it looks like I'll need to disable fa0/3 - fa0/24 for SW1 and the same for SW2, plus g0/1. Let's try to do this in as few commands as possible.

![](/Screenshots/Pasted%20image%2020260304182834.png)


![](/Screenshots/Pasted%20image%2020260304182853.png)

SW1:

`int range fa0/3 - 24`
`shutdown`

![](/Screenshots/Pasted%20image%2020260304183952.png)
SW2

`int range fa0/3 - 24, g0/2`
`shutdown`

![](/Screenshots/Pasted%20image%2020260304184021.png)

Then, to confirm, I checked the statuses with `show interfaces status`

![](/Screenshots/Pasted%20image%2020260304184308.png)

![](/Screenshots/Pasted%20image%2020260304184320.png)

That's weird, G0/1 on SW1 is showing as notconnect... It looks like it's fully on though. I think I need to go back to that router and run the 'no shutdown' command on G0/0.

![](/Screenshots/Pasted%20image%2020260304184435.png)

Yep, that was it!

![](/Screenshots/Pasted%20image%2020260304184513.png)

Alright, now for each device, I will use `wr` to save the running configuration to the startup configuration as a best practice. 

![](/Screenshots/Pasted%20image%2020260304184622.png)

Voila! The lab is done.