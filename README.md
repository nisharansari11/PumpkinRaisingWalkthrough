
# Pumpkin Raising Walkthrough

Pumpkin Raising is a CTF Challenge which from Mission Pumpkin Series.

 Penetration Techniques:-

Scanning:-

    1)Nmap 

Enumeration:-

    1)Txt
    2)Abusing HTTP services
Exploiting:-

    1)SSH Login
Privilege Escalation

    1)Abusing Sudo Right

Walkthrough

Step 1:-Open VMware/Virtual Box in your system and play Kali–Linux Virtual machine and Pumpkin Raising in it.








![App Screenshot](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/8279a968-8982-4751-8961-c619ef000fd3)






Step 2:-On playing kali-linux virtual machine a new window will appear as shown below after the completion of booting of kali-linux enter the id and password as kali.



![App Screenshot](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/blob/main/ScreenShot/2.png?raw=true)


Step 3:-  After entering the id and password as kali the kali virtual machine starts and we are able to use all the features of kali linux.

![App Screenshot](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/blob/main/ScreenShot/3.jpg?raw=true)

Step 4:-On playing Pumpkin Raising virtual machine a new window will appear as shown below after the completion of booting of Pumpkin Raising we will se an ip address of the machine from here we have to copy ip address of the machine and paste it in the notepad.

![3](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/1f0c15e7-22d5-4787-a9c6-fde891ab5118)

Step 5:-  Now go back to the kali linux and open the root terminal. In the terminal write ping 192.168.137.15 as  ping command is a simple utility used to check whether a network is available and if a host is reachable or not. After starting ping command if host is reachable press ctrl + c to stop the ping command.

![4](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/a6afef27-f733-4bfa-bc32-2dc2c82f4035)

Step 6:-  Now we have to find the all open pots of the ip for which we use  nmap -A -p- 192.168.137.15  command. As nmap  command is used for:-

•	Real time information of a network

•	Detailed information of all the IPs activated on your network

•	Number of ports open in a network

•	Provide the list of live hosts

•	Port, OS and Host scanning

![5](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/c73c01eb-b210-4ca9-a589-1b6544d58f61)

Step 7:-  By using Nmap command we can clearly see that two ports ssh and http are open and they are running on common port so we have to open the web browser and type the target/pumpkin raising ip address in the search bar and search as it is running  on http port.

