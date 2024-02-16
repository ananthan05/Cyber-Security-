### Lan Based Insider Attack 
### Performing the attack

First we need go to 
`mousepad /etc/ettercap/etter.conf`
we need set the ec_uid = 0, ec_gid = 0  

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ea75098a-bc29-4cf7-86da-713382f774ab)

we have remove the hashes from linux category

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/59ce5dc3-be35-476d-a482-9b106b37b3d2)

then go to `mousepad /etc/ettercap/etter.dns`
and the domain that we need spoof and add the ip of the attcker system

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/822f819e-0458-4f3a-ae06-a23dc57db176)

after confguring both this file we need start our own apache server before that go to  `cd /var/www/html` and modify index.html.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/b3a748db-f878-4890-969a-585c485a6ecc)

and then start apache server `service apache2 start`.And no go to `ettercap -G`.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/983d7851-a5f6-468c-92fd-3cd69e0aa2da)

after starting after few seconds we need to press the stop on the bottom left side.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/2493767e-066c-4d60-a429-90b944bde8a7)

after that we need scan for the network which means the connected device ans will display some host lists.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/2446906a-ba80-4367-8416-5bd2c5f0243b)

then we need go to the host list and we need all the hosts in target 1 or target2.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/ce5bcdda-7abd-4a3a-9bc8-1ffa82cb89ec)

and go to plugins and select mange plugins the click on dns spoffing and it will show activating it.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/267d6827-0eda-4081-aa34-0f43e41c5558)

then select arp spoffing and  click ok.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/79b15e88-bc0f-426b-80cc-77b3374e8259)

and go to victims machine  and check if the attack is sucessfull.

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/74c36154-7a6d-403d-bd65-e587dec87e86)

IDENTIFY THE SOURCE OF THE ATTACK JUST BY USING SPLUNK LOGS

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/8205f5e5-a766-4df3-9c25-bdb394ac57b8)

![image](https://github.com/ananthan05/Cyber-Security-/assets/140697378/e6778b1a-c93c-4bd4-b4b2-750fa9fabe27)




