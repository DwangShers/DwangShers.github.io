---
Title: SWS101 Journal6
categories: [CTF, CTFJournal6]
tags: [CTF]
---

### Topic : Corridor

---

![alt text](</image/CTF/Corridor/cor0.png>)

#### Can you escape the Corridor?

Reconnaissance 

![alt text](</image/CTF/Corridor/nmap.png>)

There is only 1 port open that http. Let’s check the webpage for this machine.

![alt text](</image/CTF/Corridor/website.png>)

### Task 1: Escape the Corridor

#### What is the flag?

There are many doors which we can open by clicking on the door. When I opened the door the url in the md5 hash, so I copied all the hash from the source code and pasted it in the crack station.

![alt text](</image/CTF/Corridor/cor1.png>)

![alt text](</image/CTF/Corridor/cor2.png>)

Notice that the result is numbered from 1-13, so it is sure that i came from door zero. So I generated the hash for zero.

![alt text](</image/CTF/Corridor/cor3.png>)

Taking this md5 hash, I paste it in the url. 

![alt text](</image/CTF/Corridor/cor4.png>)

This url takes me to the flag.

Answer: flag{2477ef02448ad9156661ac40a6b8862e}

### Conclusion
When I visit the webpage of that machine there are many doors but none of them take me back to where I come from. I notice that when I open each door I get the hash, when I crack those hash the result is the number. I observed the number pattern and found that the door number that I come from is 0, so I hash the number 0 and paste it in the url then get the flag.

