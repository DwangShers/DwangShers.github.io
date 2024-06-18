---
Title: SWS101 Journal8
categories: [CTF, CTFJournal8]
tags: [CTF]
---

### Topic : Simple CTF

---

![alt text](</image/CTF/Simple ctf/sim0.png>)

Beginner level ctf

Reconnaissance

![alt text](</image/CTF/Simple ctf/nmap.png>)

There are 3 ports open that are ssh, http and ftp. Let’s check the webpage for this machine.

![alt text](</image/CTF/Simple ctf/website.png>)

It’s just a normal Apache2 page.

### Task 1: Simple CTF

#### How many services are running under port 1000?

There are 2 ports that are running under 1000. They are 21 and 80.

Answer: 2

#### What is running on the higher port?

ssh service is running on port 2222 which is higher than 1000.

Answer: ssh

#### What's the CVE you're using against the application?

For that let’s find the hidden directories.

![alt text](</image/CTF/Simple ctf/sim1.png>)

There is /simple directory.

![alt text](</image/CTF/Simple ctf/sim2.png>)

There is this link, which is below the left corner.

![alt text](</image/CTF/Simple ctf/sim3.png>)

Here we can see this is a default page for something called “CMS Made Simple” and if we look in the bottom corner we can see it is version 2.2.8.

Let’s see if there is anything online about this particular version by simply going to Google and
searching “CMS Made Simple 2.2.8 exploit”

![alt text](</image/CTF/Simple ctf/sim4.png>)

We can use this cve for exploitation.

Answer: CVE-2019-9053

#### To what kind of vulnerability is the application vulnerable?

We can see that it is vulnerable to SQL injection.

Answer: sqli

#### What's the password?

This is the python script I am going to use in exploiting.

![alt text](</image/CTF/Simple ctf/sim5.png>)

I save this python script inside the simple.py

![alt text](</image/CTF/Simple ctf/sim6.png>)

![alt text](</image/CTF/Simple ctf/sim7.png>)

With the following command we can now begin the exploit.

![alt text](</image/CTF/Simple ctf/sim8.png>)

Answer: secret

#### Where can you login with the details obtained?

It's for sure, we can login to ssh once we got the username and the password.

Answer: ssh

#### What's the user flag?

Answer: G00d j0b, keep up!

#### Is there any other user in the home directory? What's its name?|

Answer: sunbath

#### What can you leverage to spawn a privileged shell?

Answer: vim

#### What's the root flag?

Answer: W3ll d0n3. You made it!

### Conclusion

Using CVE we can easily exploit the server.
