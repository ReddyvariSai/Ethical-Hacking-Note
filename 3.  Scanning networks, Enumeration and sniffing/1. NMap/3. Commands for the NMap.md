
# Commands for the NMap for the beginners:


Nmap provides a vast array of commands and flags used for network discovery, security auditing, and vulnerability detection. It is a command-line tool that scans IP addresses and ports to identify running applications and devices.

## Host Discovery and Range Commands
* `nmap <target>`: This is the default scan, which identifies the state of the top 1,000 most common TCP ports.
* `-sn`: Performs a ping scan, which identifies if hosts are up without performing a port scan.
* `-Pn`: Treats all hosts as online and skips host discovery, which is useful if a firewall blocks standard ping probes.
* `-sL`: A list scan that simply lists targets without sending packets to them.
* `-iL <file>`: Loads a list of targets from a text file instead of typing them manually.
* `--exclude <IP>`: Used to skip specific IP addresses during a network-wide scan.
* `192.168.1.1-100`: Scans a specific range of IP addresses.

## Port Specification Commands

* `-p-`: Scans all 65,535 ports on a system rather than just the default top 1,000.
* `-p <port>`: Scans a specific port (e.g., -p 80) or a list of ports separated by commas.
* `-F`: Enables Fast Mode, which limits the scan to the top 100 most popular ports.
* `--exclude-ports <ports>`: Tells Nmap to ignore specific ports during the scanning process.

## Scanning Techniques

* `-sS`: The TCP SYN scan (also called a stealth or half-open scan); it does not complete the three-way handshake, making it harder for firewalls to log.
* `-sT`: A TCP Connect scan, which completes the full three-way handshake and is more easily detected by defensive systems.
* `-sU`: Used for UDP scanning, which is essential for discovering services like DNS or DHCP but is significantly slower than TCP scans.
* `-sN`, `-sF`, `-sX`: Null, FIN, and Xmas scans, which manipulate TCP headers to bypass certain firewall rules.
* `-sA`: An ACK scan used to map out firewall rules and determine if ports are filtered or unfiltered.

## Service, OS, and Aggressive Detection

* `-sV`: Enables version detection, identifying specifically what software and version are running on an open port.
* `-O`: Enables Operating System fingerprinting to identify the target's OS.
* `-A`: An Aggressive scan that combines OS detection, version detection, default script scanning, and traceroute into one command.

## Evasion and Timing Control

* `-f`: Fragments packets, splitting them into smaller pieces to help bypass Intrusion Detection Systems (IDS).
* `-D <decoy1,decoy2>`: Performs a decoy scan, making it appear to the target that multiple different IP addresses are scanning them simultaneously to hide your real identity.
* `-T<0-5>`: Sets a timing template; -T0 is the slowest (stealthiest), while -T5 is the fastest (most aggressive and noisy).
* `--scan-delay <time>`: Adds a specific delay between probes to avoid triggering rate-limiting or firewall alerts.

## Nmap Scripting Engine (NSE)

* `-sC`: Runs the default set of scripts for discovery and basic vulnerability testing.
* `--script=<name>`: Runs a specific script or category of scripts (e.g., --script=vuln for vulnerability checks or --script=brute for brute force attacks).

## Output Formatting

* `-oN <file>`: Saves the output in normal text format.
* `-oX <file>`: Saves the output in XML format, which is useful for importing into other tools.
* `-oG <file>`: Saves the results in a grepable format for easy searching with command-line tools.
* `-oA <basename>`: Saves the results in all three major formats (normal, XML, and grepable) at once.
* `-v or -vv`: Increases verbosity, providing more detailed information about the scan's progress in real-time.


#### To find the ip add 

> ifconfig

#### To scane the NMap

 nmap < target ip add >

Example:

``` 
nmap 192.168.133.1
```

<img width="1597" height="641" alt="Screenshot 2026-01-06 122447" src="https://github.com/user-attachments/assets/3ccffc68-2c16-4f7a-ab67-0db0d79a2039" />

<img width="1602" height="915" alt="Screenshot 2026-01-06 122944" src="https://github.com/user-attachments/assets/8f8ea0cb-9356-4b79-95a9-1efcff47c6c0" />

#### To Scane TCP Ports && UDP Ports

> If you scane all tcp ports on the IPadd
` sudo nmap -sT -p- < IP add >` 

>  If you scane all udp ports on the IPadd
` sudo nmap -sU -p- < IP add >`

> If you scane all tcp && udp ports on the IPadd
` sudo nmap -sT -sU -p- < IP add >` 

```
Note :- If you Scane ` sudo nmap -sT -sU -p- < IP add >` firewall detect your ip ( hacker IP ) and band it.

So don`t use this command.
````
<img width="1140" height="868" alt="Screenshot 2026-01-06 193756" src="https://github.com/user-attachments/assets/29bde180-1bfd-47a2-9152-4dfcf0d1a7d2" />

<img width="1145" height="871" alt="Screenshot 2026-01-06 193843" src="https://github.com/user-attachments/assets/03583da8-8cdb-4f80-bc1d-cc48fe0f669c" />

> If you scane all tcp in port 21 ( FTP ) open in the target host.
` sudo nmap -sT -p21 < IP add >` 

<img width="1141" height="868" alt="image" src="https://github.com/user-attachments/assets/9b210115-d245-49f9-912f-bcf0663bb53e" />

> To discover the host addres ( yours addres ).

```
└─$ sudo netdiscover -i eth0                                 
````

<img width="1037" height="488" alt="Screenshot 2026-01-06 205846" src="https://github.com/user-attachments/assets/1493ad29-7dba-4a2e-915f-8d6f26e4bdfb" />

> If you Know the how many ports are open in my host( you )/target addres.

```
nmap -sn < ip add >
```

<img width="1137" height="914" alt="image" src="https://github.com/user-attachments/assets/9d48b1fd-f805-4e29-93eb-d7f4c7cf3290" />


> If you know the how may conntions to your networking ( router ) for limeted data you want.

```
nmap -sn < ip add >-100
```
Example:
```
nmap -sn 192.168.1.1-100
```
























