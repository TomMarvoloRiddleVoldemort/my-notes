```
[recon-ng][default] > workspaces create example_name
[recon-ng][example_name] >
```

The command `recon-ng -w example_name` opens or returns directly to that workspace.

### Recon-ng modules
---
Modules are grouped together under various categories and can be found searching on `marketplace`

`- discovery   
`- exploitation   `
`- import   `
`- recon   `
`- reporting`

Each of the above have sub categories as shown in the table below. Use `marketplace search` for a full table providing information on version, status (installed or not-installed), date updated, dependencies or require keys.



```
recon-ng][default] >marketplace search ssl
[*] Searching module index for 'ssl'...

  +----------------------------------------------------------------------------+
  |             Path            | Version |     Status    |  Updated   | D | K |
  +----------------------------------------------------------------------------+
  | recon/domains-hosts/ssl_san | 1.0     | not installed | 2019-06-24 |   |   |
  | recon/hosts-hosts/ssltools  | 1.0     | not installed | 2019-06-24 |   |   |
  | recon/ports-hosts/ssl_scan  | 1.1     | not installed | 2021-08-24 |   |   |
  +----------------------------------------------------------------------------+

  D = Has dependencies. See info for details.
  K = Requires keys. See info for details.

[recon-ng][default] >
```



```
[recon-ng][default] > marketplace info ssltools 

  +---------------------------------------------------------------------------------------+
  | path          | recon/hosts-hosts/ssltools                                                                                                                                                                                 |
  | name          | SSLTools.com Host Name Lookups                                                                                                                                                                             |
  | author        | Tim Maletic (borrowing from the ssl_san module by Zach Graces)                                                                                                                                             |
  | version       | 1.0                                                                                                                                                                                                        |
  | last_updated  | 2019-06-24                                                                                                                                                                                                 |
  | description   | Uses the ssltools.com site to obtain host names from a site's SSL certificate metadata to update the 'hosts' table.  Security issues with the certificate trust are pushed to the 'vulnerabilities' table. |
  | required_keys | []                                                                                                                                                                                                         |
  | dependencies  | []                                                                                                                                                                                                         |
  | files         | []                                                                                                                                                                                                         |
  | status        | not installed                                                                                                                                                                                              |
  +------------------------------------------------------------------------------------+

[recon-ng][default] >
```



#### Install module
---
To install this module use the following:

```
[recon-ng][default] > marketplace install hackertarget
[*] Module installed: recon/domains-hosts/hackertarget
[*] Reloading modules...
[recon-ng][default] >
```



#### Load module
---
```
[recon-ng][default] > modules load hackertarget
[recon-ng][default][hackertarget] > 
```

#### Module Help
---
The help command from within a loaded module has different options to the global 'help'.  
When you are ready to explore more modules use 'back'.

```
[recon-ng][default][hackertarget] > help
```

#### Set source
---
Using `show options`, brings a table showing the source `current value` set at `default`.

```
[recon-ng][default][hackertarget] > show options

  Name    Current Value  Required  Description
  ------  -------------  --------  -----------
  SOURCE  `default`        yes       source of input (see 'show info' for details)
```
Now, set the source to the name of the domain investigating. This example uses tesla.com as they have a published big bounty.

Use command `options set SOURCE tesla.com`

```
[recon-ng][default][hackertarget] > options set SOURCE tesla.com
SOURCE => tesla.com
```
Use command `info`. This shows `current value` has changed to tesla.com

```
[recon-ng][default][hackertarget] > info

Options:
  Name    Current Value  Required  Description
  ------  -------------  --------  -----------
  SOURCE  **tesla.com**      yes       source of input (see 'info' for details)

Source Options:
  default      SELECT DISTINCT domain FROM domains WHERE domain IS NOT NULL
  string       string representing a single input
  path         path to a file containing a list of inputs
  query sql    database query returning one column of inputs
```

Use `input` to see

```
[recon-ng][default][hackertarget] > input

  +---------------+
  | Module Inputs |
  +---------------+
  | tesla.com     |
  +---------------+
```
#### Run the module
---
Type `run` to execute the module.
```
[recon-ng][default][hackertarget] > run
```