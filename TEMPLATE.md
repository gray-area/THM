# Advent of Cyber

[link to room](https://tryhackme.com/room/25daysofchristmas)

## Day 1 : Inventory Management 
#### 1.	What is the name of the cookie used for authentication?
	
	Go to the <machine IP:3000> and register yourself then refresh the page
	Press CTRL + SHIFT + I to access the Developer Consoloe
	Go to Applications tab and click on Cookies 

	auth<redacted>

#### 2.	If you decode the cookie, what is the value of the fixed part of the cookie?
	
	Access the cookie and decode the value which is encoded in base64(%3D is '=')
	Your username is the first part and second part will be same for everybody

	v4er9<redacted>

#### 3. After accessing his account, what did the user 'mcinventory' request?
	
	user = mcinventory
	we know the second part of cookie
	encode 'mcinventoryv4er9111!ss' into base64(you can search online for tools)
	bWNpbnZlbnRvcnl2NGVyOWxsMSFzcw%3D%3D
	copy and paste it into the value and press enter and refresh

	fire<redacted>

##  Day 2 : Arctic Forum 
#### 1.	What is the path of the hidden page?

	Recommended tool is DirSearch but we will use gobuster
	we will use the the recommended wordlist
	run 'gobuster -u http://<machine IP>:3000 -w /path/to/wordlist'

	/Sys<redacted>

#### 2.	What is the password you found?
	
	goto http://<machine IP>:3000/sysadmin
	check the page source
	"Admin Portal Created by Arctic Digital Design - check out github repo"
	google it 


    username: admin
    password: <redacted>word
    
    
    
    
    ## Day 13 : Accumulate

#### 1. A web server is running on the target. What is the hidden directory which the website lives on?
	nmap -sC -sV -Pn -oN nmap_day13.txt machine-ip
```bash
gobuster dir -u http://10.10.237.165/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 35
```
```
===============================================================
Gobuster v3.0.1
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@_FireFart_)
===============================================================
[+] Url:            http://10.10.237.165/
[+] Threads:        35
[+] Wordlist:       /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Status codes:   200,204,301,302,307,401,403
[+] User Agent:     gobuster/3.0.1
[+] Timeout:        10s
===============================================================
2020/06/21 03:36:27 Starting gobuster
===============================================================
/????? (Status: 301)
Progress: 12292 / 220561 (5.57%)^C
[!] Keyboard interrupt detected, terminating.
===============================================================
2020/06/21 03:38:01 Finished
===============================================================
```

> /r????

#### 2. Gain initial access and read the contents of user.txt
	After visiting the directory we found a username `wade` and a blog
```
Contents of blog:
I can’t believe the movie based on my favorite book of all time is going to come out in a few days! Maybe it’s because my name is so similar to the main character, but I honestly feel a deep connection to the main character Wade. I keep mistyping the name of his avatar whenever I log in but I think I’ll eventually get it down. Either way, I’m really excited to see this movie! 
```
After checking the comments of of the post i was able to get the password of the user
After logging in you will see the user flag on desktop

> THM{HACK_??????????}


#### 3. [Optional] Elevate privileges and read the content of root.txt

We will also see a executable named hhupd.exe on the desktop lets research on it
After searching i was able to get the vulnerabilty that will escalate our privileges to root/Administrator

[Github link to exploit we will use](https://github.com/jas502n/CVE-2019-1388)

After successful exploitataion, you will get a command prompt with Administrator privileges

```
Microsoft Windows [Version 10.0.14393]
(c) 2016 Microsoft Corporation. All rights reserved.

C:\Windows\System32>powershell -ep bypass
Windows PowerShell
Copyright (C) 2016 Microsoft Corporation. All rights reserved.

PS C:\Users> cd .\Administrator
PS C:\Users\Administrator> cd .\Desktop
PS C:\Users\Administrator\Desktop> ls

    Directory: C:\Users\Administrator\Desktop


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/23/2020  10:34 AM             31 root.txt


PS C:\Users\Administrator\Desktop> type root.txt
THM{COIN????????????????????}
PS C:\Users\Administrator\Desktop>
```

## Day 14 : Unknown Storage

#### 1. What is the name of the file you found?

You can use check the bucket by simply browsing

```bash
firefox http://advent-bucket-one.s3.amazonaws.com/
```
```
Contents of webpage:
<ListBucketResult>
<Name>advent-bucket-one</Name>
<Prefix/>
<Marker/>
<MaxKeys>1000</MaxKeys>
<IsTruncated>false</IsTruncated>
<Contents>
<Key>employee??????.txt</Key>
<LastModified>2019-12-14T15:53:25.000Z</LastModified>
<ETag>"e8d2d18588378e0ee0b27fa1b125ad58"</ETag>
<Size>7</Size>
<StorageClass>STANDARD</StorageClass>
</Contents>
</ListBucketResult>
```
> employee_??????


#### 2. What is in the file?

We can also simply check the whats inside the file by browsing to it
```bash
firefox http://advent-bucket-one.s3.amazonaws.com/employee_??????
```

> mc?????


## Day 16 :File Confusion

![day 16 script](https://github.com/strange07/tryhackme/blob/master/Advent%20of%20Cyber/day16.png)

For this task you have to create a python script to automate the task
I have already created the [script](https://github.com/strange07/tryhackme/blob/master/Advent%20of%20Cyber/day16-script.py) but i encourage you to make it yourself but if you stuck than you can get the guidance from here

#### 1. How many files did you extract(excluding all the .zip files)?

> ?0

#### 2. How many files contain Version: 1.1 in their metadata?

> ?

#### 3. Which file contains the password?

> ????.txt
