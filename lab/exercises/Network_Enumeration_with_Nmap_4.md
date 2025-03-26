# Network Enumeration with Nmap  

    - Page 4
    - Host and Port Scanning

# Host and Port Scanning


## Find all TCP ports on your target. Submit the total number of found TCP ports as the answer. 

I do a scan on the default port.

```
└──╼ $nmap 10.129.219.49
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-03-26 17:41 +08
Nmap scan report for 10.129.219.49
Host is up (0.53s latency).
Not shown: 993 closed tcp ports (conn-refused)
PORT      STATE SERVICE
22/tcp    open  ssh
80/tcp    open  http
110/tcp   open  pop3
139/tcp   open  netbios-ssn
143/tcp   open  imap
445/tcp   open  microsoft-ds
31337/tcp open  Elite

Nmap done: 1 IP address (1 host up) scanned in 40.71 seconds
```

## Enumerate the hostname of your target and submit it as the answer. (case-sensitive) 

I do a fast scan with all the default options and script enabled. 
  - `-F`
  - `-A`

```
└──╼ $sudo nmap -A -F 10.129.219.49
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-03-26 17:57 +08
Nmap scan report for 10.129.219.49
Host is up (0.50s latency).
Not shown: 94 closed tcp ports (reset)
PORT    STATE SERVICE     VERSION
22/tcp  open  ssh         OpenSSH 7.6p1 Ubuntu 4ubuntu0.7 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 71:c1:89:90:7f:fd:4f:60:e0:54:f3:85:e6:35:6c:2b (RSA)
|   256 e1:8e:53:18:42:af:2a:de:c0:12:1e:2e:54:06:4f:70 (ECDSA)
|_  256 1a:cc:ac:d4:94:5c:d6:1d:71:e7:39:de:14:27:3c:3c (ED25519)
80/tcp  open  http        Apache httpd 2.4.29 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.29 (Ubuntu)
110/tcp open  pop3        Dovecot pop3d
|_pop3-capabilities: CAPA UIDL AUTH-RESP-CODE SASL TOP RESP-CODES PIPELINING
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
143/tcp open  imap        Dovecot imapd (Ubuntu)
|_imap-capabilities: listed OK IDLE have IMAP4rev1 LOGINDISABLEDA0001 more LITERAL+ capabilities Pre-login ENABLE ID post-login LOGIN-REFERRALS SASL-IR
445/tcp open  netbios-ssn Samba smbd 4.7.6-Ubuntu (workgroup: WORKGROUP)
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.94SVN%E=4%D=3/26%OT=22%CT=7%CU=39997%PV=Y%DS=2%DC=T%G=Y%TM=67E3
OS:CFB8%P=x86_64-pc-linux-gnu)SEQ(SP=109%GCD=1%ISR=10D%TI=Z%CI=Z%II=I%TS=A)
OS:SEQ(SP=109%GCD=1%ISR=10D%TI=Z%CI=Z%II=I%TS=B)OPS(O1=M53AST11NW7%O2=M53AS
OS:T11NW7%O3=M53ANNT11NW7%O4=M53AST11NW7%O5=M53AST11NW7%O6=M53AST11)WIN(W1=
OS:FE88%W2=FE88%W3=FE88%W4=FE88%W5=FE88%W6=FE88)ECN(R=Y%DF=Y%T=40%W=FAF0%O=
OS:M53ANNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=N)
OS:T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S
OS:+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=
OS:Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G
OS:%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=S)

Network Distance: 2 hops
Service Info: Host: NIX-NMAP-DEFAULT; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
|_nbstat: NetBIOS name: NIX-NMAP-DEFAUL, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
|_clock-skew: mean: -19m26s, deviation: 34m37s, median: 32s
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.7.6-Ubuntu)
|   Computer name: nix-nmap-default
|   NetBIOS computer name: NIX-NMAP-DEFAULT\x00
|   Domain name: \x00
|   FQDN: nix-nmap-default
|_  System time: 2025-03-26T10:58:24+01:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-time: 
|   date: 2025-03-26T09:58:24
|_  start_date: N/A

TRACEROUTE (using port 21/tcp)
HOP RTT       ADDRESS
1   533.98 ms 10.10.16.1
2   245.12 ms 10.129.219.49

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 72.05 seconds
```



