# SUBLIST3R
## What is Sublist3r and How to Use it?

Sublister is a tool designed in python and uses OSINT in order to enumerate subdomains of websites. It helps pen-testers in collecting and gathering subdomains for a domain which is their target. In order to fetch the accurate results, sublilster uses many search engines like Google, Yahoo, etc. and even tools like Netcraft, Virustotal, etc.

### Installing and using sublister

Install Sublist3r and its dependencies, inside a python3 virtual env as detailed in installation steps below, in order to avoid non-tool specific python related errors that normally result from broken dependencies when user installs several dependency-conflicting python tools under the system-wide python installation.
Any issues raised due to inappropriate user installation will be closed to allow focus on resolving real bugs and implementing new features

The installation steps assume you will keep your python virtual envs in a folder called environments under your home directory directory:

## sublist3r Install
Run sublist3r -h to verify if Sublist3r is already installed, as it comes pre-packaged in recent Kali versions. If the help menu appears, no installation is needed.​

Native Package Install
Update packages and install via apt:
```
sudo apt update
```
```
sudo apt install sublist3r
```

## Usage

| Short Form | Long Form       | Description                                                                 |
|------------|----------------|---------------------------------------------------------|
| `-d`       | `--domain`     | Domain name to use for subdomain enumeration                                 |
| `-b`       | `--bruteforce` | Turn on **aiodnsbrute** bruteforce mode                                      |
| `-p`       | `--ports`      | Check / filter subdomain results for open TCP ports (comma-separated ports) |
| `-v`       | `--verbose`    | Enable verbose mode and display results in real time                         |
| `-t`       | `--threads`    | Number of threads to use for **aiodnsbrute** bruteforce                      |
| `-e`       | `--engines`    | Specify a comma-separated list of search engines                             |
| `-o`       | `--output`     | Save results to a text file                                                  |
| `-h`       | `--help`       | Show the help message and exit                                               |



<img width="951" height="603" alt="image" src="https://github.com/user-attachments/assets/aa9c6885-0581-42b5-8e4e-1fd6735e02a1" />

# Install Requirements
---
Kali Linux is blocking `pip install -r requirements.txt` because Python is in an **externally-managed environment** (PEP 668).

You have **3 safe ways** to fix this:

---

### ✅ Option 1: Use Virtual Environment (recommended)

This avoids breaking system Python.

Install venv if missing
```bash
sudo apt install python3-venv -y
```
Create virtual environment
```bash
python3 -m venv venv
```
Activate it
```bash
source venv/bin/activate
```
Install requirements
```bash
sudo su
pip3 install -r requirements.txt
```
or
```
sudo apt install python3-requests python3-dnspython

```

Later, whenever you want to use the tool:

```bash
source venv/bin/activate
```

---

### ✅ Option 2: Use `--break-system-packages` (quick but riskier)

If you don’t want to use venv and want to force-install globally:

```bash
sudo pip install -r requirements.txt --break-system-packages
```

⚠️ Warning: This can mess with Kali’s system Python, so use only if you know what you’re doing.

---

### ✅ Option 3: Use `pipx` (clean isolation for apps)

If Sublist3r is meant to be used like a tool:

```bash
sudo apt install pipx -y
```
```bash
pipx install -r requirements.txt
```

This way, it keeps things isolated without breaking system packages.

---

