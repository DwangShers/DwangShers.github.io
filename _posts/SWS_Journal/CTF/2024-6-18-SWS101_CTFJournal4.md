---
Title: SWS101 Journal4
categories: [CTF, CTFJournal4]
tags: [CTF]
---

### Topic : Dig Dug

---
![alt text](</image/CTF/Dig Dug/dig0.png>)

Turns out this machine is a DNS server - it's time to get your shovels out!

Reconnaissance 

![alt text](</image/CTF/Dig Dug/nmap.png>)

There is only 1 port open that is ssh. 


### Task 1: Dig Dug
Retrieve the flag from the DNS server!

![alt text](</image/CTF/Dig Dug/dig1.png>)

To solve this room we are given a link where we can find something useful. As I checked those links, in passive reconnaissance I found the command line to deal with the domain.

![alt text](</image/CTF/Dig Dug/dig2.png>)

Now let’s give this command in the terminal.

![alt text](</image/CTF/Dig Dug/dig3.png>)

#### With that one command we got the flag.

Answer: flag{0767ccd06e79853318f25aeb08ff83e2}

### Conclusion
The machine we are attacking is a DNS server. A DNS server simply assigns a domain, like google.com, to an IP. In our case the domain name is givemetheflag.com. 
