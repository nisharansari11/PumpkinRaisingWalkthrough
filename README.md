
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

Step 10:-  On decoding the code we got a message that “This is just to remind you that it is level 2 of Mission-Pumpkin! ;) ”. Now you have to go back to the view page source in the web browser here you see pumpkin.html file click on that.

![9](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/80e45c6e-4685-4af3-ba6c-ebe4b38296c7)

Step 11:- On clicking on pumpkin.html file you were directed to another source code page. Here you see another encoded code which we have to decode an we can also see some additional information as

Jack used to purchase seeds from the best-sellers and Morse is one among them
To contact sellers, he used to go online using public internet
Poor Jack, he is unaware that people can secretly spy online conversations.
Let’s go get the seeds to raise healthy


From here you have to save some important names in notepad such as

    Jack

    Morse

From the starting webpage I already save lots of information such as

    PumpkinRaising

    jack:

    max:

    acorn:

    Lil' Pump-Ke-Mon:

    SEED WATER SUNLIGHT 


![10](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/df989259-fe0e-4082-b2b7-98b37a064e27)

Step 13:- Now you have to go back to the terminal and decode the encoded code using command 
echo F5ZWG4TJOB2HGL3TOB4S44DDMFYA==== | base32 -d as the encoded code is in the form of base32 code. 


![11](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/ff8f77a2-7596-4812-b5b3-39377e4c8d70)


Step 14:- By decoding the base32 code we get the source path of .pcap file which we have to download using 

![12](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/ede6a919-47b9-4931-90a6-9e8362333f4d)

 wget http://192.168.137.15/scripts/spy.pcap command as wget command is used for downloading the file.



Step 15:-  Now we have to open the spy.pcap file using wireshark as Wireshark is a popular open source graphical user interface (GUI) tool for analyzing packets. However, it also provides a powerful command-line utility called TShark for people who prefer to work on the Linux command line. For that we use wireshark spy.pcap command.


![14](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/564fcfd3-948e-4551-819e-f8aa421fdec1)

Step 16:- On doing wireshark on spy.pcap file it has capture various packets now we have to do right click on any  of above packet and follow it using TCP Stream. On Following it using tcp stream we will get more important  information about the mission. 


“ Hey Jack, Robert has given me your contact.I'm sure I have the seeds that you
want Hi Mark, I'm greatful that you have the seeds Please share the seed ID so that I can get you exact seeds Sure, 50609 is the ID Thank you, I have the seeds. You'll get your seeds in a couple of days Thank you so much Mark You're welcome”

From this information we get More names and seed id Note all important name and information in notepad.

    JACK
    ROBERT
    MARK
    50609


![15](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/ee80efa6-8d97-4e9b-ba90-9170749e52e5)

Step 17:-  Now you have to go back to pumkin.html file source code in the browser here you see a scroll bar on that page on scrolling the page you will find a hexadecimal code in the comments form shown below :-

    <--59 61 79 21 20 41 70 70 72 65 63 69 61 74 65 20 79 6f 75 
    72 20 70 61 74 69 65 6e 63 65 20 3a 29 0a 41 6c 6c 20 74 68 69 6e 67
    73 20 61 72 65 20 64 69 66 66 69 63 75 6c 74 20 62 65 66 6f 
    72 65 20 74 68 65 79 20 62 65 63 6f 6d 65 20 65 61 73 79 2e 0a
    41 63 6f 72 6e 20 50 75 6d 70 6b 69 6e 20 53 65 65 64 73 20 49
    44 3a 20 39 36 34 35 34 0a 0a 44 6f 2c 20 72 65 6d 65 6d 62 65 
    72 20 74 6f 20 69 6e 66 6f 72 6d 20 4a 61 63 6b 20 74 6f 20 70 
    6c 61 6e 74 20 61 6c 6c 20 34 20 73 65 65 64 73 20 69 6e 20 74 
    68 65 20 73 61 6d 65 20 6f 72 64 65 72 2e-->


![16](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/825ada78-6ca6-46bf-9eab-c94a791c5377)

Step 18:-  To decode this hexadecimal code you have to open browser and search cybershef website or just click on the link below:-
https://gchq.github.io/CyberChef/

Now you have to paste the hexadecimal code in the input section of the website and on the left section click on from hexadecimal. Now you can see the hexa decimal code is decoded and gives us important information that :-

“Yay! Appreciate your patience :)
All things are difficult before they become easy.
Acorn Pumpkin Seeds ID: 96454
Do, remember to inform Jack to plant all 4 seeds in the same order.”

From this information we get :-

    Acron id :- 96454
    Jack id   :-  50609

![17](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/02d694d7-845b-4f0a-bf57-928b3545d257)


Step 19:- Now we have to find some hidden data so we have to see the robots.txt file of the ip address for that we have to use command:-

curl http://192.168.137.15/robots.txt   as robots.txt file is to prevent the crawling and indexing of certain parts of your site by web crawlers and spiders run by sites like Yahoo! and Google. By telling these "robots" where not to go on your site, you save bandwidth and server resources.

On doing that we find two Files which is important :-

    hidden/note.txt
    /seeds/seed.txt.gpg

![18](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/32d3fbf9-f380-4c93-8cca-9a6332ffb4c8)

Step 20:- Now we have to open /hidden/note.txt file using 

curl http://192.168.137.15/hidden/note.txt  command.

On opening it we find 

    Robert : C@43r0VqG2=
    Mark : Qn@F5zMg4T
    goblin : 79675-06172-65206-17765

![19](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/305d7df8-50c5-4618-a95e-f57ad5f017e5)


Step 21:- Now you have to go back to pumkin.html file source code in the browser here we find another underconstruction.html file source code click on that. On clicking on that you were directed to another source code page here you find some more clues.

Looking for seeds? I ate them all!
jackolantern dot GraphicsInterchangeFormat is under images

![20](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/5b039845-3b61-46d7-84ca-f77a3fca7470)




Step 22:- On decoding the above message we decode that this is an image jacolantern.gif which contain pumpkin raising seed. Now we have to find the seed. For that we have to first download the image for downloading the image we have to go back to the terminal and write:-

wget http://192.168.137.15/images/jackolantern.gif  Command.

![21](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/6d98cc98-a805-45c5-ae93-57b124b37373)


Step 23:- Now we have to find the seed in the image using :-

 stegosuite jackolantern.gif command as stegosuite is is a graphical steganography tool. It is used to hide secret data or information in image files. Stegosuite provides the facility of embedding text messages and multiple files of any type. On doing stegosuite on the image the stegosuite tab will open which will demand a password for extracting. Now if you remember we have find password of 3 person earlier Mark, Robert, Goblin here we have to will one of the password among them On entering the all three passwords we find that Mark password is correct for extracting On Cling on extract we got a decorative.txt file now we have to click on Embed for downloading the file.

![22](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/087dd59b-367a-4c7e-ac9c-f545c46590cb)


Step 24:- Now we have to open decorative.txt file for opening decorative.txt file we have to go back to terminal and using cat decorative.txt command to open the file. On opening file we got a message and Lil' Pump-Ke-Mon seed id.

Fantastic!!! looking forward for your presence in pumpkin party.

    Lil' Pump-Ke-Mon Pumpkin seeds ID : 86568  

![23](https://github.com/nisharansari11/PumpkinRaisingWalkthrough/assets/117331485/2233691b-2c16-4c99-af2f-c2fee7a3fbd3)


Step 26:- Now we have to open and decode the seed.txt.gpg file for opening it we have to use gpg -d seed.txt.gpg command. On  decoding it it  demand you for password I do lots of effort and decode that the password is SEEDWATERSUNLIGHT as written on webpage of the ip. On opening and decoding the seed.txt.gpg we got a morse code.




Step 27:- Now we have to decode the morse code to decode the morse code we have to open the browser and search for cybershef website again enter the morse code in input section and from the left side bsr click on from morse code.On decoding the morse code we got big max pumpkin seed id 

    T  T     I   E OF U   M N  YIPPEE! YOU ARE ON THE RIGHT PATH... BIGMAXPUMPKIN SEEDS ID: 69507

Now we have seed id of all 4 i.e

    50609 - Jack's
    96454 - Acorn's
    86568 - Lil' Pump-Ke-Mon Pumpkin   
    69507 - Big Max Pumpkin's




Step 28:- Now we have to arrage the seed id as per the first webpage of mission pumpkin i.e
Big Max Pumpkin's - Jack's - Acorn's - Lil' Pump-Ke-Mon Pumpkin

After arrangement the password for mission 
pumpkin raising is:-
69507506099645486568 

Now using ssh jack@192.168.137.15 command we have to login to mission pumpkin raising it demand for the password we have to enter the seed id password which we have decoded above.




Step 29:- Now we are inside the pumpkin raising now we have to find the flag.txt file.
Now we have a foothold on the box, we can run a basic command to see if any sudo privileges are available to us for that we use sudo -l command




Step 30:-We can see that we have access to run the /usr/bin/strace command, which we can take advantage of to escalate our privileges.

Running this command will execute strace, redirect the trace output to /dev/null and run a bash shell as the root user:

sudo strace -o/dev/null /bin/bash

We are then able to switch to the /root directory and read the contents of flag.txt:


Hence we got the flag.txt file
Our CTF Mission Pumpkin Raising is completed successfully.



