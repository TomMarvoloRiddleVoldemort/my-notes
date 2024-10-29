### Command to find subdomain 
```
ffuf -w /usr/share/wordlists/dirb/big.txt -H "HOST:FUZZ.board.htb" -u "http://board.htb"  
```

**Here's a summary of the filtering techniques you can use with `ffuf` to find the relevant subdomains:** 

**1. Filter by Status Codes**: Focus on responses with specific HTTP status codes like `200`, `301`, `302`, which often indicate valid or interesting pages. 

	   `-mc 200,301,302` 

**2. Filter by Content Length**: Exclude responses based on content length. For example, ignore responses with a length of `0`. 

	   -fs 0 

**3. Filter by Word Count**: Exclude responses based on the number of words. For example, ignore responses with a word count of `0`. 

	   -fw 0 

**4. Match Strings**: Search for specific strings within the response body to find relevant results. 

	   -mr "specific-string" 

**5. Save Output for Analysis**: Save the results to a file for further manual analysis or to process with additional tools. 

	   -o results.json -of json 

**6. To add specific extension**: Save the results to a file for further manual analysis or to process with additional tools. 

	   -e .txt,.md,.php

### Command to Find Directories
```
ffuf -c -w /usr/share/wordlists/dirbuster/directory-list-1.0.txt -u http://itrc.ssg.htb/?page=FUZZ –b "PHPSESSID=d9d5c700f355b51c27d8026f8f3d8027" -recursion -fs 3976
```

|                |                                                                                                                                                                                                                                                  |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **-c**         | This flag tells ffuf to colorize the output, making it easier to read.                                                                                                                                                                           |
| **-w**         | Wordlist                                                                                                                                                                                                                                         |
| **-u**         | Url for FUZZ  \| eg.-u [http://itrc.ssg.htb/?page=FUZZ](http://itrc.ssg.htb/?page=FUZZ)                                                                                                                                                          |
| **-b**         | Cookie data `"NAME1=VALUE1; NAME2=VALUE2"` for copy as curl functionality. Eg. -b "PHPSESSID=d9d5c700f355b51c27d8026f8f3d8027"                                                                                                                   |
| **-recursion** | Scan recursively. Only FUZZ keyword is supported, and URL (-u) has to end in it. (default: false) Enables recursion, which means ffuf will follow discovered links and directories within the initial results to find more directories or files. |
| **-fs 3976**   | Ignore responses with a length of `3976`.                                                                                                                                                                                                        |

### Command to find Subdomain
```
ffuf -c -w SecLists/Discovery/DNS/n0kovo_subdomains.txt -u "http://ssg.htb" -H "HOST: FUZZ.ssg.htb" -t 200 -mc all -fc 302 
```

|             |                                                                                                                            |
| ----------- | -------------------------------------------------------------------------------------------------------------------------- |
| **-t 200**  | Sets the number of concurrent threads to 200. This speeds up the scanning process by making multiple requests in parallel. |
| **-mc all** | Specifies the status codes to match. all means that ffuf will include all status codes in its output.                      |
| **-fc 302** | Excludes responses with status code 302 from the results                                                                   |

---
