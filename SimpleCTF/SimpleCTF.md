# SimpleCTF Room

[Link to room](https://tryhackme.com/room/easyctf)

## Scanning
 ```
 sudo nmap -sC -sV -O 10.10.x.x -vv 
```
## Enumeration
```
  gobuster dir -u http://10.10.x.x -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 40
```
