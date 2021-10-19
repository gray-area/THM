## Intro

I will openly admit, after the first section I struggled with this, as encoding and encryption are not my strongsuit - yet. Because of this, i would use hints from walkthroughs to get me on the right track. Dont be discouraged if you dont know the methods. This is used to learn things that you dont know and expose you to different techniques. 


### /diningRoom/

```SG93IGFib3V0IHRoZSAvdGVhUm9vbS8```

```klfvg ks r wimgnd biz mpuiui ulg fiemok tqod. Xii jvmc tbkg ks tempgf tyi_hvgct_jljinf_kvc```

```there is a shield key inside the dining room. The html page is called the_great_shield_key```

```^--/sapphire.html```

```blue_jewel{e1d457e96cac640f863ec7bc475d48aa}```

### /teaRoom/

```lock_pick{037b35e2ff90916a9abf99129c8e1837}```

### /artRoom/

```<p>Look like a map</p>

<p>Location:<br>
/diningRoom/<br> X
/teaRoom/<br> X
/artRoom/<br> X
/barRoom/<br>
/diningRoom2F/<br>
/tigerStatusRoom/<br>
/galleryRoom/<br>
/studyRoom/<br>
/armorRoom/<br>
/attic/
```

### /barRoom/

```NV2XG2LDL5ZWQZLFOR5TGNRSMQ3TEZDFMFTDMNLGGVRGIYZWGNSGCZLDMU3GCMLGGY3TMZL5```

```moonlight somata```

```music_sheet{362d72deaf65f5bdc63daece6a1f676e}```

```rebecca```

/barRoomHidden/

```gold_emblem{58a8c41a9d08b8a4e38d02a4d7ff4843}```

### /diningRoom2F/

```Lbh trg gur oyhr trz ol chfuvat gur fgnghf gb gur ybjre sybbe. Gur trz vf ba gur qvavatEbbz svefg sybbe. Ivfvg fnccuver.ugzy```

```You get the blue gem by pushing the status to the lower floor. The gem is on the diningRoom first floor. Visit sapphire.html```

### /tigerStatusRoom/

```
crest 1:
S0pXRkVVS0pKQkxIVVdTWUpFM0VTUlk9
Hint 1: Crest 1 has been encoded twice
Hint 2: Crest 1 contanis 14 letters
Note: You need to collect all 4 crests, combine and decode to reavel another path
The combination should be crest 1 + crest 2 + crest 3 + crest 4. Also, the combination is a type of encoded base and you need to decode it
```

### /galleryRoom/

```
crest 2:
GVFWK5KHK5WTGTCILE4DKY3DNN4GQQRTM5AVCTKE
Hint 1: Crest 2 has been encoded twice
Hint 2: Crest 2 contanis 18 letters
Note: You need to collect all 4 crests, combine and decode to reavel another path
The combination should be crest 1 + crest 2 + crest 3 + crest 4. Also, the combination is a type of encoded base and you need to decode it
```


### /armorRoom/

```
crest 3:
MDAxMTAxMTAgMDAxMTAwMTEgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTAwMTEgMDAxMDAwMDAgMDAxMTAxMDAgMDExMDAxMDAgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTAxMTAgMDAxMDAwMDAgMDAxMTAxMDAgMDAxMTEwMDEgMDAxMDAwMDAgMDAxMTAxMDAgMDAxMTEwMDAgMDAxMDAwMDAgMDAxMTAxMTAgMDExMDAwMTEgMDAxMDAwMDAgMDAxMTAxMTEgMDAxMTAxMTAgMDAxMDAwMDAgMDAxMTAxMTAgMDAxMTAxMDAgMDAxMDAwMDAgMDAxMTAxMDEgMDAxMTAxMTAgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTEwMDEgMDAxMDAwMDAgMDAxMTAxMTAgMDExMDAwMDEgMDAxMDAwMDAgMDAxMTAxMDEgMDAxMTEwMDEgMDAxMDAwMDAgMDAxMTAxMDEgMDAxMTAxMTEgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTAxMDEgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTAwMDAgMDAxMDAwMDAgMDAxMTAxMDEgMDAxMTEwMDAgMDAxMDAwMDAgMDAxMTAwMTEgMDAxMTAwMTAgMDAxMDAwMDAgMDAxMTAxMTAgMDAxMTEwMDA=
Hint 1: Crest 3 has been encoded three times
Hint 2: Crest 3 contanis 19 letters
Note: You need to collect all 4 crests, combine and decode to reavel another path
The combination should be crest 1 + crest 2 + crest 3 + crest 4. Also, the combination is a type of encoded base and you need to decode it
```

### /attic/

```
crest 4:
gSUERauVpvKzRpyPpuYz66JDmRTbJubaoArM6CAQsnVwte6zF9J4GGYyun3k5qM9ma4s
Hint 1: Crest 2 has been encoded twice
Hint 2: Crest 2 contanis 17 characters
Note: You need to collect all 4 crests, combine and decode to reavel another path
The combination should be crest 1 + crest 2 + crest 3 + crest 4. Also, the combination is a type of encoded base and you need to decode it
```
ftp to machine
```
ftp> dir
200 PORT command successful. Consider using PASV.
150 Here comes the directory listing.
-rw-r--r--    1 0        0            7994 Sep 19  2019 001-key.jpg
-rw-r--r--    1 0        0            2210 Sep 19  2019 002-key.jpg
-rw-r--r--    1 0        0            2146 Sep 19  2019 003-key.jpg
-rw-r--r--    1 0        0             121 Sep 19  2019 helmet_key.txt.gpg
-rw-r--r--    1 0        0             170 Sep 20  2019 important.txt
```
I then ran exiftool on the images

image 1 yielded nothing
image 2 = 5fYmVfZGVzdHJveV9
image 3 yielded nothing

Installed steghide

ran the following:

```
steghide extract -sf 001-key.jpg -xf 001-key.data
Enter passphrase: 
wrote extracted data to "001-key.data".
Kali :: THM/Biohazard » cat 001-key.data 
cGxhbnQ0Ml9jYW
```
I then checked key 3 as follows:

```
KaliLab :: THM/Biohazard » binwalk -e 003-key.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
1930          0x78A           Zip archive data, at least v2.0 to extract, uncompressed size: 14, name: key-003.txt
2124          0x84C           End of Zip archive, footer length: 22

Kali :: THM/Biohazard » cd _003-key.jpg.extracted 
Kali :: Biohazard/_003-key.jpg.extracted » ls -la
total 16
drwxr-xr-x 2 nameless nameless 4096 Oct 19 13:26 .
drwxr-xr-x 3 nameless nameless 4096 Oct 19 13:26 ..
-rw-r--r-- 1 nameless nameless  216 Oct 19 13:26 78A.zip
-rw-r--r-- 1 nameless nameless   14 Sep 19  2019 key-003.txt
KaliLab :: Biohazard/_003-key.jpg.extracted » cat key-003.txt 
3aXRoX3Zqb2x0
```


Combine all three keys and use CyberChef to go "From Base64"

```
cGxhbnQ0Ml9jYW5fYmVfZGVzdHJveV93aXRoX3Zqb2x0
```

```
plant42_can_be_destroy_with_vjolt
```

### /hiddenCloset/

```
wpbwbxr wpkzg pltwnhro, txrks_xfqsxrd_bvv_fy_rvmexa_ajk
```

```
SSH password: T_virus_rules
```

I then SSH into the box:

Nothing really to look at, so I moved to weaskers directory and opened the file.

```
Weaker: Finally, you are here, Jill.
Jill: Weasker! stop it, You are destroying the  mankind.
Weasker: Destroying the mankind? How about creating a 'new' mankind. A world, only the strong can survive.
Jill: This is insane.
Weasker: Let me show you the ultimate lifeform, the Tyrant.

(Tyrant jump out and kill Weasker instantly)
(Jill able to stun the tyrant will a few powerful magnum round)

Alarm: Warning! warning! Self-detruct sequence has been activated. All personal, please evacuate immediately. (Repeat)
Jill: Poor bastard

```


I then when back to root, because i was missing something. 

I did an ``` ls -la``` and found that there was a directory called ```.jailcell```

After going in there, I opened the file:

```
Jill: Chris, is that you?
Chris: Jill, you finally come. I was locked in the Jail cell for a while. It seem that weasker is behind all this.
Jil, What? Weasker? He is the traitor?
Chris: Yes, Jill. Unfortunately, he play us like a damn fiddle.
Jill: Let's get out of here first, I have contact brad for helicopter support.
Chris: Thanks Jill, here, take this MO Disk 2 with you. It look like the key to decipher something.
Jill: Alright, I will deal with him later.
Chris: see ya.

MO disk 2: albert 
```
I then took the encoded text from earlier, and used the MO disk 2 code:

```
wpbwbxr wpkzg pltwnhro, txrks_xfqsxrd_bvv_fy_rvmexa_ajk
```

```
weasker login password, stars_members_are_my_guinea_pig
```

I then logged into SSH with the weasker credentials.

After logging in, I was able to "cat" the text by using the following:

```
sudo -u root cat /root/root.txt
```

This gave me the root flag.
