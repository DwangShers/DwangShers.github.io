---
Title: SWS101 Journal1
categories: [CTF, CTFJournal1]
tags: [CTF]
---

### Topic : Bounty Hacker

---
![alt text](</image/CTF/Bounty Hacker/bounty0.jpg>)
You talked a big game about being the most elite hacker in the solar system. Prove it and claim your right to the status of Elite Bounty Hacker!

Reconnaissance.
![alt text](</image/CTF/Bounty Hacker/bounty1.png>)

There are 3 ports open. Let’s check the webpage of the machine.

![alt text](</image/CTF/Bounty Hacker/Website.png>)

To solve this room there is nothing in port 80.


### Task 1: Living up to the title.

#### Who wrote the task list?
Hint: Have you visited FTP?

Login to ftp server with anonymous username.
![alt text](</image/CTF/Bounty Hacker/bounty2.png>)

Once we are successfully logged in then check for the directory. We found two txt file and checked who wrote task.txt, it was lin.
 
Answer: lin

#### What service can you bruteforce with the text file found?
Hint: What is on port 22?
Hint says it is port 22 and we know that in port 22 the service is ssh.

Answer: SSH

#### What is the users password?
Hint: Hydra may be able to help.
![alt text](</image/CTF/Bounty Hacker/bounty3.png>)

To get the  lin’s password, I bruteforce for the password using hydra and locks.txt as password list and found a password.

Answer: RedDr4gonSynd1cat3

#### User.txt
![alt text](</image/CTF/Bounty Hacker/bounty4.png>)
Now we have both the username and password. We can login to ssh.

In the ssh server there is a user.txt and I captured the flag.

Answer: THM{CR1M3_SyNd1C4T3}

#### Root.txt
To get the root.txt flag I need to get root access. For that lets check what the user’s privileges are. Command is sudo -l.
![alt text](</image/CTF/Bounty Hacker/bounty5.png>)

I found that we can gain root access on the /bin/tar command.For that run the following command.
![alt text](</image/CTF/Bounty Hacker/bounty6.png>)

Answer: THM{80UN7Y_h4cK3r}

### Conclusion
This room is vulnerable to ftp server. For ftp server we can always login by giving an anonymous name and get the information about that machine which can be username, password or any other kinds of information. 
