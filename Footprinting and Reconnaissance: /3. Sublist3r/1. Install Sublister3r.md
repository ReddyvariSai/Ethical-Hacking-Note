# About Sublist3r

Sublist3r is a python tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting. Sublist3r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu and Ask. Sublist3r also enumerates subdomains using Netcraft, Virustotal, ThreatCrowd, DNSdumpster and ReverseDNS.

subbrute was integrated with Sublist3r to increase the possibility of finding more subdomains using bruteforce with an improved wordlist. The credit goes to TheRook who is the author of subbrute.
# Screenshots
Sublist3r.py
### Installation 
```bash
git clone https://github.com/aboul3la/Sublist3r.git
```
About Sublist3r

Sublist3r is a python tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting. Sublist3r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu and Ask. Sublist3r also enumerates subdomains using Netcraft, Virustotal, ThreatCrowd, DNSdumpster and ReverseDNS.

subbrute was integrated with Sublist3r to increase the possibility of finding more subdomains using bruteforce with an improved wordlist. The credit goes to TheRook who is the author of subbrute.
Screenshots

Sublist3r
Installation

git clone https://github.com/aboul3la/Sublist3r.git

Recommended Python Version:

Sublist3r currently supports Python 2 and Python 3.

The recommended version for Python 2 is 2.7.x
The recommended version for Python 3 is 3.4.x

## Dependencies:

Sublist3r depends on the `requests`,`dnspython` and `argparse` python modules.

These dependencies can be installed using the requirements file:

Installation on Windows:
```bash
c:\python27\python.exe -m pip install -r requirements.txt
```
Installation on Linux
```bash
sudo pip install -r requirements.txt
```
Alternatively, each module can be installed independently as shown below.
Requests Module (http://docs.python-requests.org/en/latest/)

Install for Windows:

```dash
c:\python27\python.exe -m pip install requests
```
Install for Ubuntu/Debian:
```bash
sudo apt-get install python-requests
```
Install for Centos/Redhat:
```bash
sudo yum install python-requests
```
Install using pip on Linux:
```bash
sudo pip install requests
```
dnspython Module (http://www.dnspython.org/)

Install for Windows:
```bash
c:\python27\python.exe -m pip install dnspython
```
Install for Ubuntu/Debian:
```bash
sudo apt-get install python-dnspython
```
Install using pip:
```bash
sudo pip install dnspython
```
argparse Module
Install for Ubuntu/Debian:
```bash
sudo apt-get install python-argparse
```
Install for Centos/Redhat:
```bash
sudo yum install python-argparse
```
Install using pip:
```bash
sudo pip install argparse
```
for coloring in windows install the following libraries
```bash
c:\python27\python.exe -m pip install win_unicode_console colorama
```
### Usage
## Options

| Short Form | Long Form     | Description                                           |
|------------|---------------|-------------------------------------------------------|
| `-d`       | `--domain`    | Domain name to enumerate subdomains of               |
| `-b`       | `--bruteforce`| Enable the subbrute bruteforce module                |
| `-p`       | `--ports`     | Scan the found subdomains against specific TCP ports |
| `-v`       | `--verbose`   | Enable verbose mode and display results in realtime  |
| `-t`       | `--threads`   | Number of threads to use for subbrute bruteforce     |
| `-e`       | `--engines`   | Specify a comma-separated list of search engines     |
| `-o`       | `--output`    | Save the results to a text file                      |
| `-h`       | `--help`      | Show the help message and exit                       |

## Examples

List basic options and switches:

```bash
python sublist3r.py -h
```

Enumerate subdomains of a domain:

```bash
python sublist3r.py -d example.com
```

Enumerate subdomains and show only those with open ports 80 and 443:

```bash
python sublist3r.py -d example.com -p 80,443
```

Enumerate subdomains and display results in real time (verbose):

```bash
python sublist3r.py -v -d example.com
```

Enumerate subdomains and enable the bruteforce module:

```bash
python sublist3r.py -b -d example.com
```

Enumerate subdomains using specific search engines (comma-separated):

```bash
python sublist3r.py -e google,yahoo,virustotal -d example.com
```

---

## Using Sublist3r as a Python module

### Example (import & call)

```python
import sublist3r

subdomains = sublist3r.main(
    domain,            # string: target domain
    no_threads,        # int: number of threads
    savefile,          # str or None: path to save results
    ports,             # str or None: comma-separated TCP ports, e.g. "80,443"
    silent,            # bool: run silently (less logging)
    verbose,           # bool: show results in realtime
    enable_bruteforce, # bool: enable bruteforce module
    engines            # list or str or None: specific engines, e.g. "google,yahoo"
)
```

### Function parameter descriptions

| Parameter           | Type                | Description                                        |
| ------------------- | ------------------- | -------------------------------------------------- |
| `domain`            | `str`               | Domain to enumerate (e.g. `'example.com'`)         |
| `no_threads`        | `int`               | Number of threads to use for bruteforce/search     |
| `savefile`          | `str`/`None`        | Path to save results (text file)                   |
| `ports`             | `str`/`None`        | Comma-separated TCP ports to scan, e.g. `"80,443"` |
| `silent`            | `bool`              | If `True`, minimize noisy output                   |
| `verbose`           | `bool`              | If `True`, display found subdomains in real time   |
| `enable_bruteforce` | `bool`              | If `True`, enable bruteforce module                |
| `engines`           | `str`/`list`/`None` | Optional engines to use (comma separated or list)  |

### Example: enumerate Yahoo subdomains and save to file

```python
import sublist3r

subdomains = sublist3r.main(
    'yahoo.com',
    40,
    'yahoo_subdomains.txt',
    ports=None,
    silent=False,
    verbose=False,
    enable_bruteforce=False,
    engines=None
)
```

The `main` function returns a set (or list) of unique subdomains found by Sublist3r.

---

## License

Sublist3r is licensed under the **GNU GPL**. See the `LICENSE` file for full details.
