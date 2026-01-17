# Google Dorhing

Google Dorking, also known as Google Hacking, is a reconnaissance technique that uses advanced search operators to uncover sensitive or unusual information that search engines have indexed but that is not readily available through normal queries. By crafting specialized search strings called "dorks," a researcher can find everything from exposed passwords and private files to live camera feeds and administrative login portals.

## How Google Dorking Works

#### google hacking darking

```
https://www.exploit-db.com/google-hacking-database

```

Dorking relies on advanced operators that refine search results far beyond a standard keyword search. These operators allow you to target specific parts of a website or file:

* intitle:: Searches for specific text in the title of a webpage (e.g., intitle:"index of" to find directory listings).

* inurl:: Looks for specific strings within a URL (e.g., inurl:admin to find management pages).

* filetype:: Restricts results to specific formats, such as PDF, XLS (spreadsheets), or LOG (log files).

* site:: Limits the search to a specific domain or top-level domain (e.g., site:gov.in to search only Indian government sites).

* intext:: Searches for specific words within the body content of a page.

* cache:: Shows Google's cached version of a site, which may contain information that has since been deleted.

## Search Logic and Modifiers

Researchers often combine operators with Boolean logic to create complex queries:

• Quotes (" "): Forces an exact phrase match.

• Dash (-): Excludes specific words or sites from the results (e.g., Linux -Wikipedia).

• Wildcard (*): Acts as a placeholder for any word or string.

• OR / Pipe (|): Searches for results containing either of the specified terms.


## The Google Hacking Database (GHDB)

Because creating custom dorks can be complex, the cybersecurity community maintains the Google Hacking Database (GHDB) at exploit-db.com. As of the sources' recording, it contains over 7,300 dorks categorized by the type of information they reveal, such as:

• Files containing "juicy" info: Spreadsheets with budgets, email lists, or configuration files.

• Vulnerable servers and files: Sites exposed to known software flaws or SQL injection vulnerabilities.

• Online devices: Real-time access to IoT devices, including routers and IP cameras.

• Login portals: Hidden administrative entry points.

## Examples of Common Dorks

• Finding Live Cameras: Using intitle:"live view" -axis or inurl:video.mjpeg can reveal unsecured live camera feeds.

• Exposing Passwords: A query like filetype:log intext:password targets log files that might have captured sensitive credentials.

• Administrative Data: Searching for inurl:admin filetype:xls can uncover administrative spreadsheets containing organizational data.

## Defensive Countermeasures

To protect against Google Dorking, organizations should perform OSINT on themselves regularly. By using these same dorks, a security team can identify their own exposed files or devices and then take action to delete them, patch the software, or shore up security settings before an attacker finds them

## Google Dork Operators (Advanced Search Operators)

#### Basic Search Operators

|Operator|	Description|	Example|
|----------------|--------------|-------------------|
|`" "`|	Exact phrase match	|`"error 404"`|
|`OR` |Either term	|`python OR java`|
|`AND`	|Both terms (default)	|`linux AND windows`|
|`-`	|Exclude term	|`jaguar -car`|
|`*`|	Wildcard	|`"how to * a website"`|


## Site/URL Operators

|Operator|	Description|	Example|
|----------|---------------|----------|
|`site:`	|Search specific site/domain	|`site:github.com python`|
|`inurl:`	|URL contains word	|`inurl:admin`|
|`allinurl:`|	URL contains all words|`allinurl:admin login`|
|`intitle:`|	Title contains word	|`intitle:"index of"`|
|`allintitle:`|	Title contains all words	|`allintitle:"login" "admin"`|

## File/Content Operators

|Operator|	Description	|Example|
|-----------|----------|------------|
|`filetype: / ext:`|	Specific file extension|`	filetype:pdf`|
|`intext:`|	Body contains word	|`intext:"password"`|
|`allintext:`|	Body contains all words	|`allintext:"username" "password"`|

## Advanced Operators

|Operator|	Description|	Example|
|---------------|-----------------|-----------|
|`cache:`|	Cached version	|`cache:example.com`|
|`link:`|Sites linking to URL|`link:github.com`|
|`related:`|	Related sites	|`related:twitter.com`|
|`define:`	|Definitions	|`define:API`|
|`info:`|	Site information	|`info:example.com`|

## Date/Number Ranges

|Operator	|Description	|Example|
|--------------------------------|------------------|----------------|
|`..`|	Number range	|`python 2020..2024`|
|`before: / after:`|	Date range|`COVID after:2023-01-01`|
|`daterange:`|	Custom date range	|`daterange:2459580-2459585`|

## Security/Admin Examples


```
# Find login pages
site:target.com inurl:login
intitle:"login" "admin" site:gov

# Find exposed documents
filetype:pdf "confidential" site:company.com

# Find directory listings
intitle:"index of" "parent directory"

# Find specific config files
ext:env DB_PASSWORD=

# Find subdomains
site:*.target.com

# Find API keys
"api_key" "github.com"
```

### Pro Tips

Combine operators:` site:edu filetype:pdf "research paper"`

Use quotes for phrases:` "access denied"`

Exclude common results: `-site:wikipedia.org`

Search specific TLDs: `site:.gov "public report"`

Limit results: Add `&num=100` to URL for more results

### Important Notes

Operators work in Google Search and Google Hacking Database (GHDB)

Some operators are deprecated (`inanchor:`, `allinanchor:`)

Use responsibly - many results may be sensitive

Consider using `site:` with other operators for precision
























