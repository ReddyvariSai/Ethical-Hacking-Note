# How Do Attackers Identify The target’s Subdomains During Footprinting?

Footprinting is a critical phase in the early stages of a penetration test or a cyber attack, during which attackers gather publicly available information about a target to map out its network infrastructure, systems, and potential vulnerabilities. One of the key components of this process is identifying a target’s subdomains, which are often overlooked by both security teams and organisations. Identifying subdomains can reveal hidden assets, services, and entry points into a network, providing attackers with valuable information for further exploitation.

In this article, we will explore how attackers identify subdomains during footprinting, the techniques they use, the tools involved, and how organisations can protect themselves against such reconnaissance efforts.

### What Are Subdomains, and Why Are They Important in Footprinting?

Before diving into the methods used to identify subdomains, it is essential to understand what they are and why they are important in the context of footprinting.

A subdomain is a domain that is part of a larger domain, often used to organize different sections or services of a website or network. Consider, in the domain example.com, the subdomain blog.example.com could represent a blog section of the website, while ftp.example.com might refer to an FTP server. Subdomains are often used for:

* Hosting different services like mail servers, FTP servers, web applications, etc.
* Isolating specific environments, such as staging, testing, or development environments.
* Providing access to internal tools or systems.

From a security standpoint, subdomains can present significant risks. They are often overlooked in terms of security or are not as tightly monitored as the main domain, creating potential attack surfaces. Consider, an attacker may discover a forgotten subdomain that points to a vulnerable test server or a misconfigured service, opening the door for further exploitation.

## Techniques Used by Attackers to Identify Subdomains

Attackers use a variety of techniques to identify subdomains during footprinting. These techniques involve leveraging publicly available data and network reconnaissance tools to search for subdomains associated with the target domain. The goal is to locate subdomains that may expose hidden assets, misconfigurations, or weak points in the target’s infrastructure. Below are the most common methods attackers employ to identify subdomains.

-----

## 1. DNS Zone Transfer

A DNS zone transfer is a process by which a DNS server shares its entire database of domain name records with another DNS server. If a target’s DNS server is misconfigured or vulnerable, attackers can request a zone transfer and obtain a full list of the domain’s subdomains.

A zone transfer typically involves querying the target’s nameserver using a special DNS command to retrieve all DNS records associated with a domain, including A records (address records) and NS records (name server records) for subdomains. This can be highly useful in footprinting as it reveals not only subdomains but also their corresponding IP addresses.

While zone transfers are a powerful tool for attackers, most organisations today configure their DNS servers to prevent this type of information leakage. Nevertheless, attackers may still attempt to carry out zone transfer requests to gather subdomain data.

### How Zone Transfers Are Conducted:

* Attackers identify the target’s nameserver using a WHOIS lookup or DNS query.
* Using tools like dig or nslookup, they send a request for a zone transfer to the target’s nameserver.
* If the nameserver is misconfigured and allows zone transfers, the attacker gains a full list of the subdomains.

## 2. Subdomain Brute Forcing

Brute forcing is a technique used by attackers to systematically guess subdomains by trying a large list of possible names. Attackers typically use a dictionary of common subdomain names combined with the target domain name to generate a list of potential subdomains. Consider, common subdomains include www, mail, ftp, test, dev, etc.

The brute-forcing process involves attempting to resolve the subdomain names to IP addresses using DNS queries. If the subdomain exists, it will return an IP address, revealing its existence.

### Tools Used for Subdomain Brute Forcing:

* DNSmap: A tool designed to perform brute-force subdomain enumeration.
* Sublist3r: A popular tool that combines brute forcing with other techniques to identify subdomains.
* Fierce: A reconnaissance tool that can be used for DNS enumeration and brute-forcing.

Brute-forcing can be time-consuming and resource-intensive, but it is effective for uncovering less visible subdomains that may not be indexed by search engines or available in public DNS records.

## 3. Using Search Engines (Google Dorking)

Search engines like Google can be powerful allies in identifying subdomains during footprinting. Google dorking refers to using advanced search operators to uncover information that is indexed by search engines but may not be easily found by casual browsing.

Attackers can use specific search queries to uncover subdomains of a target domain. Consider, a search query like site:example.com -www might reveal a list of indexed subdomains for example.com. Google indexes a vast amount of publicly available data, and subdomains often appear in indexed content, web pages, and even configuration files that have been exposed to the internet.

#### Google Dorking Techniques for Finding Subdomains:

* site:example.com -www: Excludes the main domain to show indexed subdomains.
* inurl:example.com: Searches for subdomains within URLs indexed by Google.
* intitle:"index of" example.com: Searches for directory listings or exposed files that may reveal subdomains.

This technique is particularly effective for discovering subdomains that are not publicly advertised but are still exposed on the internet.

## 4. Public DNS Records and WHOIS Lookups

Publicly available DNS records and WHOIS information can often provide valuable clues about the existence of subdomains. When an attacker performs a WHOIS lookup, they can often obtain details about the target domain, including the name servers and other relevant infrastructure.

By performing a WHOIS lookup for a domain, attackers can uncover additional subdomains indirectly. For instance, subdomains that are hosted on third-party platforms may show up in DNS records or WHOIS information, and the attacker can use these clues to investigate further.

Similarly, DNS records like NS (Name Server) records, A (Address) records, and MX (Mail Exchange) records can reveal the presence of subdomains associated with specific services, such as mail servers or load balancers.

## 5. Third-Party Services and Passive DNS

Several online services and tools provide valuable subdomain enumeration data by aggregating DNS records from a variety of sources. These services often maintain historical records of subdomain resolutions, which can be beneficial for identifying subdomains that may have been deleted or changed over time.

Consider, PassiveDNS services collect DNS queries and store them for later analysis. These services can be used to identify subdomains that may no longer be actively used but could still pose a security risk due to the presence of sensitive data or legacy systems.

#### Popular Subdomain Enumeration Services:

* VirusTotal: Provides DNS data, including subdomains, as part of its domain analysis.
* SecurityTrails: A service that aggregates historical DNS data and subdomain information.
* Shodan: A search engine for internet-connected devices, which also indexes subdomains.

## 6. Third-Party Tools for Subdomain Enumeration

In addition to manual techniques, attackers can use a variety of automated tools to enumerate subdomains more efficiently. These tools often combine multiple techniques, such as DNS querying, brute forcing, and data aggregation from external sources, to provide a comprehensive list of subdomains.

#### Some Popular Subdomain Enumeration Tools Include:
* Amass: A comprehensive subdomain enumeration tool that uses brute-forcing, search engines, and passive DNS sources.
* Subfinder: An easy-to-use subdomain discovery tool that scans various public sources.
* Sublist3r: A Python tool that uses brute-forcing and data from public sources to identify subdomains.

---------
# How to Protect Against Subdomain Enumeration

## 1. Limit DNS Information Disclosure

Ensure that DNS zone transfers are disabled, and restrict access to authoritative DNS servers to prevent attackers from performing successful zone transfers.

## 2. Use DNSSEC (Domain Name System Security Extensions)

DNSSEC helps prevent attackers from tampering with DNS responses and reduces the risk of DNS cache poisoning and other attacks.

## 3. Monitor Subdomains Regularly

Regularly audit and monitor subdomains to ensure they are not exposed or misconfigured. This includes ensuring that subdomains are secured with proper authentication, encryption, and access controls.

## 4. Hide Sensitive Subdomains

Sensitive subdomains, such as staging environments or development servers, should be kept off the public internet and hidden from DNS records when possible. If exposed, these subdomains should be properly secured with strong authentication and encryption.

## 5. Use Web Application Firewalls (WAFs)

A WAF can help detect and block malicious traffic, including reconnaissance attempts such as subdomain enumeration. WAFs can identify suspicious requests and protect against known attack patterns.

## 6. Remove Unused Subdomains

Inactive or forgotten subdomains should be removed entirely to eliminate potential attack vectors. If a subdomain is no longer in use, it should not remain listed in DNS records.

# Conclusion

Identifying subdomains is a critical aspect of footprinting and can provide attackers with valuable information about a target’s network infrastructure, security posture, and potential vulnerabilities. Attackers use a combination of DNS queries, brute-forcing, search engines, WHOIS lookups, and other techniques to discover subdomains that may otherwise be hidden.

For organisations, understanding how subdomains are discovered and taking steps to secure them is essential in reducing the risk of a successful attack. By implementing strong DNS configurations, monitoring subdomains, and applying good security practices, organisations can better defend against footprinting attempts and safeguard their online assets.

