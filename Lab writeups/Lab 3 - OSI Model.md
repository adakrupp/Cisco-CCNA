Today I am using packet tracer's simulation mode to learn about the OSI model. I press the 'Simulation' mode, then I press play below. It starts sending out traffic. 


If I click "SW2", for STP traffic that is generated it shows more detail in regards to to the layers of the OSI model in Layer 2. In Layer 2, it shows the steps that are happening there. 

It shows IEEE 802.3 header, so this is an ethernet header.


![](/Screenshots/Pasted%20image%2020260228140535.png)

After that, I click 'Layer1'

This time, it shows what's happening on Layer 1 for the same traffic. It shows information about the ports being used, so this is the Physical layer.
![](/Screenshots/Pasted%20image%2020260228140706.png)

Next, I click 'R1' (router1) with the type OSPF. 

OSPF is a layer 3 protocol. Its job is to find the best path in the networks. OSPF has Layer 3, 2, and 1 information. 
![](/Screenshots/Pasted%20image%2020260228140923.png)

Next, I will generate some DHCP traffic, in order to see some Layer 7 (or Layer 5) traffic. First, I will click PC1 in Packet Tracer. Then I will click Desktop.

![](/Screenshots/Pasted%20image%2020260228141209.png)

Then I click "Command Prompt" to use that to release and renew the IP address.

![](/Screenshots/Pasted%20image%2020260228141243.png)

If I type in `ipconfig`, it will show the IP address:

![](/Screenshots/Pasted%20image%2020260228141322.png)

Next, I type in `ipconfig /release` and then `ipconfig /renew` in order to release and renew the IP address, generating DHCP traffic.

![](/Screenshots/Pasted%20image%2020260228141527.png)

I click this to show the traffic. Notice that there is no layer 5 or 6 traffic, as they are all combined into Layer 7 because we are using the TCP/IP model. 

![](/Screenshots/Pasted%20image%2020260228141604.png)

And that's it for this lab! Pretty simple stuff!

