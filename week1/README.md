# Week 1 Progress Report

## 📅 Day 1. Linux Basics
✅ Learned essential Linux commands:  
- Navigating directories (ls, cd, pwd)  
- Working with files (cat, nano, cp, mv, rm)  
- Created a test environment: folder cyber_test and file notes.txt  

📌 Result:  
- Able to create, edit, copy, and delete files.  
- First report file notes.txt with text: *“First step in cybersecurity”*.  

---

## 📅 Day 2. Permissions & Search
✅ Learned Linux file permissions (chmod):  
- Managing access for user (u), group (g), others (o)  
- Adding/removing read, write, and execute rights  
- Practical task: restricted access to secret.txt  

✅ Learned search commands:  
- find — locate files by name or extension  
- grep — search text inside files  

📌 Result:  
- Created secret.txt and changed its permissions.  
- Practiced file and string search.  
- Saved a report in day2.txt.  

---

## 🎯 Skills after 2 Days
- Confident navigation in Linux terminal.  
- File and directory management.

---


## 🎯 Skills after 3 Days

## 🔹 Topic  
DNS analysis and traffic inspection with Kali Linux  

---

## 🔹 What we did today  

1. Port Scanning  
   - Used nmap to check open ports.  
   - Found only port 53 (DNS) open.  
   - Service detected: dnsmasq (Android hotspot).  

2. DNS Functionality Check  
   - Queried domain names with dig.  
   - Received multiple A-records (IPv4 addresses).  
   - Learned about TTL (time to live) in DNS answers.  

3. WHOIS / IP Info  
   - Tested whois and ipinfo.io.  
   - Understood difference between local IP (10.x.x.x) and public IP.  
   - Learned about bogon addresses (private ranges).  

4. Traffic Capture & Analysis  
   - Captured DNS packets with tcpdump.  
   - Opened them in Wireshark.  
   - Applied filters (dns, dns.qry.name == "google.com", ip.src == <local-ip>).  
   - Observed queries and responses in detail.  

---

## 🔹 Commands used today  

### 🔸 Port scanning
Bash

sudo nmap -sS -sV -O -Pn 10.66.211.217
### 🔸 DNS queries
Bash

dig @10.66.211.217 example.com A
dig @10.66.211.217 +short google.com
dig @10.66.211.217 CHAOS TXT version.bind +short
### 🔸 WHOIS / IP info
Bash

whois 23.192.228.80
curl ipinfo.io/23.192.228.80
curl ifconfig.me
### 🔸 Traffic capture
Bash

sudo tcpdump -i wlan0 port 53 -n
sudo tcpdump -i wlan0 port 53 -w dns_lab.pcap
wireshark dns_lab.pcap &
### 🔸 Wireshark filters
dns
dns.qry.name == "google.com"
dns.flags.response == 1   # only responses
dns.flags.response == 0   # only queries
ip.src == 10.66.211.106
ip.dst == 10.66.211.217
---

## 🔹 Key Learnings  
- Port 53 is essential for DNS communication.  
- DNS mainly uses UDP, TCP is used as fallback.  
- Local vs Public IP addresses.  
- Wireshark filters help to focus on exact traffic.  
- First steps in traffic analysis completed successfully.  

---

## 🔹 Next Steps  
- Explore HTTP/HTTPS analysis (ports 80/443).  
- Capture and analyze HTTP headers.  
- Practice writing more detailed audit-style reports
- Understanding and modifying file permissions.  
- Searching files and text with find and grep.  
