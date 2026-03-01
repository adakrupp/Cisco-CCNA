In this lab I will be getting hands-on with the Cisco IOS CLI. Here are the lab instructions:

1. Change the hostnames of the router and switch to the appropriate names (R1, SW1)
- Use the 'hostname' command in global configuration mode##
So first, I will click into these two, go to 'CLI' at the top, and run the following commands:
`enable`
`conf t`
SW1:`hostname SW1`
R1: `hostname R1`

![](/Screenshots/Pasted%20image%2020260228160906.png)

![](/Screenshots/Pasted%20image%2020260228161130.png)
![](/Screenshots/Pasted%20image%2020260228161144.png)

2. Configure an unencrypted enable password of 'CCNA' on both devices
Keeping both terminals open, I will type the command below for both:
`enable password CCNA`
![](/Screenshots/Pasted%20image%2020260228161512.png)
![](/Screenshots/Pasted%20image%2020260228161522.png)

3. Exit back to user EXEC mode and test the password
First I put in the `exit` command twice, then I put in `enable` and got the following on both:
![](/Screenshots/Pasted%20image%2020260228161633.png)
![](/Screenshots/Pasted%20image%2020260228161659.png)
4. View the password in the running configuration
After typing in the password, I used the `show running-config` command in user EXEC mode.
![](/Screenshots/Pasted%20image%2020260228161801.png)
![](/Screenshots/Pasted%20image%2020260228161814.png)
5. Ensure that the current password, and all future passwords, are encrypted
From here, I put in `conf t` to get back to Global Configuration Mode, then I used the command `service password-encryption`
6. View the password in the running configuration
Once again, I exited Global Configuration Mode with `exit`, then I used the command `show running-config`
![](/Screenshots/Pasted%20image%2020260228162308.png)
![](/Screenshots/Pasted%20image%2020260228162322.png)
7. Configure a more secure, encrypted enable password of 'Cisco' on both devices
Again, I used `conf t` to go back into global configuration mode, then used the command `enable secret Cisco` to set the new password.
8. Exit back to user EXEC mode and then return to privileged EXEC mode.
- Which password do you have to use?
From here `exit` command twice, then used the `enable` command and typed in the password 'Cisco'
9. View the passwords in the running configuration.
From here, I typed in the `show running-config` command.

![](/Screenshots/Pasted%20image%2020260228162715.png)

![](/Screenshots/Pasted%20image%2020260228162735.png)

- What encryption type number is used for the encrypted 'enable password'?
7
- What encryption type number is used for the encrypted 'enable secret'?
10. Save the running configuration to the startup configuration
For this instruction, I used the `write` command on both.
![](/Screenshots/Pasted%20image%2020260228163023.png)

![](/Screenshots/Pasted%20image%2020260228163031.png)