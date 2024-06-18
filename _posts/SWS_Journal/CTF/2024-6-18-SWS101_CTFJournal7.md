---
Title: SWS101 Journal7
categories: [CTF, CTFJournal7]
tags: [CTF]
---

### Topic : CyberHeroes

---

![alt text](</image/CTF/CyberHeroes/cyb0.png>)

Want to be a part of the elite club of CyberHeroes? Prove your merit by finding a way to log in!

Reconnaissance 

![alt text](</image/CTF/CyberHeroes/nmap.png>)

There are 2 ports open that are ssh and  http. Let’s check the webpage for this machine.

![alt text](</image/CTF/CyberHeroes/website.png>)

We need to login to solve this room.

### Task 1: CyberHeroes
#### Q. Uncover the flag!

![alt text](</image/CTF/CyberHeroes/cyb1.png>)

To login we need username and password but we don't have it. So check source code to gain more information.

![alt text](</image/CTF/CyberHeroes/cyb2.png>)

There is a javascript code where username and reverse string is mentioned. Now taking that reverse string we can get the original password with the command line echo.

![alt text](/image/CTF/CyberHeroes/cyb3.png>)

So the password for user h3ck3rBoi is SuperSecret@12345

![alt text](</image/CTF/CyberHeroes/cyb4.png>)

By using that credentials we can successfully logged into the website and there we find the flag.

Answer: flag{edb0be532c540b1a150c3a7e85d2466e}

### Conclusion
Source code usually contains vulnerabilities, in this case also contains username and password but password is in reverse string. 
