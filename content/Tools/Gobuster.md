Typical output for GoBuster. 
Status code **200** means you can access it and 
**403** is forbidden, and 
**301** is a redirection (you can usually still access it) . 
The **400**'s and **500**'s are generally client/server errors, and 
anything in the **300**'s means some kind of redirect. 
There you have it, the basic functionality of GoBuster. 

### Command to find Directory
```
gobuster dir -u http://10.10.11.14 -w /usr/share/wordlists/dirbuster/directory-list-2.23-medium.txt -b 301 
```

### Command to find Subdomain (DNS subdomain enumeration)
```
gobuster dns -d solarlab.htb -w /usr/share/wordlists/amass/subdomains-top1mil-20000.txt -t 20  
```

|           |                                                                                                                           |
| --------- | ------------------------------------------------------------------------------------------------------------------------- |
| **-t 20** | Sets the number of concurrent threads to 20. This speeds up the scanning process by making multiple requests in parallel. |
