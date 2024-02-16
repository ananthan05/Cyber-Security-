### Use the tool NMAP [Command line only]to perform the below task. Run Wireshark in the background and capture only the necessary packets to showcase for the corresponding question.

#### a) Explain the subnet and use the NMAP Command to scan the services for the whole subnet.

A subnet, short for subnetwork, is a logical subdivision of an IP network. It allows for the division of a larger network into smaller, manageable parts. Subnetting is primarily used to improve network performance, security, and organization. Each device on a network is assigned an IP address, and subnetting helps in efficient routing of data packets within the network.

Command to scan entire subnet  `nmap -sV <subnet/CIDR notation>`

*Victim Machine*

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/b6392aff-d900-452a-8909-ea9825790166)

*Attacker Machine*

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/6a0d258e-4483-4e2c-9c9c-9a3881762a63)

#### b) What is a firewall,andmention its types. Use the NMAP command to detect that a firewall protects the host.

#### Firewall 

- A firewall is a type of network security appliance that keeps an eye on and regulates inbound and outgoing network traffic in accordance with pre-established security rules. Its main goal is to defend devices and networks from malicious activity, assaults, and unauthorised access. It is possible to deploy firewalls using hardware, software, or a combination of the two. They function by looking at network traffic packets and comparing them to the administrator's preset rules or policies. 

- A packet is permitted to get across the firewall if it matches a rule. If it doesn't fit any of the rules, it's either rejected or forwarded to another place for more examination.

#### firewall types
- Software firewall. 
- Hardware firewall. 
- Packet filtering firewall. 
- Circuit-level gateway. 
- Proxy service application firewall.

 #### The NMAP command to detect if a host is protected by a firewall. Here’s an example of how you might do this:

`nmap -sS -p- <target-ip>`

In this command:

`-sS` option tells NMAP to perform a SYN scan, which is a type of stealth scan.
`-p-` option tells NMAP to scan all 65535 ports.
This command will send a TCP SYN packet to each port on the target host. If the port is open, the target will respond with a SYN/ACK packet. *If the port is closed, the target will respond with a RST packet. If there is no response, or the packet is dropped, it’s likely that a firewall is protecting the host.*


*Victim Machine when firewall is on*

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/578b0788-44ee-4281-9611-e57ab582e57a)

*Attacker Machine*

There is no response. So it’s likely that a firewall is protecting the host

![Screenshot 2024-02-16 233309](https://github.com/ananthan05/Cyber-Security-/assets/140697378/23a11cf0-59fa-44ef-80d8-d18df4fb7a44)

*Victim Machine when firewall is off*

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/b3d1390b-eab0-4842-b583-d31a49c5b022)

*Attacker Machine*

![Screenshot 2024-02-16 233818](https://github.com/ananthan05/Cyber-Security-/assets/140697378/4479ba91-c2f7-45a3-b731-fe677859b228)


#### c) Use the NMAP command to scan a network and determine which devices are up and running.

Command - `nmap -sn <ip>/<CIDR> `

*Attacker Machine*

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ef9d349a-0af7-407b-bb49-e49d837755fc)


#### d) What are vertical and horizontal scanning?

- `Horizontal scanning ` sends requests to the same port on different hosts. Attackers use horizontal scanning to prepare for a mass attack.
- `Vertical scanning` sends requests to different ports on the same host. Attackers typically use vertical scanning to look for vulnerabilities in a preselected target.


#### e) Use the NMAP command to scan multiple hosts. [HINT: Add hosts into a file and scan it].

*Attacker Machine*

WE need to add the ip address of the Victim Machine `192.168.192.131` to `/etc/hosts` file.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/f7d0a54e-f32c-4a6e-b9ab-a9b2193e6dd4)

#### f) Use NMAP commands to export the output in XML format.

*Attacker Machine*

Use the  `nmap -sV <target-ip> -oX name.xml`

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/1c60b046-ae16-4d91-97d6-c3299da52aa2)


#### g) Use the NMAP command to get OS information about a host.

 *Attacker Machine*

  `nmap -O <target-ip>`

  ![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/e364c609-a212-49da-8d63-d081e8964e60)

  #### h) Explain ping sweeping and Perform ping sweeping using Nmap

#### Ping Sweep

A method of network reconnaissance called "ping sweeping" is used to find out which IP addresses are active and reachable within a network. To find out which IP addresses are reachable and available, it entails sending a string of ICMP echo request messages, or pings, to a variety of addresses, usually in a sequential manner.

Network administrators frequently use ping sweeping to map the network and find active hosts.

Nmap command to perform ping sweep - `nmap -sn <network address>/<CIDR>`.

 *Attacker Machine*

 ![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/1278d6f9-e000-4fc6-ae23-dadeffbd9ebb)






