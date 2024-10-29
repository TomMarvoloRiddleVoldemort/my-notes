
### Command to extract *public key* from *private key*
```
ssh-keygen -y -f ca-itrc
```

|                |                                                                                                                                                                                                                                                 |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ssh-keygen** | - This is the command-line tool for generating, managing, and converting SSH keys.                                                                                                                                                              |
| **-y**         | - This option is used to extract the public key from a private key file.                                                                                                                                                                        |
| **-f ca-itrc** | - This option specifies the file containing the private key. <br>    <br>- In this case, the file is named ca-itrc. <br>    <br>- The -f option is used to provide the filename of the private key from which the public key will be extracted. |


### Command to create new private rsa key
```
ssh-keygen -t rsa -b 2048 -f axurakey
```

|                 |                                                                                                                                                                                                                                                                                |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **-t rsa**      | - This option specifies the type of key to create rsa                                                                                                                                                                                                                          |
| **-b 2048**     | - This option specifies the number of bits in the key. <br>    <br>- 2048 bits is a common key length for RSA keys, providing a good balance between security and performance.  <br>    <br>- You could also use 4096 bits for even stronger security, but it might be slower. |
| **-f axurakey** | - This option specifies the file name to save the private key.  <br>    <br>- In this case, the private key will be saved as axurakey.  <br>    <br>- The corresponding public key will be saved a s `axurakey.pub.  <br>    <br>- Default (id_rsa and id_rsa.pub).            |

### Command to sign public key with valid private key.
```
ssh-keygen -s ca-itrc -I ca-itrc.pub -n zzinter axurakey.pub 
```

|                    |                                                                                                                                                                                                                                                                                            |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **-s ca-itrc**     | - This option specifies the path to the private key that is used to sign the public key.  <br>    <br>- In this case, ca-itrc is the private key of the Certificate Authority (CA) that will be used to sign the public key.                                                               |
| **-I ca-itrc.pub** | - This option specifies the key identity or certificate identifier. <br><br>- It’s a unique string that identifies the certificate.                                                                                                                                                        |
| **-n zzinter**     | - This option specifies the principals or users for which the certificate is valid.  <br>    <br>- zzinter would be a username or a set of usernames that are allowed to use the certificate.  <br>    <br>- It defines the scope or the set of users that can use the signed certificate. |
| **auxrakey.pub**   | - This is the public key file that you want to sign with the CA’s private key.  <br>    <br>- The result will be a signed certificate that includes the original public key and is validated by the CA’s private key.                                                                      |

### Command to get details about public key.
``` 
ssh-keygen -Lf axurakey-cert.pub 
```

|                          |                                                                                                                                                                                   |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **-L**                   | - This option displays the fingerprint and other details about the public key.  <br>    <br>- Information such as valid principals, validity periods, and certificate extensions. |
| **-f axurakey-cert.pub** | - This specifies the file containing the public key (or certificate) to be examined.                                                                                              |

### Command to connect with ssh from public certificate and private key. 
```
ssh -o CertificateFile=axurakey-cert.pub -i axurakey zzinter@localhost 
```

|                                          |                                                                                                          |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **-o certificateFile=axurakey-cert.pub** | - This option specifies the path to a public key certificate file.                                       |
| **-i axurakey**                          | - This option specifies the path to the private key file that corresponds to the public key certificate. |
| **zzinter@localhost**                    | - This specifies the user and the hostname (or IP address) of the SSH server you are connecting to.      |
