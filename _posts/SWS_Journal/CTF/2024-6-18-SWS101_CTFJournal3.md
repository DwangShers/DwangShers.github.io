---
Title: SWS101 Journal2
categories: [CTF, CTFJournal2]
tags: [CTF]
---

### Topic : Basic Pentesting

---
![alt text](</image/CTF/Basic Pentesting/pentest0.png>)

This is a machine that allows you to practice web app hacking and privilege escalation.

Reconnaissance 

![alt text](</image/CTF/Basic Pentesting/nmap.png>)

There are 6 ports open. Let's check http server.

![alt text](</image/CTF/Basic Pentesting/website.png>)

The website is under maintenance.

### Task 1: Web App Testing and Privilege Escalation 
#### What is the name of the hidden directory on the web server(enter name without /)?

I used gobuster to find the hidden directory. I have used this word list:

https://github.com/danielmiessler/SecLists/blob/master/Discovery/Web-Content/directory-list-2.3-small.txt

![alt text](</image/CTF/Basic Pentesting/pentest1.png>)

I found that there is a directory as /development.

Answer: development

#### What is the username?
When I check the /development directory, there are 2 txt files(dev.txt and j.txt).

This is the content of dev.txt

![alt text](</image/CTF/Basic Pentesting/pentest2.png>)

This is the content of j.txt.

![alt text](</image/CTF/Basic Pentesting/pentest3.png>)

This 2 file does not contain the full name of the user.

{enum4linux 10.10.24.174 -U} 

Run this code to find the username. 

![alt text](</image/CTF/Basic Pentesting/pentest4.png>)

So the user k is Kay and j is Jan.

Answer: jan


#### What is the password?
If you are not able to locate the rockyou.txt file, then browse it for your laptop and you will find it in the internet. 

![alt text](</image/CTF/Basic Pentesting/pentest5.png>)

Hydra is the powerful tool to brute force. Using hydra I got the user’s password.

Answer: armando

#### What service do you use to access the server(answer in abbreviation in all caps)?
Now I have the username and password, so it is easy to login to ssh. Therefore I will use the ssh service to access the server. 

Answer: SSH

#### What is the name of the other user you found(all lower case)?
Earlier we found two usernames Jan and kay.

Answer: kay

#### What is the final password you obtain?
Once we login to kay, i will get the passphrase. Next use john the ripper to brute force the passphrase then we will get the final password.

Answer: heresareallystrongpasswordthatfollowsthepasswordpolicy$$

### Conclusion
This room gives an opportunity to learn the real scenario of pentesting. From this room, I learned brute forcing, hash cracking and service enumeration.
