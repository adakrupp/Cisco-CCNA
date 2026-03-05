This is the lab for Jeremy's IT Lab - Free CCNA Day 2
### Instructions: 

Connect the network devices together according to the labels. Use the appropriate type of cable. For practice, assume that Auto MDI-X is disabled, or not supported on the devices.

NOTE: Packet Tracer doesn't differentiate between single-mode and multimode fiber, but think about which one is appropriate when you use a fiber connection.


For this lab, I will be connecting devices together with my newfound knowledge of UTP cables vs different types of Fiber-Optic cables.

First, I will put down the distances each cable can connect with:

UTP - 100M
Multimode Fiber - 400m (10Gbps) to 550m (1Gbps)
Single-Mode Fiber 5KM (1Gbps) - 10-30 km (10Gbps)

Here is what we need to connect:

![](/Screenshots/Pasted%20image%2020260227125542.png)

So I think I'll start by building a table to be able to see things more clearly:

| Connection | Distance       | Cable type              | Straight-through or crossover |
| ---------- | -------------- | ----------------------- | ----------------------------- |
| R1-R3      | 3km            | Single-Mode Fiber-Optic | N/A                           |
| R1-R2      | 50m            | UTP                     | Crossover                     |
| R2-SW1     | Less than 100m | UTP                     | Straight-through              |
| R2-SW2     | Less than 100m | UTP                     | Straight-through              |
| SW1-SW2    | Less than 100m | UTP                     | Crossover                     |
| SW1-SW3    | Less than 100m | UTP                     | Crossover                     |
| SW2-SW4    | Less than 100m | UTP                     | Crossover                     |
| SW3-PC1    | Less than 100m | UTP                     | Straight-through              |
| SW4-PC2    | Less than 100m | UTP                     | Straight-through              |
| R3-R4      | 250m           | Multimode Fiber-Optic   | N/A                           |
| R4-SW5     | Less than 100m | UTP                     | Straight-through              |
| R4-SW6     | Less than 100m | UTP                     | Straight-through              |
| SW5-SW6    | Less than 100m | UTP                     | Crossover                     |
| SW5-SW7    | Less than 100m | UTP                     | Crossover                     |
| SW6-SW8    | Less than 100m | UTP                     | Crossover                     |
| SW7-PC3    | Less than 100m | UTP                     | Straight-through              |
| SW8-SRV1   | Less than 100m | UTP                     | Straight-through              |

There we go! Mostly UTP cables with a single-mode Fiber Optic and a Multimode Fiber-Optic. I assume because no further info was given that the connections that did not mention distance were less than 100m.

Now that I've made the table, the connections should be pretty straightforward.

![](/Screenshots/Pasted%20image%2020260227132242.png)

Easy peasy! This lab is done.