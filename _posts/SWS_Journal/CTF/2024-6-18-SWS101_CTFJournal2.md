---
Title: SWS101 Journal2
categories: [CTF, CTFJournal2]
tags: [CTF]
---

### Topic : "TryHack3M: Bricks Heist"

---

### Introduction

Hello everyone. This is my first CTF journal and I will show you all how to go through.

In this journal I will be solving the Bricks Heist which is one of the CTF(Capture the Flag) challenges.

To do the rooms, as we know we will have to connect the vpn or use the AttackBox.

### Enumeration

![alt text](/image/ip_adding.png)
As mentioned in there, once we start the machine, we need to add the IP in our /etc/hosts file.

![alt text](</image/Pasted image 6.png>)

So, first lets scan this website using <u>wpscan</u>.

![alt text](</image/Pasted image 7.png>)

Now, we need to disable checks for tls certificates

![alt text](</image/Pasted image 8.png>)

Now, it should scan. So, lets try.

![alt text](</image/Pasted image 9.png>)

![alt text](</image/Pasted image 10.png>)

After scanning, we can find a theme: bricks with version:1.9.5.
Lets try searching for it in the google.

![alt text](</image/Pasted image 11.png>)

So, the github link has the exploit avialable. Copy the raw code or you can download the raw code and paste it in a file in our machine.

![alt text](</image/Pasted image 12.png>)

To make the file executable use this code.

![alt text](</image/Pasted image 13.png>)

To run the exploit, we need to install some requirements.

```command
pip3 install alive-progress
```

Now, lets run the exploit.

```python3
python3 shell.py -u https://bricks.thm
```

After running this code, we can see that we have an initial access on the system as apache user.
But this shell is not a stable shell, as we can't cd into the directory.

650c844110baced87e1606453b9