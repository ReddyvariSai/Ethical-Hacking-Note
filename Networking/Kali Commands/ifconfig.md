# Ifconfig
Knowing your IP address is fundamental for network administration, troubleshooting, and various Linux system tasks. In this article, we will explore several methods to find your IP address in a Linux environment. Whether you are a seasoned Linux user or just getting started, understanding these methods will empower you to navigate and manage your network effectively.

## Why is this important?
### Network Configuration:
ifconfig allows users to configure network interfaces, including setting IP addresses, netmasks, and broadcast addresses.
###Network Troubleshooting:
It provides detailed information about network interfaces, which is essential for diagnosing connectivity issues, monitoring network traffic, and checking interface statuses.
### Interface Management:
Users can enable or disable network interfaces, which is crucial for managing network connections and controlling which interfaces are active.
### MAC Address Modification:
ifconfig enables users to change the MAC address of a network interface, which can be useful for security purposes or bypassing network restrictions.
### Temporary Network Changes:
It allows for temporary network configuration changes without editing configuration files, useful for testing and troubleshooting.

## How to Find Your IP Address in Linux Using `ifconfig Command
ifconfig (interface configuration) command is used to configure the kernel-resident network interfaces. It is used at the boot time to set up the interfaces as necessary. After that, it is usually used when needed during debugging or when you need system tuning.

Also, this command is used to assign the IP address and netmask to an interface or to enable or disable a given interface.

Syntax of `ifconfig`Command in Linux
```bash
ifconfig [interface] [options]
```
Where:

[interface] is the network interface you want to configure or display information for (e.g., eth0, wlan0).
[options] are various command-line options that can be used to modify the behavior of ifconfig.
Newer versions of some Linux distributions don't have ifconfig command pre-installed. So, in case, there is an error "ifconfig: command not found", Then execute the following command to install ifconfig.

## Installing net-tools in Linux
For Debian, Ubuntu, and related Linux distributions.
```bash

sudo apt-get install net-tools
```
For CentOS or RPM(RedHat Package Manager) based Linux
```bash
yum install net-tools
or

dnf install net-tools
```
This will install `ifconfig` along with some other networking commands like arp, route, ipmaddr.

Finding Your Ip Address in Linux Using `ifconfig` Command
To view information about all network interfaces on your Linux system, simply execute the following command:
```bash
ifconfig
```
<img width="481" height="344" alt="image" src="https://github.com/user-attachments/assets/db08ec4e-d950-446e-8406-be24ce7db693" />

This command will provide a comprehensive list of all network interfaces along with their respective IP addresses, MAC addresses, and other relevant details.

Options available in `ifconfig` Command in Linux
Here are the most commonly used option in ifconfig command in linux

## ifconfig Command Options

| Option | Description | Syntax |
|-------|------------|--------|
| `-a` | Display all interfaces, including those that are down | `ifconfig -a` |
| `-s` | Display a short list instead of full details | `ifconfig -s` |
| `-v` | Run the command in verbose mode | `ifconfig -v` |
| `up` | Activate the driver for the given interface | `ifconfig <interface> up` |
| `down` | Deactivate the driver for the given interface | `ifconfig <interface> down` |
| `add addr/prefixlen` | Add an IPv6 address to an interface | `ifconfig <interface> add <addr>/<prefixlen>` |
| `del addr/prefixlen` | Remove an IPv6 address from an interface | `ifconfig <interface> del <addr>/<prefixlen>` |
| `[-]arp` | Enable/disable ARP protocol on an interface | `ifconfig <interface> [-]arp` |
| `[-]promisc` | Enable/disable promiscuous mode | `ifconfig <interface> [-]promisc` |
| `[-]allmulti` | Enable/disable all-multicast mode | `ifconfig <interface> [-]allmulti` |
| `mtu N` | Set the Maximum Transmission Unit (MTU) | `ifconfig <interface> mtu <size>` |
| `--help` | Display help for the ifconfig command | `ifconfig --help` |


## What is Public and Private IP in Linux
In the realm of networking, both in Linux and other operating systems, IP addresses are categorized as either public or private. These designations are crucial for facilitating communication between devices on a network, whether it's the global internet or a local intranet. Let's delve into the distinctions between public and private IP addresses in Linux.

## 1) How to Find Your Public IP Addresses in Linux
A public IP address is a globally unique identifier assigned to a device on the internet. It serves as the address by which other devices on the internet can find and communicate with it. Public IP addresses are assigned by the Internet Assigned Numbers Authority (IANA) to Internet Service Providers (ISPs) and other organizations that control access to the global internet.

In Linux, you can determine the public IP address of a system by using external services or commands like curl or wget to query a web service. For example:

```
curl ifconfig.me
```
This command retrieves your public IP address from a web service.

Public IP addresses are essential for servers, websites, and other devices that need to be directly accessible from the internet. They are globally routable, meaning they can be reached from any location on the internet.

Different Ways to Find Your Public IP Address in Linux
### 1) Using `wget` with `ifconfig.me` to Find Your IP Address in Linux

Similar to curl, this uses the ifconfig.me service to fetch your public IP address.
```
wget -qO- ifconfig.me
```
<img width="587" height="44" alt="image" src="https://github.com/user-attachments/assets/71b65f41-5880-4076-8e61-cf6896af9b7b" />

Using `wget` with `ifconfig.me` to Find Your IP Address in Linux
Using `wget` with `ifconfig.me` to Find Your IP Address in Linux
### 2) Using `dig` with `resolver1.opendns.com` to Find Your IP Address in Linux

This command uses the OpenDNS resolver to query your public IP address.
```
dig +short myip.opendns.com @resolver1.opendns.com
```
<img width="838" height="40" alt="image" src="https://github.com/user-attachments/assets/e91681a4-5143-4147-96e6-36946b0f6388" />


3) Using `curl` with `icanhazip.com`to Find Your IP Address in Linux

This command queries the icanhazip.com service to obtain your public IP address.
```
curl icanhazip.com
```
<img width="582" height="39" alt="image" src="https://github.com/user-attachments/assets/e8f478c8-c607-4b4f-b0e9-ad8d2452760f" />


4) Using `wget` with `icanhazip.com` to Find Your IP Address in Linux

Similar to the curl command, this uses the icanhazip.com service to fetch your public IP address.
```
wget -qO- icanhazip.com
```
<img width="611" height="40" alt="image" src="https://github.com/user-attachments/assets/13fed0f6-3b08-4093-8b38-3b514a8a1ac9" />


5) Using host with dns.google to Find Your IP Address in Linux

This command utilizes the DNS service provided by Google to resolve your public IP address.
```
host myip.opendns.com resolver1.opendns.com
```

<img width="776" height="129" alt="image" src="https://github.com/user-attachments/assets/15f19520-7b7f-406f-ba32-5312fcceb928" />

## 2) How to Find Your Private IP Addresses in Linux:
Contrastingly, private IP addresses are used within a private network and are not directly accessible from the internet. These addresses are defined in reserved address ranges specified by the Internet Engineering Task Force (IETF) in RFC 1918. The commonly used private IP address ranges are:

✔ 10.0.0.0 to 10.255.255.255 (10.0.0.0/8)
✔ 172.16.0.0 to 172.31.255.255 (172.16.0.0/12)
✔ 192.168.0.0 to 192.168.255.255 (192.168.0.0/16)
These addresses are intended for use in local networks, such as home or corporate intranets. Devices within the same private network can communicate with each other using these private IP addresses, but they rely on a mechanism called Network Address Translation (NAT) to access the internet through a shared public IP address.

In Linux, you can view the private IP addresses of your system using the ifconfig or ip addr commands. For example:
```
ifconfig
or
ip addr
```
Different Ways to Find Your Private IP Address in Linux
### 1) Using `hostname` to Find Your IP Address in Linux

The -I option with the hostname command can be used to display the private IP address of your machine.
```
hostname -I
```

<img width="501" height="40" alt="image" src="https://github.com/user-attachments/assets/6c0689eb-64bb-4669-9c2b-da8af08f998e" />


### 2) Using `nmcli` (NetworkManager command-line tool) to Find Your IP Address in Linux

If you're using NetworkManager, this command filters out IPv4 addresses associated with your network interfaces.
```
nmcli dev show | grep IP4.ADDRESS
```
<img width="689" height="79" alt="image" src="https://github.com/user-attachments/assets/b743a991-7655-47a0-bf30-328440df044c" />

### 3) Using `awk` with `ifconfig` to Find Your IP Address in Linux

This command uses the awk tool to filter and print only the private IP addresses from the ifconfig output.
```
ifconfig | awk '/inet / {print $2}'
```
<img width="703" height="74" alt="image" src="https://github.com/user-attachments/assets/ade5c8ff-3321-4a4a-89d2-634fd994be26" />

### 4) Using `grep` with `ip` to Find Your IP Address in Linux

This command uses grep with Perl-compatible regular expressions to extract private IP addresses from the ip command output.
```

ip addr show | grep -oP 'inet \K[\d.]+'
```
### 5) Using `ss` (socket statistics) command to Find Your IP Address in Linux

This complex command lists the IP addresses to which the system is listening for incoming connections.

```
ss -tunapl | grep LISTEN | awk '{print $5}' | cut -d: -f1 | sort -u

```

## Linux ifconfig Command Examples
Display Specific Network Interface
This command shows detailed information about the specified interface, eth0.
```

ifconfig eth0
```
Enable a Network Interface
This command activates the specified network interface, eth0.
```

ifconfig eth0 up
```
Disable a Network Interface
This command deactivates the specified network interface, eth0.
```

ifconfig eth0 down
```
Assign an IP Address
This command assigns the IP address 192.168.1.10 to the specified network interface, eth0.
```

ifconfig eth0 192.168.1.10
```
Set a Netmask
This command sets the netmask for the specified network interface, eth0.
```

ifconfig eth0 netmask 255.255.255.0
```
Set a Broadcast Address
This command sets the broadcast address for the specified network interface, eth0.
```

ifconfig eth0 broadcast 192.168.1.255
```
Change the MAC Address
This command changes the MAC address of the specified network interface, eth0.
```

ifconfig eth0 hw ether 00:1a:2b:3c:4d:5e
```

Add an Alias to a Network Interface
This command adds an alias with IP address 192.168.1.20 to the specified network interface, eth0.
```
ifconfig eth0:0 192.168.1.20
```
Remove an Alias from a Network Interface
This command removes the alias eth0:0 from the specified network interface.
```
ifconfig eth0:0 down
```
ifconfig Gateway
To set a gateway using the ifconfig command, you typically need to use route because ifconfig itself does not configure gateways. Here's how to do it in a simple way:

Set IP Address and Netmask (if needed):
```
ifconfig eth0 192.168.1.10 netmask 255.255.255.0
```

Set Default Gateway:
```

route add default gw 192.168.1.1
```
Here, 192.168.1.1 is the IP address of the gateway.
---
# Conclusion 

In this article, we've explored how to find your IP address in Linux using the ifconfig command. We also discuss what is private and public IP address and how to display both of the IP Address .This essential skill is crucial for effective network management. Whether you're a seasoned Linux user or a beginner, understanding these simple commands empowers you to navigate and control your network effortlessly.
---
