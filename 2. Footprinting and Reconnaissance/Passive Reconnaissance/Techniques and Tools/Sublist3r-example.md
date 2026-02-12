

```
                                                                                                                                                         
┌──(kali㉿kali)-[~]
└─$ sublist3r                           

                 ____        _     _ _     _   _____                                                                                                       
                / ___| _   _| |__ | (_)___| |_|___ / _ __                                                                                                  
                \___ \| | | | '_ \| | / __| __| |_ \| '__|                                                                                                 
                 ___) | |_| | |_) | | \__ \ |_ ___) | |                                                                                                    
                |____/ \__,_|_.__/|_|_|___/\__|____/|_|                                                                                                    
                                                                                                                                                           
                # Coded By Ahmed Aboul-Ela - @aboul3la                                                                                                     
                                                                                                                                                           
Usage: python3 /usr/bin/sublist3r [Options] use -h for help                                                                                                
Error: the following arguments are required: -d/--domain               
```

```
sublist3r --help

```
```

──(kali㉿kali)-[~]
└─$ sublist3r --help
usage: sublist3r [-h] -d DOMAIN [-b [BRUTEFORCE]] [-p PORTS] [-v [VERBOSE]] [-t THREADS] [-e ENGINES] [-o OUTPUT] [-n]

OPTIONS:
  -h, --help            show this help message and exit
  -d, --domain DOMAIN   Domain name to enumerate it's subdomains
  -b, --bruteforce [BRUTEFORCE]
                        Enable the subbrute bruteforce module
  -p, --ports PORTS     Scan the found subdomains against specified tcp ports
  -v, --verbose [VERBOSE]
                        Enable Verbosity and display results in realtime
  -t, --threads THREADS
                        Number of threads to use for subbrute bruteforce
  -e, --engines ENGINES
                        Specify a comma-separated list of search engines
  -o, --output OUTPUT   Save the results to text file
  -n, --no-color        Output without color

Example: python3 /usr/bin/sublist3r -d google.com


```

It takes lort of time to scane the data about host in the web page or web site.



```
|──(kali㉿kali)-[~]
└─$ sublist3r -d eccouncil.org        

                 ____        _     _ _     _   _____                                                                                                       
                / ___| _   _| |__ | (_)___| |_|___ / _ __                                                                                                  
                \___ \| | | | '_ \| | / __| __| |_ \| '__|                                                                                                 
                 ___) | |_| | |_) | | \__ \ |_ ___) | |                                                                                                    
                |____/ \__,_|_.__/|_|_|___/\__|____/|_|                                                                                                    
                                                                                                                                                           
                # Coded By Ahmed Aboul-Ela - @aboul3la                                                                                                     
                                                                                                                                                           
[-] Enumerating subdomains now for eccouncil.org                                                                                                           
[-] Searching now in Baidu..
[-] Searching now in Yahoo..
[-] Searching now in Google..
[-] Searching now in Bing..
[-] Searching now in Ask..
[-] Searching now in Netcraft..
[-] Searching now in DNSdumpster..
[-] Searching now in Virustotal..
[-] Searching now in ThreatCrowd..
[-] Searching now in SSL Certificates..
[-] Searching now in PassiveDNS..
[!] Error: Virustotal probably now is blocking our requests
[!] DNSDumpster module failed: Could not find CSRF token on DNSDumpster page
[-] Total Unique Subdomains Found: 149
www.eccouncil.org
66trainingllcservices.eccouncil.org
academia.eccouncil.org
www.academia.eccouncil.org
accesscomputertraining.eccouncil.org
ace.eccouncil.org
www.ace.eccouncil.org
affiliate.eccouncil.org
affiliates.eccouncil.org
aletheiasolutionsinc.eccouncil.org
aptechqatarcomputereducationcentre.eccouncil.org
aspen.eccouncil.org
www.aspen.eccouncil.org
aspenadmin.eccouncil.org
associate-cciso.eccouncil.org
atc-bestlink-strategies.eccouncil.org
aware.eccouncil.org
backend-codered.eccouncil.org
bestlinkstrategies.eccouncil.org
blog.eccouncil.org
blogtest.eccouncil.org
campaign.eccouncil.org
campaigns.eccouncil.org
captivasolutions.eccouncil.org
staging.careers.eccouncil.org
cedsolutions.eccouncil.org
cert.eccouncil.org
www.cert.eccouncil.org
certblog.eccouncil.org
checkout.eccouncil.org
checkout-india.eccouncil.org
checkout-us.eccouncil.org
cia.eccouncil.org
ciso.eccouncil.org
www.ciso.eccouncil.org
cisoconsultancy.eccouncil.org
cisomag.eccouncil.org
codered.eccouncil.org
codered-enterprise.eccouncil.org
codered-india.eccouncil.org
coderedcheckout.eccouncil.org
coderedcheckout-uk.eccouncil.org
coderedmarketing.eccouncil.org
community.eccouncil.org
connect.eccouncil.org
continuing-education-institute.eccouncil.org
ctfevent-dev.eccouncil.org
cybacybersecuritycenter.eccouncil.org
cyberleague.eccouncil.org
cyberplus.eccouncil.org
cyberq.eccouncil.org
cyberresearch.eccouncil.org
cybersecurity.eccouncil.org
cybersecuritypro.eccouncil.org
desertclouds.eccouncil.org
dev-gravity.eccouncil.org
dev-iclass.eccouncil.org
dev-staging.eccouncil.org
dev-wpp.eccouncil.org
devgeo.eccouncil.org
drm.eccouncil.org
www.drm.eccouncil.org
ebooks.eccouncil.org
ebooks2.eccouncil.org
ecc-backup.eccouncil.org
ecctest.eccouncil.org
eclstore.eccouncil.org
ecsa-grandfathering.eccouncil.org
egs.eccouncil.org
email.eccouncil.org
ethicalhacking.eccouncil.org
ferrotechnicsinc.eccouncil.org
fndtst.eccouncil.org
fortifyinstitute.eccouncil.org
foundation.eccouncil.org
www.foundation.eccouncil.org
frank.eccouncil.org
frontend-codered.eccouncil.org
greencircle.eccouncil.org
grismtechnologies.eccouncil.org
hidt.eccouncil.org
hub.eccouncil.org
iclass.eccouncil.org
www.iclass.eccouncil.org
dev-wpp.iclass.eccouncil.org
iclass2.eccouncil.org
ictacademy.eccouncil.org
idcybersolutions.eccouncil.org
identity.eccouncil.org
................
....................
........................
```




