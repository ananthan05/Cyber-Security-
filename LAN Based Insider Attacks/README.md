## TOOL USED HERE
### ETTERCAP
Ettercap is a comprehensive, open-source network security tool used for analyzing, monitoring, and manipulating network traffic in a computer network. Originally developed for Unix-like operating systems, it has since been adapted for Windows as well. Ettercap operates as a man-in-the-middle (MITM) attack tool, allowing cybersecurity professionals, penetration testers, and ethical hackers to inspect and modify data as it passes through a network.

### Familiarization with tool

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/c925e528-b037-416f-bbd9-e0d9f40a41e7)


So here we set the interface on which have to start sniffing and related attacks. Then we start sniffing on the interface.

## ARP Cache Poisoning
ARP spoofing is the process of linking an attacker’s MAC address with the IP address of a legitimate user on a local area network using fake ARP messages. As a result, data sent by the user to the host IP address is instead transmitted to the attacker.

### CAUSE OF ATTACK
The main cause of ARP spoofing attacks is the fundamental trust issue within the Address Resolution Protocol (ARP) itself. ARP is a network communication protocol that helps devices translate IP addresses, which are easy for humans to remember, into MAC addresses, which are the unique identifiers used by network devices.

### PREVENTION
We can prevent it by implementing the IDS(Intrusion detection system).
Using the Arp-spoof detecting software.

### PERFORMING THE ATTACK
First we discover all the hosts and choose the target on which we want to perform ARP spoofing attack.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/8abf25bb-0c56-488d-b871-3c4e8b0e35ce)

To find the Victim gateway.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/f23502a5-0775-4bcc-b02c-8f5a42c77964)

So here the target is 192.168.21.128 and the target gateway is 192.168.21.2

Then we perform the ARP poisoning attack

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/e62d5c8f-2abc-441d-b7c2-bb39c231ba25)


Now we can see that we are able to see the traffic. So our attack is successful.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/bed044a2-5029-4097-afa0-51c606d31cfb)


When analyze the Splunk reports we can see that http request was successful but there was no sign of showing ARP spoof.



## Perform Denial of Service (DoS) attacks using ARP Cache Poisoning attacks.

The DoS (Denial of Service) attack plugin in ettercap is used to overload a target system or network with traffic in order to prevent the system or network from operating normally. This attack aims to prevent authorised users from accessing the target system or network. The way the DoS attack plugin in ettercap operates is by flooding the target with a lot of network traffic. Requests sent over the network, such as HTTP or DNS inquiries, might be considered genuine traffic.

As like the previous steps,

Scan for hosts

Add hosts as target (only the target ip & not the gateway ip)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ffbc16e0-a668-4ec0-b365-e79879142357)

Start arp poisoning the victim. 

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/cd343bff-c91a-484b-a10a-059ef3c6db3d)

And now run the dos_attack plugin.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/4a1abc86-03a1-4974-9eb2-e394c7f68198)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/0eb005c5-8a27-4b78-ac77-66795e514ed2)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ae79726c-674c-42aa-a9e5-ad6e2ef84f62)

IN victim Machine.

The victim becomes sluggish as soon as we enable the plugin since the target IP starts sending the victim a large number of packets. Therefore, the victim's web searches just never stop loading.

![WhatsApp Image 2024-02-17 at 21 50 42_c06541b8](https://github.com/ananthan05/Cyber-Security-/assets/140697378/aaa5707f-33aa-4fc3-ad90-a79583021267)


