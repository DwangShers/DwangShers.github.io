---
Title: SWS101 Journal 1
categories: [SWS101, Journal1]
tags: [SWS101]
---

## Topic : Networking and OverTheWire Bandit
----
### networking

Basic Networking Concepts:

Networking Devices:
1. Router: Connects extraordinary networks together.
2. Switch: Connects gadgets inside a neighborhood community.
3. Hub: Connects a couple of devices in a LAN but operates on the bodily layer.
4. Modem: Converts virtual information from a laptop into alerts appropriate for transmission over communique strains.

Network Topologies:
1. Point-to-Point: Direct connection among two gadgets.
2. Star: Devices connect with a significant hub or transfer.
Three. Mesh: Devices connect with each other at once.
Four. Hybrid: Combination of various topologies.
5. Bus: Devices join along a single cable.
6. Ring: Devices join in a circular way.
7. Tree: Hierarchical association of gadgets.
Eight. Daisy Chain: Devices join sequentially in a series.

Network Types:
1. WAN (Wide Area Network): Covers a massive area just like the net.
2. LAN (Local Area Network): Covers a constrained area like home or office.
Three. WLAN (Wireless Local Area Network): Uses Wi-Fi inside a restrained area.
4. VPN (Virtual Private Network): Connects multiple networks securely.

Proxy:
A mediator between connections, with types like ahead, reverse, and obvious proxies.

Networking Models:
1. OSI Model (Open Systems Interconnection): 
   - Defines verbal exchange features into seven layers:
     - Physical, Data-link, Network, Transport, Session, Presentation, and Application.
2. TCP/IP Model (Transmission Control Protocol/Internet Protocol):
   - Comprises 4 layers: Link, Internet, Transport, and Application.
   - Used for statistics packet switching and transport at the Internet.

Relationship between OSI and TCP/IP Models:
- The Link layer in TCP/IP corresponds to the Physical and Data Link layers in OSI.
- The Network layer in TCP/IP corresponds to the Internet layer.
- The Transport layer in TCP/IP fits the Transport layer in OSI.
- The Application layer in TCP/IP corresponds to the Session, Presentation, and Application layers in OSI.

---
### SSH(Secure Shell)

Cryptography/cryptology is the practice and study of techniques for secure communication in the presence of adversarial behavior.
Generally cryptography is about constructing and analyzing protocols that prevent third parties from reading private messages.

The Secure Shell Protocol(SSH) is a cryptographic network protocol for operating network services securely over an unsecured network. 

#### What is Bandit? 

Bandit is the recommended starter “wargame” for the overthewire suite of games. It goes over simple Linux commands and ramps up into more advanced techniques as the game gets into higher levels.

---
---
#### Bandit level

* Level 0: 

The goal is to log into the game using SSH. The host needed to connect is bandit.labs.overthewire.org, on port 2220. Username and password is bandit0.


Solution: To log into the host, the command we have to run in the terminal is;

#ssh username@ssh.server.com -p 2220

#ssh bandit0@bandit.labs.overthewire.org -p 2220

---
* Level 0 - level 1:

At this level our goal is to find the password for bandit1, but it’s already specified that password is stored in a file called readme.

Solution : To solve this problem, we need to use two commands ls and cat. (ls) command is used to list the contents of a directory on the remote server.

#ls   Output : readme

Now we need to read the readme file by using cat;

#cat readme

Password for bandit1 : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

[Note that to log into the next bandit, we will have to exit from the previous bandit using (exit/exit) -d command.]

---
* Level 1 - level 2: 

The goal is to find the password from a file called _(dashed file).
Solution : We can use (ls) command to list contents or we can use (ls -a) to list all contents.

#ls Output: _

So, to open this type of file we have to specify the full location by;

#cat ./_

Password for bandit2: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

---
* Level 2- level 3:

The goal is to find the password from a file called spaces in this filename.

[Note: Files in linux usually do not contain spaces in their name]

So, to deal with the spaces in filename, there are two ways:

1. Wrap the entire filename between quotes;
“file name with spaces”

2. Escape every space using backslash key;
file\ name\ with\ spaces

Solution : We can use either ways, so I’m going with the first one;

#cat “spaces in this filename”

Password for bandit3 : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

---
* Level3 - level4: 

The goal is to find the password from a hidden file in the inhere.

Solution : To find the password from a hidden file, first we will have to use the cd(change directory) command on inhere.

#1. cd inhere

#2. ls -a 

Output: . .. .hidden  (We can see that the password is in the hidden)

#3. cat .hidden

Password for bandit4 : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

---
* Level4 - level5:

Goal is to find the password from a file which is stored in the only human-readable file in the inhere. We can find that there are many files in the inhere directory, so, to make it easy, we can use (file) command to determine the type of a file without opening it.

Solution : #file inhere/*  (the little asterisk at the end is called a wildcard. They allow to search the directory for a specific pattern and in this case, it searches through every file)

Output : inhere/-file00: data

inhere/-file01: data

inhere/-file02: data

inhere/-file03: data

inhere/-file04: data

inhere/-file05: data

inhere/-file06: data

inhere/-file07: ASCII text

inhere/-file08: data

inhere/-file09: data

So, we can find that -file07 is the one;

#cat ./inhere/-file07

Note that we will have to specify the directory.

Password for bandit5 : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

---
* Level5 - level6:

Goal is to find the password from file somewhere under the inhere which has following properties: 

Human-readable

1033 bytes in size

Not executable 

Solution : First go to the inhere directory. We will have to use (find) command to search for files in a directory hierarchy. 

#find -readable -size 1030c ! -executable 

Output : ./maybehere07/.file2

Then, #cat maybehere07/.file2

Password for bandit6 : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

---
* Level6 - level7: 

Goal is to find password from somewhere on the server which has following properties;

owned by user bandit7

owned by group bandit6

33 bytes in size

Solution : #find / -user bandit7 -group bandit6 -size 33c

From the output we can find that only /var/lib/dpkg/info/bandit7 .password is not denied. 

So, #cat /var/lib/dpkg/info/bandit7 .password

![alt text](<../image/Screenshot from 2024-03-10 01-25-20.png>)

Password for bandit7 : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

---
* Level7 - level8: 

The password for the next level is stored in the file data.txt next to the word millionth

Solution : We will have to use grep to find the password which is said to be next to millionth.
So, grep command is used for searching and matching text patterns in files contained in the regular expression.

#grep millionth data.txt 

Password for bandit8: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

---
* Level8 - level9:

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

When we check the data.txt, we will find a bunch of texts which are not sorted.
First we will have to sort the texts, then find the unique texts to find the password.

Solution : #"sort data.txt | uniq -u"

Password for bandit9 : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

---
* Level9 - level10:

We can find many binary words when we “cat data.txt”. So, to find the password (strings) command is used to find humanreadable texts, and we also should use grep to find the words with “=”.

Solution: #"strings data.txt | grep “===”"

Password for bandit10: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

---
* Level10 - level11:

The password for the next level is stored in the file data.txt, which contains base64 encoded data

Solution : Since the data.txt file contains  base64 encoded data, we just need to decode the data using base64 command with -d.
#base64 -d database

Password for bandit11:  6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

---
* Level11 - level12:

From the goal statement, it's been said that all the uppercase and lowercase letters have been rotated by 13 positions. Here we can see that Caeser Cypher method is being used.
In rot13 each letter is shifted 13 places. 

So, to solve this problem we have to again rot 13 to get the password.
 
Solution : #"cat data.txt | tr a-zA-Z n-za-mN-ZA-M"
	
Password for bandit12 : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

---
* Level12 - level13: 

In this level the password is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. xxd command creates a hex dump of a given file or standard input.  It can also convert a hex dump back to its original binary form.

So, to find the password, we will have to use xxd command and revert the file to get the password.

Solution : first as instructed in the statement, we will have to create a file directory under tmp, since we don’t have the permission to cat the file. And copy the datafile using cp.

Command line : #mkdir /tmp/lv12 	

#cp data.txt /tmp/lv12		

#cd /tmp/lv12

Then we will  have to convert the hex dump back to its original form by; 
	
Command line : #"cat data.txt | xxd -r > data1"  

Here, the arrow(>) tells it to revert the file into that new file data1.

Then, using the file command we can find what type of file we are working with. 
		
#file data1
		
Output : data1: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573

Here the file type is gzip so, we will have to rename the file. 

#mv data1 ./data2.gz  Then,  #zcat data2.gz > data3  

And  

#file data3 

Output: bzip2 compressed data, block size = 900k 

Here the file type is bzip so, we will have to do the same step. When the file is in tar type, then we will have to use # tar -xvf “filename” and then follow the same step until we get an ASCII text type file. 

Finally : # cat “filename”

Password for bandit13 : wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

---
* Level13 - level14: 

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. But, for this level we don't get the password, but we get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

Solution : So, as it’s said; we will have to use the private key to login to bandit14 and find the password that’s stored in /etc/bandit_pass/bandit14.
	
Command line : ssh -i sshkey.private bandit14@localhost -p 2220
	
Then, we just cat from the file /etc/bandit_pass/bandit14 ;

#cat /etc/bandit_pass/bandit14 
		
Password for bandit14 : fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

---
* Level14 - level15:

To get the password for this level we will have to submit the password of level14 to port 30000 on localhost.

Solution : So, we can do that using a multitude of commands using the nc(netcat) command which is used for arbitrary TCP and UDP connections and listens. 
		
#nc localhost 30000  

then write the previous password and we get the level password.
 		
Password for Bandit15: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

---
* Level15 - level16: 

For this level we have to submit the previous password to the port 30001 on localhost using SSL encryption.

Solution : We will have to use openssl(tool to generate private keys) and s_client(can establish a transparent connection to a remote server).
	
#openssl s_client -connect localhost:30001 And submit the password.
	
Password for bandit16 : JQttfApK4SeyHwDlI9SXGR50qclOAil1

---
* Level16 - level17: 

In this level the credentials can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. So, first we have to check which port is open and there is only one server that will give the next credentials.

Solution: We will have to use nmap to check open ports. 
	
#nmap localhost -p 31000-32000 

So, we could find that there are 5 open ports and we will have to find which port is the one that will give the next credentials.

Then, we will have to find which port is the one that can give us the credentials.
	
#nmap localhost -A -p 31046,31518,31691,31790,31960
	
From the output we can see that ‘31790/tcp open  ssl/unknown’ is type ssl/unknown. So, we will have to use this port.

#ncat -ssl localhost 31790 

then, submit the previous password. 
And it gives us a PRIVATE KEY with the password for bandit17. 

Next step is to exit from the bandit and create a text file using touch key command, then open the file using nano key command and copy paste the private key.

Then ssh -i key bandit17@bandit.labs.overthewire.org -p 2220  

to login to bandit17

Password for bandit17: VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e 
 
“I got this password by using the previous knowledge from bandit14 (by using this command cat /etc/bandit_pass/bandit17). 

Note that we can only use this command inside itself a level to retrieve password.

---
* Level17- level18: 

For this level we are supposed to find the password for the next level from two files in the homedirectory: passwords.new and passwords.old. 

Solution : #diff passwords.new passwords.old
  
“this command gives us two passwords”. So, like it's said, the password for the next level is the first one.
	
Password for level18: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

---
* Level18 - level19: 

The password for the next level is stored in a file readme, but it’s said that someone has modified .bashrc to log out the users.

So, I found that when I try to login to bandit18, we are given “Byebye” as said in the previous level. 

Solution : #ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh  

 “Here, the -t flag is used to force pseudo-terminal allocation. -t options force tty allocation, even if ssh has no local tty”

Password for level19: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

---
* Level19 - level20: 

Here, to gain access to the next level we should use the setuid binary and execute without arguments. And it’s said that the password can be found at the usual pace(/etc/bandit_pass).

Solution : #./bandit20-do cat /etc/bandit_pass/bandit20 

Password for bandit20 : VxCazJaVykI6W36BkBU0mJTCM8rR95XT

---
* Level20 - level21: 

There is a setuid binary that does the following: it makes a connection to localhost on the port that I specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21). 

Solution : In this one I have to have two terminals both logged in to bandit20. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21). 

In one of the terminal I run this command:

#"cat /etc/bandit_pass/bandit20 | nc -l localhost 1234" 

 “This starts a listening server (-l) on port 1234 on the localhost”

In the other terminal I run this command:
	
#./suconnect 1234

Then, when the password is matched we receive the next level password.

Password for bandit21: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
