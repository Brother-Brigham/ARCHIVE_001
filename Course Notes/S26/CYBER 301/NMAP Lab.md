## Part 1: Basic Scanning

The most fundamental Nmap command identifies which ports are open and responding.

**Task:** Run a simple scan against the target.

`nmap scanme.nmap.org`

**Discussion Questions:**

1. How many ports are listed as "open"?
Four ports are open.

PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
9929/tcp  open  nping-echo
31337/tcp open  Elite

2. What is the IP address resolved for the hostname?
45.33.32.156

---

## Part 2: Service and Version Detection

Knowing a port is open is helpful, but knowing _what_ is running on that port is critical for vulnerability assessment.

**Task:** Use the `-sV` flag to probe open ports to determine service/version info.

`nmap -sV scanme.nmap.org`

**What to look for:**

- In the **VERSION** column, you’ll see specific software names (e.g., Apache, OpenSSH).
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
80/tcp    open  http       Apache httpd 2.4.7 ((Ubuntu))
9929/tcp  open  nping-echo Nping echo
31337/tcp open  tcpwrapped
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

- Compare these results to Part 1. Does the extra detail help identify potential attack vectors?
Yes, it does. Knowing that certain ports are using OpenSSH/Apache/a specific OS/etc. provides additional information that can be used to identify attack vectors.

---

## Part 3: Aggressive Scanning (The "All-in-One")

For a quick, comprehensive look, Nmap provides an "aggressive" mode. This enables OS detection, version detection, script scanning, and traceroute.

**Task:** Run the aggressive scan using the `-A` flag.

`nmap -A scanme.nmap.org`

**Caution:** This scan is "loud" and easily detected by Intrusion Detection Systems (IDS).

┌──(kali㉿kali)-[~]
└─$ nmap -A scanme.nmap.org
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-06 13:10 -0400
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.035s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 996 closed tcp ports (reset)
PORT      STATE SERVICE    VERSION
22/tcp    open  ssh        OpenSSH 6.6.1p1 Ubuntu 2ubuntu2.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   1024 ac:00:a0:1a:82:ff:cc:55:99:dc:67:2b:34:97:6b:75 (DSA)
|   2048 20:3d:2d:44:62:2a:b0:5a:9d:b5:b3:05:14:c2:a6:b2 (RSA)
|   256 96:02:bb:5e:57:54:1c:4e:45:2f:56:4c:4a:24:b2:57 (ECDSA)
|_  256 33:fa:91:0f:e0:e1:7b:1f:6d:05:a2:b0:f1:54:41:56 (ED25519)
80/tcp    open  http       Apache httpd 2.4.7 ((Ubuntu))
|_http-favicon: Nmap Project
|_http-title: Go ahead and ScanMe!
|_http-server-header: Apache/2.4.7 (Ubuntu)
9929/tcp  open  nping-echo Nping echo
31337/tcp open  tcpwrapped
Aggressive OS guesses: Linux 4.19 - 5.15 (98%), Linux 4.15 (96%), IPFire 2.27 (Linux 5.15 - 6.1) (93%), Linux 5.4 (92%), Linux 5.0 - 5.14 (91%), MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3) (91%), Linux 3.11 - 4.9 (90%), Linux 3.2 - 3.8 (90%), Synology DiskStation Manager 5.1 (90%), Linux 4.15 - 5.19 (89%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 11 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 3389/tcp)
HOP RTT      ADDRESS
1   0.14 ms  192.168.122.1
2   8.04 ms  10.15.0.2
3   2.09 ms  10.33.190.70
4   6.32 ms  10.15.155.4
5   ...
6   7.10 ms  74.118.18.16
7   ...
8   30.75 ms 10.255.1.152
9   25.47 ms 10.255.1.111
10  22.88 ms 10.255.0.140
11  19.97 ms scanme.nmap.org (45.33.32.156)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 24.12 seconds

---

## Part 4: Operating System Fingerprinting

Nmap can often guess the underlying operating system by analyzing how the target's TCP/IP stack responds to specific packets.

**Task:** Attempt to identify the OS. (Note: This usually requires administrative/root privileges).

`sudo nmap -O scanme.nmap.org`

┌──(kali㉿kali)-[~]
└─$ sudo nmap -O scanme.nmap.org
[sudo] password for kali: 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-05-06 13:13 -0400
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.037s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 996 closed tcp ports (reset)
PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
9929/tcp  open  nping-echo
31337/tcp open  Elite
Aggressive OS guesses: Linux 4.19 - 5.15 (98%), Linux 4.15 (96%), IPFire 2.27 (Linux 5.15 - 6.1) (93%), Linux 5.4 (92%), Linux 5.0 - 5.14 (91%), MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3) (91%), Linux 3.11 - 4.9 (90%), Linux 3.2 - 3.8 (90%), Synology DiskStation Manager 5.1 (90%), Linux 4.15 - 5.19 (89%)
No exact OS matches for host (test conditions non-ideal).
Network Distance: 24 hops

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 4.51 seconds