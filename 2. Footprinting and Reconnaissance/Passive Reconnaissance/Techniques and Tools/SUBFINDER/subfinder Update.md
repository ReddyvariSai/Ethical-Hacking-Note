
# Subfinder 

```
                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ subfinder                                      

               __    _____           __         
   _______  __/ /_  / __(_)___  ____/ /__  _____
  / ___/ / / / __ \/ /_/ / __ \/ __  / _ \/ ___/
 (__  ) /_/ / /_/ / __/ / / / / /_/ /  __/ /    
/____/\__,_/_.___/_/ /_/_/ /_/\__,_/\___/_/

                projectdiscovery.io

[INF] Current subfinder version v2.6.0 (outdated)
[FTL] Program exiting: no input list provided
```

subfinder help

```
subfinder --help
```

```
                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ subfinder --help                               
Subfinder is a subdomain discovery tool that discovers subdomains for websites by using passive online sources.

Usage:
  subfinder [flags]

Flags:
INPUT:
   -d, -domain string[]  domains to find subdomains for
   -dL, -list string     file containing list of domains for subdomain discovery

SOURCE:
   -s, -sources string[]           specific sources to use for discovery (-s crtsh,github). Use -ls to display all available sources.
   -recursive                      use only sources that can handle subdomains recursively (e.g. subdomain.domain.tld vs domain.tld)
   -all                            use all sources for enumeration (slow)
   -es, -exclude-sources string[]  sources to exclude from enumeration (-es alienvault,zoomeye)

FILTER:
   -m, -match string[]   subdomain or list of subdomain to match (file or comma separated)
   -f, -filter string[]   subdomain or list of subdomain to filter (file or comma separated)

RATE-LIMIT:
   -rl, -rate-limit int  maximum number of http requests to send per second
   -t int                number of concurrent goroutines for resolving (-active only) (default 10)

UPDATE:
   -up, -update                 update subfinder to latest version
   -duc, -disable-update-check  disable automatic subfinder update check

OUTPUT:
   -o, -output string       file to write output to
   -oJ, -json               write output in JSONL(ines) format
   -oD, -output-dir string  directory to write output (-dL only)
   -cs, -collect-sources    include all sources in the output (-json only)
   -oI, -ip                 include host IP in output (-active only)

CONFIGURATION:
   -config string                flag config file (default "/home/kali/.config/subfinder/config.yaml")
   -pc, -provider-config string  provider config file (default "/home/kali/.config/subfinder/provider-config.yaml")
   -r string[]                   comma separated list of resolvers to use
   -rL, -rlist string            file containing list of resolvers to use
   -nW, -active                  display active subdomains only
   -proxy string                 http proxy to use with subfinder
   -ei, -exclude-ip              exclude IPs from the list of domains

DEBUG:
   -silent             show only subdomains in output
   -version            show version of subfinder
   -v                  show verbose output
   -nc, -no-color      disable color in output
   -ls, -list-sources  list all available sources
   -stats              report source statistics

OPTIMIZATION:
   -timeout int   seconds to wait before timing out (default 30)
   -max-time int  minutes to wait for enumeration results (default 10)
```

## subfinder update

sudo  subfinder -up

```
                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ sudo  subfinder -up 

               __    _____           __         
   _______  __/ /_  / __(_)___  ____/ /__  _____
  / ___/ / / / __ \/ /_/ / __ \/ __  / _ \/ ___/
 (__  ) /_/ / /_/ / __/ / / / / /_/ /  __/ /    
/____/\__,_/_.___/_/ /_/_/ /_/\__,_/\___/_/

                projectdiscovery.io

10.33 MiB / 10.33 MiB [-------------------------------------------------------] 100.00% 2.75 MiB p/s
[INF] Verified Integrity of subfinder_2.12.0_linux_amd64.zip

[INF] subfinder sucessfully updated 2.6.0 -> 2.12.0 (latest)

  ## What's Changed                                                           
                                                                              
  ### 🎉 New Features                                                         
                                                                              
  • Added API key support for HackerTarget by @dogancanbakir in               
  https://github.com/projectdiscovery/subfinder/pull/1622                     
  • Added Reconeer by @dogancanbakir in                                       
  https://github.com/projectdiscovery/subfinder/pull/1694                     
  • Added optional API key support for sources by @dogancanbakir in           
  https://github.com/projectdiscovery/subfinder/pull/1700                     
  • Added request tracking to -stats flag by @dogancanbakir in                
  https://github.com/projectdiscovery/subfinder/pull/1699                     
                                                                              
  Full Changelog:                                                             
  https://github.com/projectdiscovery/subfinder/compare/v2.11.0...v2.12.0     

```
## subfinder version 

ubfinder --version

```
┌──(kali㉿kali)-[~]
└─$ subfinder --version
[INF] Current Version: v2.12.0
[INF] Subfinder Config Directory: /home/kali/.config/subfinder

```


