
# 🦈 Wireshark or Tcpdump

## ~={green}Wireshark=~

```bash
wireshark -i eth1

# Filter by ip
ip.addr == 10.10.10.9

# Filter by dest ip
ip.dest == 10.10.10.15

# Filter by source ip
ip.src == 10.10.16.33

# Filter by tcp port
tcp.port == 25

# Filter by multiple tcp port
ip.addr == 10.10.0.4 or
ip.addr ==10.10.0.5

# Filter by ip addr and port
ip.addr == 10.10.14.22 and tcp.port == 8080

# Filter SYN flag
tcp.flags.syn == 1 and tcp.flags.ack ==0

# Broadcast filter
eth.dst == ff:ff:ff:ff:ff:ff

# other filters
ip.dst == 10.0.1.50 && frame.pkt_len > 400
ip.addr == 10.0.1.12 && icmp && frame.number > 15 && frame.number < 30
ip.src == 205.153.63.30 or ip.dst == 205.153.63.30

# Display all TCP resets
top.flags.rest == 1

# sets a filter for the HEX of 0x33 0x27 0x58 at any offset
udp contains 33:27:58

# Displays all http GET request
http.request

# Displays all TCP packets that contain the word "traffic"
tcp contains traffic

# Masks aut arp, icmp, dns, or other protocols and allows you to view traffic of your interest
!(arp or icmp or dns)

# Sets a filter for any TCP packet with 4000 as a source or destination port
tcp.port == 4000

# Displays only traffic in the LAN(192.1678.x.x), between workstations and servers - no internet
ip.src == 192.168.0.0/16  and
ip.dst == 192.168.0.0/16

# Filter by a protocol(eg. SIP) and filter out unwanted IPs
ip.src != xxx.xxx.xxx.xxx && ip.dst != xxx.xxx.xxx.xxx && sip

```

### ~={green}Filters Cheat Sheet=~

![[Pasted image 20241018162859.png]]

![[Pasted image 20241018162908.png]]
### ~={green}TShark=~

```bash
tshark -D
tshark -i eth1
tshark -r <FILE>.pcap
tshark -r <FILE>.pcap | wc -l

# First 100 packets
tshark -r <FILE>.pcap -c 100

# Protocl hierarchy statistics
tshark -r <FILE>.pcap -z io,phs -q

# HTTP traffic
tshark -r <FILE>.pcap -Y 'http' | more
tshark -r <FILE>.pcap -Y "ip.src==<SOURCE_IP> && ip.dst==<DEST_IP>"

# Only GET requests
tshark -r <FILE>.pcap -Y "http.request.method==GET"

# Packets with frame time, source IP and URL for all GET requests
tshark -r <FILE>.pcap -Y "http.request.method==GET" -Tfields -e frame.time -e ip.src -e http.request.full_uri

# Packets with a string
tshark -r <FILE>.pcap -Y "http contains password"

# Check destination IP
tshark -r <FILE>.pcap -Y "http.request.method==GET && http.host==<TARGET_URL>" -Tfields -e ip.dst

# Check session ID
tshark -r <FILE>.pcap -Y "ip contains amazon.in && ip.src==<IP>" -Tfields -e ip.src -e http.cookie

# Check OS/User Agent type
tshark -r <FILE>.pcap -Y "ip.src==<IP> && http" -Tfields -e http.user_agent

# WiFi traffic filter
tshark -r <FILE>.pcap -Y "wlan"

# Only deauthentication packets 
tshark -r <FILE>.pcap -Y "wlan.fc.type_subtype==0x000c"
# and devices
tshark -r <FILE>.pcap -Y "wlan.fc.type_subtype==0x000c" -Tfields -e wlan.ra

# Only WPA handshake packets
tshark -r <FILE>.pcap -Y "eapol"

# Onyl SSID/BSSID
tshark -r <FILE>.pcap -Y "wlan.fc.type_subtype==8" -Tfields -e wlan.ssid -e wlan.bssid

tshark -r <FILE>.pcap -Y "wlan.ssid==<SSID>" -Tfields -e wlan.bssid

# WiFi Channel
tshark -r <FILE>.pcap -Y "wlan.ssid==<SSID>" -Tfields -e wlan_radio.channel

# Vendor & model
tshark -r <FILE>.pcap -Y "wlan.ta==<DEVICE_MAC> && http" -Tfields -e http.user_agent
```

```bash
# ARP POISONING - arpspoof

## Forward IP packets
echo 1 > /proc/sys/net/ipv4/ip_forward
# arpspoof -i <interface> -t <target> -r <host>
arpspoof -i eth1 -t <TARGET_IP> -r <HOST_IP>
```

#### Others Notes

```bash
#To find DOS (SYN and ACK)
tcp.flags.syn == 1  , tcp.flags.syn == 1 and tcp.flags.ack == 0

#To find passwords
http.request.method == POST

#More reference
https://www.comparitech.com/net-admin/wireshark-cheat-sheet/

#To find DOS: look for Red and Black packets with around 1-2 simple packets in between and then pick any packet and check the Source and Destination IP with port(As per question)
#To find DOS (SYN and ACK) : tcp.flags.syn == 1  , tcp.flags.syn == 1 and tcp.flags.ack == 0
#To find passwords : http.request.method == POST
```


## ~={green}**Password sniffing using Wireshark**=~

**Attacker**

* `Stop capture`
* `File-\&gt;Save as`
* `Filter: http.request.method==POST`
* `RDP log in Target`
* `service`
* `start Remote Packet Capture Protocol v.0 (experimental)`
* `Log off Target`
* `Wireshark-\&gt;Capture options-\&gt;Manage Interface-\&gt;Remote Interfaces`
* `Add a remote host and its interface`
* `Fill info`
