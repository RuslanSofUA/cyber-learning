#Finding my phone's IP
During practice with **nmap** and **tcpdump**,
I found that my Android phone was using the IP **10.66.211.217**
At first, the MAC address did not match Samsung,
dut after analyzing ARP and DNS packets,
I confirmed this IP delongs to my device.
---
#Steps
1. Scanned the subnet with `nmap -sn
10.66.211.0/24`.

2. Captured packets using `tcpdump`.
 
3. Saw new DNS requests from `10.66.211.217.
 
4. Verified is was my phone.
 
---
 
#Conclusion
 
- Phone may randomize MAC address for privacy.
- IP addresses can change after reconnecting.
- Comdining **nmap** and **tcpdump** helps identify devices.
