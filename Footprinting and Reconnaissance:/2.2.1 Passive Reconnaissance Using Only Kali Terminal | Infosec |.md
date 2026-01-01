# Passive Reconnaissance Using Only Kali Terminal | Infosec |

<img width="1100" height="619" alt="image" src="https://github.com/user-attachments/assets/a3ebe5c9-624e-4e6d-bac6-67d2a44afcf3" />

In this blog, we are going to look at Passive Recon

# Commands:-
## Tool: host

We can use the host command to find the IP address of the target domain or the domain name of the particular IP address.


<img width="531" height="201" alt="image" src="https://github.com/user-attachments/assets/59d2ec50-adb6-40d2-a9b8-a075d5563cc4" />


The result shows medium.com has two IP addresses each for IPV4 and IPV6. When there are two IP addresses like that, it indicates that the website is using some kind of reverse proxy or firewall. Also, we can see they are using a google mail server.

-----

# Firewall Detection

## Tool: wafw00f

This tool sends malicious HTTP requests and analyzes the response using some algorithm to identify the WAF being used.

<img width="738" height="408" alt="image" src="https://github.com/user-attachments/assets/06da51ad-f9b9-446b-a3b2-4eedb57deddc" />

This confirms that the website is behind a firewall.

```
Cloudfare is a Content Distribution System whose job is to deliver content to users safely and quickly around the globe through cloud computing.
```

----

# Finding Technologies
## Tool: WhatWeb

This tool can help us to find the technologies that a particular website is using which can help a pentester to find technologies that are old or whose version is vulnerable to some kind of exploit.

<img width="1042" height="123" alt="image" src="https://github.com/user-attachments/assets/89a54bd0-6b65-4b61-8d74-ca53804e7d5e" />

From the screenshot above, we can see the technologies this website is using which is PHP along with its version and the web server that is Nginx and other stuff.

----

# DNS Enumeration
## Tool: dnsrecon

This tool gives information about the DNS servers and records.

It checks all NS Records for Zone Transfers.

Enumerate General DNS Records for a given Domain (MX, SOA, NS, A, AAAA, SPF, and TXT).

Perform common SRV Record Enumeration.

Brute Force subdomain and resolve records for a domain.

Check a DNS Server Cached records for A, AAAA, and CNAME Records provided with a list of host records in a text file to check.

Enumerate Common mDNS records and Subdomains using Google.

<img width="524" height="698" alt="image" src="https://github.com/user-attachments/assets/8cd59d39-7786-44c3-908c-061192ef79a0" />

From the result above, we can see the firewall IP and different types of DNS servers.

```
Terms and their meaning:-
-------------------------------------------------------------------------
SOA - Start of Authority --

Stores information about a domain or zone as the email address of the  administrator.
when the domain was last updated.
how long the  server should wait between refreshes.

NS - Name Server --

The NS records specify the servers which are providing DNS services for that domain name.

MX - Mail Exchange --

Directs all the emails for that particular domain to a mail server.

SRV - Service Record --

This records contains hostnames with a port number to identify certain services on the domain.
```

<img width="832" height="125" alt="image" src="https://github.com/user-attachments/assets/52cc8532-cab0-4892-b0c6-6cd8d5f63797" />

----

# Zone Transfer

A common insecure configuration with DNS is to allow anyone to perform a zone transfer. Zone transfer basically means copying the information in the zone file from one server(primary) to another server(secondary). Admins use it to replicate DNS databases so if in case the primary server goes down, the secondary server will have the zone file and can handle DNS requests.

But sometimes it is misconfigured so anyone can request the zone file, and thereby receive the whole list of subdomains.

```
Command: dnsrecon -d example.com -a
```

-----

# Domain Brute Force

Dnsrecon can also perform domain bruteforce and will try to resolve the A, AAA, and CNAME records against the domain using a given wordlist. We just have to provide the domain name, a wordlist, and -t is used to provide the type of enumeration to be performed, in this case, bruteforce.
```
Command: dnsrecon -d example.com -D wordlist.txt -t btr
```
<img width="1060" height="614" alt="image" src="https://github.com/user-attachments/assets/28c8d73d-302d-4f8f-9600-d94ea31b2ed4" />

Dnsrecon can do more like cache poisoning, It happens when the DNS server has a specific DNS record cached through which an attacker can gather information about the name servers and DNS records which can be done with -t snoop command along with the domain name






