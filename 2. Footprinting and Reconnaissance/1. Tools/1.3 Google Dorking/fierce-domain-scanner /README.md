# Fierce - DNS reconnaissance tool for locating non-contiguous IP space

Understanding the network structure of the organization is very important. So to locate targets both inside and outside a corporate network there is a tool designed in the Python Language known as Fierce. This tool is different from other tools as its main objective is to locate non-contiguous IP spaces and hostnames against specified domains or subdomains. The Fierce tool doesn't scan the total internet for our results but the results which it finds are really helpful in the process. This tool is open-source and free to use. The Fierce tool is very easier to use due to its tags of flags features.

> Note: Make Sure You have Python Installed on your System, as this is a python-based tool. Click to check the Installation process: Python Installation Steps on Linux

## Installation of Fierce Tool on Kali Linux

Step 1: Check whether Python Environment is Established or not, use the following command.

```
python3
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/80d7948d-d1a8-4879-a4fb-f3bb2daf2518" />


Step 2: Open up your Kali Linux terminal and move to the Desktop directory using the following command.

```
cd Desktop
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/3fd4c2f0-04d5-482e-b310-c563b2b8507f" />

Step 3: You are on Desktop now, create a new directory called Fierce using the following command. In this directory, we will complete the installation of the Fierce tool.

```
mkdir Fierce 
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/bb82bf05-adb3-4570-9049-c66c7264a928" />

Step 4: Now switch to the Fierce directory using the following command.

```
cd Fierce 
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/6c96c0c9-02ef-41b4-a0b4-46e5ba546fda" />

Step 5: Now you have to install the tool. You have to clone the tool from Github.

```
git clone git clone https://github.com/mschwager/fierce
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/13a30b98-9632-426d-b141-11ea50a898aa" />

Step 6: The tool has been downloaded successfully in the Fierce directory. Now list out the contents of the tool by using the below command.

```
ls
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/86798d40-781d-4f74-a017-f0c291522b16" />

Step 7: You can observe that there is a new directory created for the Fierce tool that has been generated while we were installing the tool. Now move to that directory using the below command:

```
cd fierce 
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/dccd0a55-7257-4eeb-b2af-9895e16e0ded" />

Step 8: Once again to discover the contents of the tool, use the below command.

```
ls
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/f4b41d19-7488-4c61-b187-a4fdd72f8d09" />

Step 9: Download the required packages for running the tool, use the following command.

```
pip3 install -r requirements.txt
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/c43ad0db-0158-4c72-a30a-639358302112" />

Step 10: Now we are done with our installation, Use the below command to view the help (gives a better understanding of the tool) index of the tool.

```
python3 fierce/fierce.py -h
```

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/f25ca151-6bb7-460a-8b11-5e748f5fa298" />

## Attributes

The fierce tool has the attributes to perform Reverse Lookups for the specified range of IP addresses.  [--dns-file] option is used.

The fierce tool has the attribute to enumerate Domain Name System Records on the Target domain. [--dns-servers] option is used

The fierce tool has the attribute of performing Internal as well as External IP ranges Enumeration. [--range] option is used.

Class C IP addresses are also supported by the Fierce tool. [--traverse] option is used.

The fierce tool has the attribute to Scan Name Server Directory and also Zone Transfer attack.

## How does Fierce  Tool perform Scanning?

The fierce tool is the most helpful tool for the Reconnaissance, Information Gathering, and Scanning phase in the process of Penetration Testing or Network Testing. The working of this tool is very simple. At the very first stage, the tool performs scanning with brute-forcing attacks and can also perform zone transfer attacks on the target is possible. There are massive word lists that contain possible words, through which subdomains of the target can be enumerated. If the subdomain is not in the list, then there is no chance of detection of the subdomain on the target.

## Additional Features and Functions

## 1. Saving

Unfortunately, there is no inbuilt function available for storing the results of the Fierce scan on the target at your disk. Although no saving function is available, so there is no feature to save the output in various formats. But you can redirect the output of the scan into any text file with some Linux skills and terminal commands.

## 2. Range Scan

One of the amazing functions or features of the Fierce tool is the Range scan. You can scan the range of IP address with a single click. --the range is the option that is mandatory while performing a range scan. You need to specify the IP address; like ( 192.168.28.4/24).

## 3. Dictionary file

A brute-forcing attack or method approach is used for enumeration or detection of subdomains associated with the target domain. The inbuilt wordlist file is activated when the installation of the Fierce tool is done on the system. But Fierce tool allows users to use custom subdomains wordlists with a massive number of possible subdomains words. --subdomain-file is the option for using the custom wordlists for brute-forcing.

## Working with Fierce Tool on Kali Linux

### Example 1: Basic

```
fierce --domain geeksforgeeks.org --subdomains write admin videos
```

In this Example, We are performing a simple scan using the subdomain words which include write, admin, videos. We have chosen geeksforgeeks.org as our target.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/b029d64b-2262-4153-8004-47da104a0cff" />


Example 2: Traverse IPs near discovered domains to search for contiguous blocks with the --traverse flag

```
fierce --domain geeksforgeeks.org --subdomains videos --traverse 10
```

In this Example, We are scanning domains near discovered records. Our target domain is geeksforgeeks.org

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/43bcbcce-8b00-4fae-a3b6-df00b31098d3" />


Example 3: Attempt an HTTP connection on domains discovered with the --connect flag

```
fierce --domain stackoverflow.com --subdomains mail --connect
```

In this Example, We are attempting HTTP connection on the domains using the connect flag. We have chosen a different target for this Example, which is stackoverflow.com.

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/fa1c1f8c-c903-4d8d-80ec-158925bfecc3" />


Example 4: Exchange speed for breadth with the --wide flag, which looks for nearby domains on all IPs of the /24 of a discovered domain

```

fierce --domain geeksforgeeks.org --wide
```

In this example, We will scan the entire class of discovered records. (Full Detailed Scan)

<img width="600" height="338" alt="image" src="https://github.com/user-attachments/assets/74cf4e62-2a5b-473a-beeb-f77a94c0a2fe" />



Example 5: Zone transfers are rare these days, but they give us the keys to the DNS castle.

```
fierce --domain geeksforgeeks.org
```

In this Example, We are performing a basic scan without any arguments on geeksforgeeks.org

<img width="1000" height="562" alt="image" src="https://github.com/user-attachments/assets/757a8015-cef5-4110-9d16-533a6ae123c1" />






