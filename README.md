# DEDSEC-s-Pyhooma


# Ethical-Hacking-Scripts
More Advanced and Powerful Scripts made for pen-testing developped by Retr0.
I might add dev notes to my scripts if I get bored.

# Please Don't Black Hat.
Do not use these scripts for malicious intent. I will not be responsible for any damages.

Only use these scripts if you have permission from the people whom you are attacking, and only for ethical purposes.

# What's in this Repository?
The Scripts in this repository include:
* HTTP-Flood DoS Scripts - Scripts that are aimed at taking down web servers.
* ARP-Poisoning Scripts  - Sending Poisonous Packets to the router for a Man-In-The-Middle-Attack on an IP on your network.
* Packet-Sniffers        - Get your network traffic(Use Linux for better experience).
* XSS-Payload Scripts    - Perform Cross site scripting when you are able to obtain working payloads on a vulnerable Web Server.
* Malware                - Malware that can destroy files on the computer, and can also make it unbootable.
* BotNets                - Botnets that can control and perform unauthorized actions to remote computers.
* Keyloggers             - Log the keystrokes of another person, to possibly extract their password from the keylog.
* Hash Crackers          - Brute force a Hash of a password with these scripts.
* IP Utilities           - Can get information about a specified IP address or host for future attacks.
* Vulnerability Scanners - Scan For online IP Addresses, open ports, and scan for MAC Addreses on a home network.
* Vulnerable Server Scripts - Weak servers that allow you to 'legally' test out Cross site scripting and SQL Injections(if you have nobody's permission).
* Phishing Scripts       - Scripts designed to pose as another site's login page, to extract login information from another user.

There is more to be added.

# Warnings
SquidWare and RansomSquid are very dangerous scripts. RansomSquid will encrypt all of your files, and will only decrypt them if you have the correct key. SquidWare is very dangerous as well, it deletes all of your files as well as ruining your Operating system(makes it unbootable). ONLY RUN THESE IF YOU ARE ON A VIRTUAL MACHINE OR HAVE PERMISSION FROM ANOTHER USER! Unauthorized usage of these scripts on other people is also Illegal.

# Updates
I might consider making more optimised versions of the scripts, perhaps with more functionality.

# Brief Overview of My Scripts(to show that these are actually mine and are not borrowed/copied from other people):

* SquidNet - Read my SquidNet repository(there is a lot of description there). Repo for your info: https://github.com/DrSquidX/SquidNet
* SquidNet2 - The improved version of SquidNet, removing many of the useless features it had, and added some more neccesary protocols. There will a repository soon, however my workload at school will determine whenever that will happen - Repo for your info: https://github.com/DrSquidX/SquidNet2.
* SquidNetSSH - An SSH botnet made for taking control of bots in which they have port 22(SSH Protocol) open for connections. If the Bot-Master has a user and password of one of a device, they could potentially log in with those credentials where they could be able to control the device via SSH. There is also an SSH worm inside of the script, made for if someone wanted to spread the botnet automatically. However the brute forcing on this botnet is very slow, so using an external tool such as Hydra would be useful for that.
* SquidWorm - This worm first generates the payload for which it is used to infect other machines. This is so that it could configure the password file for brute forcing as well as the config for better way of SFTP when a bot has been successfully infected(Different OS's with their different directories can mess things up). It first starts out doing a host scan to get a list of all of the IP addresses in that network. It does so by doing 'arp -a' in terminal and using the information from that to build the IP list(may modify and add the ping scan instead later). I didn't really mention the way the config file worked, so what it does is you need to have the IP, operating system, as well as the username of that IP in a line(for ex. '192.168.0.230 larry windows'). Anyways, after successfully brute forcing and infecting one of the victims, it needs to clone itself in order to spread even more. The worm copies and sends the password list file, config file, as well as the script itself. Once sending it to the victim, it executes the files remotely and the process starts over. To prevent a victim from being infected multiple times, a server is binded at 0.0.0.0:42069(yes, the port is that). Before the brute forcing, the worm sends a request to that server, and if it gets the correct reply, it will not brute force that victim. If it does not send a reply it will brute force.
* HashSquid - HashSquid is a script that was made for hash cracking. You specify the hash to crack as well as the hashing algorithim(md5, sha1, sha225, sha256, sha512, and a few others) and also the password file that has the passwords. The password file would be used to dictionary attack the hash and eventually crack it(if the de-hashed hash is actually in the password list). How it works is that the password file is read top to bottom, where every word would be hashed and compared to the hash that needs to be cracked. If it does find a match then the hash has been cracked.
* SquidIPUtils - A simple IP tool script that allows you to simply resolve a hostname into an IP address, or attempting to reverse DNS an IP into a hostname, as well as using the module 'geocoder' to obtain geolocation info of the specified IP Address. It's overall a very simple and easy tool to use.
* SquidLogger - This script first makes you generate a payload for victims to run later. You specify an IP and port to host the server on(the victims will connect to this server and keystrokes will be logged). You can specify an external IP and port if you choose to do so as well. When victims run the payload, it first sends their IP address to the server(so you can differenciate between clients), and then their keystrokes will be sent to the server. The payload(when generated), will have everything needed to communicate with the Keylog server. It has the IP and Port to connect to, the code to log their keystrokes, as well as the code to obtain their IP address.
* SquidPhisher - SquidPhisher is a phishing server designed to pose as a certain website, however not actually being the same website and having a different function. This function is to obtain the client's username and password. The Phishing server is a web server that obtains the inputs of the clients. How it obtains said inputs is examining the header of the client, where it checks to see if names 'username' and 'password' are in it. If so, it will display that it got the user info of the client. It not only obtains their userinfo, it also obtains their IP address, by looking at the HTTP Header sent by the client, as well as obtaining the User-Agent(get a little info on what the client is using at the moment), and also their geolocation info.
* SquidXSS - This Script requires a text file with XSS Cross site scripting payloads. You also need to provide a website to test the payloads on, to see if the server is vulnerable said payloads. You also need to provide the query tag, so that the server can see that you are 'inputting' something into it. Once done so, the script will send bot requests to the server, where the payloads will be sent in the query tag. In order to see if it works, the Bot requests will also be read to see if the html page recieved by the server contains that payload. If it does so, it is vulnerable to Cross site scripting. Otherwise, it is not.
* SquidMap - SquidMap is a vulnerability scanner, aimed at finding open ports in systems or obtaining MAC Addresses if you're on a home network. You need to specify an IP address, along with the amount of ports you want to scan. The default is 1024, in case you need to know. For the port scanning, it tries to connect to that IP Address and the ports(goes in a for loop), where if it successfully connects, it has identified an open port. For the MAC Address obtaining, it sends ARP(Address Resoultion Protocol) Packets to the router to identify the MAC Address of that IP Address(if it's on the local network). You also have an option to scan the whole network. Simply put '/24' at the end of the IP Address and the script will scan through the whole range of IP Addresses. I believe this only works for windows, since the ping scan utilises the OS Command 'ping'. I made it so that it pings the IP Address once, whereas in other OS's it will constantly ping that IP address nonstop(may add a fix later).
* SquidWare - This is a Trojan Script designed to delete files and also make the computer unbootable. It first asks for Administrative Privallages, so that it has permission to delete system files(makes the computer unbootable). If these permissions are granted, then the Virus does its things. It first obtains all of the directories and files of the computer, where it then tries to delete everything. It of course won't be able to delete everything, as it does not have permission to delete everything. It can delete user files and some system files, which would delete personal files, as well as files needed to make Windows boot. After deleting the files, it waits a few seconds and the computer is shut down. Afterwards, the computer is bricked and it has no personal files.
* RansomSquid - A script that encrypts personal files. It first obtains all of the directories and files inside of the C:/Users directory, where it will try to encrypt every file that it can encrypt. It has an encryption key to encrypt the files. After every file in encrypted, the victim is prompted to enter the encryption key to decrypt all of the files. If the victim closes the python window, their files are truly lost. The attacker would have leverage on the victim, where they would be able to make the victim pay Ransom to obtain the Encryption key to decrypt the files(If you really are that bad of a person).
* SquidDDoS - This is an HTTP Flood script made to take down weak web servers. It has a large list of User-Agents made for generating many different HTTP Headers to send to the server. It has an option to download Proxies from the internet to cover your tracks during an Attack. It also randomly generates query strings and many other things that are needed to generate an HTTP Header. There could be thousands, maybe millions of possible HTTP Headers that could be send to the web server and confuse it. These requests are sent to the server in large masses, but it is more ideal to use this with a lot of devices and attack the web server(You can use SquidNet).
* SquidPoisoner - An ARP Poisoner designed to obtain internet traffic from another device. It first needs to obtain the MAC Addresses of the target and the router, by sending ARP Packets and then obtaining the MAC Addresses of the devices. After doing so, it sends poisonous ARP Packets to these IP addresses where it would confuse them and send their traffic to the Attacker, where the Attacker would basically be the 'Man In The Middle'(This is a type of Man-In-The-Middle Attack). The Attacker can see the targets internet traffic and see what they are connecting to(Check if they are going on any 'weird' or 'questionable' websites).
* SquidSniffer - This is more likely to work with Linux. It makes a Raw Socket where it could intercept the Raw packets(which is internet traffic) and turn them into readable or interpreble strings. It obtains the Ethernet header, in which it displays the Source and Destination MAC Addresses, as well as being able to get IP Headers, TCP Headers, and also UDP Headers that could also be decoded into. There is an option to decode the Hex Dump Binary into strings, where the Hex Dump Strings get converted into strings. Most traffic is encrypted nowadays, so you're more likely to see gibberish.
* WireSquid - You need to have WireShark Installed to use this. It uses the module PyShark, where it uses the code from WireShark to intercept internet traffic. WireSquid gets the source IP's and destination IP addresses as well as the source and destination ports of the traffic. It also obtains the Ethernet headers to obtain source and destination MAC Addresses, as well as also identifying the Protocol of these packets. There is an option to also specify filters, but it is very rough on the edges.

# Other Info
Do not copy these scripts and say they are yours. I am not ok with that. If you plan to modify these scripts, please credit me as I would appreciate that. 

Another thing is that My Vulnerable server scripts were intended to be horrible and very weak against attacks. 

A quick note that SquidNet2 is my most powerful script(It does not reflect on my socket programming skills, as DatCord does). Both versions of SquidNet are linked below, as they have their own repositories. SquidNet2 is the superior version of SquidNet, and should be used rather than SquidNet.

# Happy (Ethical for legal purposes)Hacking, Retr0
