---
Title: SWS101 Journal5
categories: [CTF, CTFJournal5]
tags: [CTF]
---

### Topic : Wgel CTF

---

![alt text](</image/CTF/Wgel CTF/gel0.png>)

Can you exfiltrate the root flag?

Reconnaissance

![alt text](</image/CTF/Wgel CTF/nmap.png>)

There are 2 ports open that are ssh and http. Let’s check the webpage for this machine.

![alt text](</image/CTF/Wgel CTF/website.png>)

It’s just a normal Apache2 page. When I looked at the source code, I got a comment line where the developer had mentioned the name of another user. In the image I have highlighted the commented line.

![alt text](</image/CTF/Wgel CTF/gel1.png>)

### Task 1: Wgel CTF

#### User flag

Let’s begin by finding the directories. Using feroxbuster I got all the hidden directories.

![alt text](</image/CTF/Wgel CTF/gel2.png>)

![alt text](</image/CTF/Wgel CTF/gel3.png>)

If I change the directory to /sitemap, I get the following page.

![alt text](</image/CTF/Wgel CTF/gel4.png>)

There is nothing on this page. So I go further to /.ssh. There I found the id_rsa file

![alt text](</image/CTF/Wgel CTF/gel5.png>)

Inside the id_rsa there is a private key.

![alt text](</image/CTF/Wgel CTF/gel6.png>)

Then I downloaded the file. .

![alt text](</image/CTF/Wgel CTF/gel7.png>)

To use the ‘id_rsa’ file, it’s permission must be set to 600.

![alt text](</image/CTF/Wgel CTF/gel8.png>)

Now let's go with ssh login using this id_rsa.

![alt text](</image/CTF/Wgel CTF/gel9.png>)

Once logged in, inside the Documents directory I found the user_flag.txt.

Answer: 057c67131c3d5e42dd5cd3075b198ff6

#### Root flag

Answer: b1b968b37519ad1daa6408188649263d

### Conclusion

Many of the information can be found in source code where the developer forgot to clear. By solving this room I knew that a private id_rsa key can be used as the password when logging to ssh service.
