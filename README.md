
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

![6](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/ee0ca80c-6f54-46f8-84b9-efd89b934939)

Step 8:-  On searching the ip address on web browser you were directed to pumpkin raising webpage which contain lots of information about the pumpkin raising . Make sure to note the important information such as names any kind of data from this webpage .Now you have to see the page source code by right clicking on the web page and then click on view page source code.

![7](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/a129aa05-2a56-4bdc-920f-dc29705d2d9c)

Step 9:-  On Entering the view page source we can see a encoded message in the form of comment so we have to copy that message and go back to the terminal and use 
echo VGhpcyBpcyBqdXN0IHRvIHJlbWFpbmQgeW91IHRoYXQgaXQncyBMZ  XZlbCAyIG9mIE1pc3Npb24tUHVtcGtpbiEgOyk=|base64 -d command to decode the encoded code. We can also use base64 decoder to decode the code as the encoded code is in format of base64.

![8](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/ae13a84f-981e-45b3-9906-486b02d6194d)





