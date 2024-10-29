a> \-m → **message** you want to hide
>
> \-p →**password**
>
> original.txt → **original file**
>
> cipher.txt → **target file**

#### ~={green}Windows=~
---
##### ~={yellow}Hide  Text=~
```bash
snow.exe -C -p 1234 -m "Secret Message" original.txt cipher.txt
```
##### ~={yellow}Unhide the hidden text=~
```bash
snow.exe -C -p 1234 cipher.txt
```

#### ~={green}Linux=~
---
##### ~={yellow}Hide  Text=~
```bash
./snow -C -m "Secret Text Goes Here!" -p "magic" original.txt cipher.txt 
```
##### ~={yellow}Unhide the hidden text=~
```bash
./snow -C -p "magic" cipher.txt
```

