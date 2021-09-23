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
