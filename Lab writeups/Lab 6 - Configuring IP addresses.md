![](/Screenshots/Pasted%20image%2020260303175444.png)

1. Configure R1's hostname

For this one, first I click R1, (hard to see in the screenshot but it's right below), then I click "CLI", then enter the following:
`enable`
`conf t`
`hostname R1`

![](/Screenshots/Pasted%20image%2020260303175613.png)


2. Use a 'show' command to view a list of R1's interfaces, their IP addresses, status, etc.
I used the following command to see this:

`show ip interface brief`

![](/Screenshots/Pasted%20image%2020260303180145.png)

3. Configure the appropriate IP addresses on R1's interfaces, and enable the interfaces

Configure appropriate interface descriptions

For this one, I used the following commands:
`conf t` to enter global configuration mode
`int g0/0`
`ip address 15.255.255.254 255.0.0.0
`no shut`

`int g0/1`
`ip address 182.98.255.254 255.255.0.0`
`no shut`

`int g0/2`
`ip address 201.191.20.254 255.255.255.0`
`no shut`

![](/Screenshots/Pasted%20image%2020260303180939.png)

Then I configured the descriptions:

`int g0/0`

`desc ## To SW1 ##`

`int g0/1`

`desc ## To SW2 ##`

`int g0/2`

`desc ## To SW2 ##`

![](/Screenshots/Pasted%20image%2020260303181718.png)

4. Use a 'show' command to verify R1's interfaces again.

For this, while still in global config mode, I used `do show ip int br`

![](/Screenshots/Pasted%20image%2020260303181037.png)

5. View the running config to confirm the configuration changes, then save the config

From here, I exited the interface and global config, and then used `show running-config` and scrolled down.

![](/Screenshots/Pasted%20image%2020260303181839.png)

After that, I used the command `wr` to write the running config to the startup config.

6. Configure the IP addresses of PC1, PC2, and PC3
To do this, I clicked into PC1, then Config > FastEthernet0

![](/Screenshots/Pasted%20image%2020260303182022.png)

Then configured it to 15.0.0.1

Next, I did the same for PC2 - configuring it to 182.98.0.1 and PC3 - configuring it to 201.191.20.1

7. Ping from PC1 to PC2 and PC3 to test connectivity
Alright, from PC1 > Desktop > Command Line, I pinged the other two PCs with the following commands:

`ping 182.98.0.1`

`ping 201.191.20.1`

And got the results below.

![](/Screenshots/Pasted%20image%2020260303182306.png)

Weird! One of the pings timed out but the others came through. The same happens in the lab video, so I'm not that worried about it. We're getting responses, so that's what matters. Yay! The lab's all done!