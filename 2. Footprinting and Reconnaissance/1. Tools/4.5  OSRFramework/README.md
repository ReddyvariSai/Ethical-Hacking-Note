# OSRFramework

OSRFramework installs easily on Kali Linux as a native package. 

This open-source intelligence toolset supports username checks, domain lookups, and more across numerous platforms.​

## Preferred Method

Update your package list and install directly from Kali repositories for a stable, dependency-managed version.
Run these commands in the terminal:

<img width="1593" height="866" alt="Screenshot 2026-01-04 104840" src="https://github.com/user-attachments/assets/6e6a5645-c103-4ad2-961c-8e8070c0f2a9" />

<img width="1576" height="832" alt="Screenshot 2026-01-04 104911" src="https://github.com/user-attachments/assets/eb86bc81-8974-4c10-acd0-4a5fb5a2f445" />

```
sudo apt update
sudo apt install osrframework
```

This installs version 0.17.2 or the latest available, along with required Python dependencies like python3-bs4 and python3-requests.​

## Alternative: Pip Install

Use pip for the latest release (0.18.8 as of last update) if the repo version lacks features.
First ensure pip3 is ready: `sudo apt install python3-pip`. Then execute:

```
sudo pip3 install osrframework
```

Upgrade later with `sudo pip3 install osrframework --upgrade`.​​

## Verification

Confirm installation by running `osrf --help` or `usufy.py -h`. These display available tools like usufy, mailfy, and domainfy.​​


## Source Download

Clone the GitHub repo for manual build or customization: `git clone` https://github.com/i3visio/osrframework.git. Follow the INSTALL.md for setup, though package methods are simpler.​

## OSRFramework Description

OSRFramework is Open Sources Research Framework.

OSRFramework is a GNU AGPLv3+ set of libraries developed by i3visio to perform Open Source Intelligence tasks. They include references to a bunch of different applications related to username checking, DNS lookups, information leaks research, deep web search, regular expressions extraction and many others. At the same time, by means of ad-hoc Maltego transforms, OSRFramework provides a way of making these queries graphically as well as several interfaces to interact with like OSRFConsole or a Web interface.

Homepage: https://github.com/i3visio/osrframework

Author: Yaiza Rubio and Félix Brezo

License: GNU AGPLv3+

## Tools included in OSRFramework

The following tools are available in OSRFramework:

1. `alias_generator` is a tool that tries to create possible nicknames based on the entered known data about the person
2. `entify` is utility that uses regular expressions to retrieve objects - searches for records of 13 regular expression patterns
3. `osrfconsole` is console interface for the Open Sources Research Framework
4. `phonefy` is a tool that checks on four platforms, whether the phone number was associated with spam
5. `usufy` checks whether a user name (profile) exist among about 300 platforms
6. `domainfy` checks the existence of a given domain for 1567 top-level domains
7. `mailfy` checks if this email address exists and finds social media, web sites and web services where the email leaked
8. `osrframework_server` is web interface for the Open Sources Research Framework
9. `searchfy` searches for profiles by full names and other information

# OSRFramework Help

OSRFramework is a framework consisting of a number of scripts. Further information and information on each of them are given.

## alias_generator Help

alias_generator is a tool that tries to create possible aliases based on the inputs known from a person.

usage:

````
alias_generator [-n < NAME >] [-s1 < SURNAME_1 >] [-s2 < SURNAME_2 >]
                      [-c < CITY >] [-C < COUNTRY >] [-y < YEAR >]
                      [-o < path_to_output_file >] [--numbers] [--common_words]
                      [--leet] [--locales] [--extra_words EXTRA_WORDS] [-h]
                      [--version]
```

```

optional arguments:
  -n <NAME>, --name <NAME>
                        Name of the person.
  -s1 <SURNAME_1>, --surname1 <SURNAME_1>
                        First surname.
  -s2 <SURNAME_2>, --surname2 <SURNAME_2>
                        Second surname.
  -c <CITY>, --city <CITY>
                        A city linked to the profile.
  -C <COUNTRY>, --country <COUNTRY>
                        A country.
  -y <YEAR>, --year <YEAR>
                        Birth year.
  -o <path_to_output_file>, --outputFile <path_to_output_file>
                        Path to the output file.
 
Profile squatting arguments:
  Showing additional configuration options for this program based on the
  original -s option in usufy.py.
 
  --numbers             Adds numbers at the end of the nicknames.
  --common_words        Adds some famous words at the end of the nicknames.
  --leet                Adds the leet mode to change 'a' by '4', 'e' by '3',
                        etc.
  --locales             Adds ending linked to countries.
  --extra_words EXTRA_WORDS
                        Adds new words to the nicknames provided by the user.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.

````

# entify Help

entify is a program designed to extract using regular expressions all the entities from the files on a given folder. This software also provides an interface to look for these entities in any given text.

usage: 

````
entify (-r <name> [< name >< sum_ext >< sum_ext > < path_to_output_folder >< verbosity >< alternative_header_file >< path_to_log_folder] >] [-q]
              [-L ] [-F ]
              [-v  ...]] [-o  [ ...] | -R <regular_expression> | --license)
              (-i <path_to_input_folder> | -w <url>)
              [-e < sum_ext > [< sum_ext > ...]] [-o < path_to_output_folder >]
              [-v < verbosity >] [-F < alternative_header_file >] [-q]
              [-L < path_to_log_folder ] [--recursive] [-h] [--version]
````

````
Input options (one required):
  -r <name> [< name > ...], --regexp < name > [< name > ...]
                        select the regular expressions to be looked for
                        amongst the following: ['all',
                        'i3visio.bitcoin.address', 'i3visio.dni',
                        'i3visio.dogecoin.address', 'i3visio.email',
                        'i3visio.ipv4', 'i3visio.litecoin.address',
                        'i3visio.md5', 'i3visio.namecoin.address',
                        'i3visio.peercoin.address', 'i3visio.sha1',
                        'i3visio.sha256', 'i3visio.uri']
  -R <regular_expression>, --new_regexp <regular_expression>
                        add a new regular expression, for example, for testing
                        purposes.
  --license             shows the AGPLv3+ license and exists.
  -i <path_to_input_folder>, --input_folder <path_to_input_folder>
                        path to the folder to analyse.
  -w <url>, --web <url>
                        URI to be recovered and analysed.
 
Processing arguments:
  Configuring the processing parameters.
 
  -e <sum_ext> [< sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy.py will try to create;
                        if this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -v <verbosity>, --verbose <verbosity>
                        select the verbosity level: 0 - none; 1 - normal
                        (default); 2 - debug.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>.
  -q, --quiet           Asking the program not to show any output.
  -L <path_to_log_folder, --logfolder <path_to_log_folder
                        path to the log folder. If none was provided, ./logs
                        is assumed.
  --recursive           Variable to tell the system to perform a recursive
                        search on the folder tree.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.
````

## osrfconsole Help

OSRFConsole is a terminal GUI to interact with OSRFramework utilities.

OSRFramework stands for Open Sources Research Framework. It includes a set of tools that help the analyst in the task of user profiling making use of different OSINT tools.

## phonefy Help

phonefy.py is piece of software that checks the existence of a given series of phones in a bunch of phone number lists associated to malicious activities.

usage: 
````
phonefy.py (--license | -n <phones> [< phones > ...])
                  [-e < sum_ext > [< sum_ext > ...]] [-o < path_to_output_folder >]
                  [-p < platform > [< platform > ...]]
                  [-F < alternative_header_file >] [--quiet] [-w]
                  [-x < platform > [< platform > ...]] [-h] [--version]
````

````
Input options (one required):
  --license             shows the GPLv3+ license and exists.
  -n <phones> [< phones > ...], --numbers < phones > [< phones > ...]
                        the list of phones to process (at least one is
                        required).
 
Processing arguments:
  Configuring the way in which usufy will process the identified profiles.
 
  -e <sum_ext> [< sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy.py will try to create;
                        if this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -p <platform> [< platform > ...], --platforms < platform > [< platform > ...]
                        select the platforms where you want to perform the
                        search amongst the following: ['all',
                        'infotelefonica', 'kimatel', 'listaspam']. More than
                        one option can be selected.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>.
  --quiet               tells the program not to show anything.
  -w, --web_browser     opening the URIs returned in the default web browser.
  -x <platform> [< platform > ...], --exclude < platform > [< platform > ...]
                        select the platforms that you want to exclude from the
                        processing.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.
````

# usufy Help

usufy - Piece of software that checks the existence of a profile for a given user in dozens of different platforms.

usage: 

````
usufy (--info <action> | --license | -b | -f <path_to_fuzzing_list> | -l <path_to_nick_list> | -n <nick> [< nick > ...] | --show_tags)
             [-p < platform > [< platform > ...]] [-t < tag > [< tag > ...]]
             [-x < platform > [< platform > ...]] [--avoid_download]
             [--avoid_processing] [--fuzz_config < path_to_fuzz_list >]
             [--nonvalid < not_valid_characters >]
             [-e < sum_ext > [< sum_ext > ...]] [-L < path_to_log_folder] >] [-w] [-F < alternative_header_file >]
             [-T < num_threads> ] [-h] [-v < verbosity >] [--version]
Input options (one required):
  --info <action>       select the action to be performed amongst the
                        following: list_platforms (list the details of the
                        selected platforms), list_tags (list the tags of the
                        selected platforms). Afterwards, it exists.
  --license             shows the AGPLv3+ license and exists.
  -b, --benchmark       perform the benchmarking tasks.
  -f <path_to_fuzzing_list>, --fuzz <path_to_fuzzing_list>
                        this option will try to find usufy-like URLs. The list
                        of fuzzing platforms in the file should be (one per
                        line): <BASE_DOMAIN> <VALID_NICK>
  -l <path_to_nick_list>, --list <path_to_nick_list>
                        path to the file where the list of nicks to verify is
                        stored (one per line).
  -n <nick> [< nick > ...], --nicks < nick > [< nick > ...]
                        the list of nicks to process (at least one is
                        required).
  --show_tags           it will show the platforms grouped by tags.
 
Platform selection arguments:
  Criteria for selecting the platforms where performing the search.
 
  -p <platform> [< platform > ...], --platforms < platform > [< platform > ...]
                        select the platforms where you want to perform the
                        search amongst the following: ['all', '500px', 'abou',
                        'about', 'affilorama', 'anarchy101', 'angel',
                        'archive', 'arduino', 'ariva', 'armorgames', 'askfm',
                        'audiob', 'audioboo', 'authorstream', 'autospies',
                        'badoo', 'bandcamp', 'behance', 'bennugd', 'betblog',
                        'bitbucket', 'bitcointa', 'bitcointalk', 'bitly',
                        'bitrated', 'blackplanet', 'blip', 'blogmarks',
                        'blogspot', 'bookofmatches', 'boonex', 'bordom',
                        'boxedup', 'breakcom', 'bubok', 'bucketlistly',
                        'buddypic', 'burbuja.info', 'burdastyle', 'buzznet',
                        'cafemom', 'canva', 'carbonmade', 'cardinghispano',
                        'cardingmx', 'cardomain', 'care2', 'cartodb', 'cash',
                        'causes', 'ccm', 'ccsinfo', 'chess', 'cockos',
                        'codecademy', 'codementor', 'coderwall', 'coinbase',
                        'colourlovers', 'connectingsingles', 'contently',
                        'couchsurfing', 'crokes', 'crowdin', 'cryptofresh',
                        'dailymotion', 'datpiff', 'deviantart', 'digitalspy',
                        'disqus', 'doodle', 'douban', 'dreamstime',
                        'dribbble', 'drupal', 'dzone', 'ebay', 'echatta',
                        'ehow', 'eightbitme', 'ello', 'elmundo',
                        'emoneyspace', 'enfemenino', 'ethereum', 'etsy',
                        'eyeem', 'f6s', 'facebook', 'fanpop', 'fark',
                        'favstar', 'fiverr', 'flickr', 'flixster',
                        'foodspotting', 'forobtc', 'forocoches', 'foroptc',
                        'foros24h', 'forosperu', 'forospyware', 'fotolog',
                        'foursquare', 'freelancer', 'freemusicarchive',
                        'freerepublic', 'gamesheep', 'gametracker', 'gapyear',
                        'gather', 'geeksphone', 'genspot', 'getlocalization',
                        'getsatisfaction', 'github', 'goblinrefuge',
                        'goodreads', 'googleplus', 'gravatar', 'gsmspain',
                        'hi5', 'houzz', 'htcmania', 'hubpages', 'ibosocial',
                        'identica', 'ifunny', 'imgur', 'inkonsky',
                        'instagram', 'instructables', 'intfiction',
                        'islamicawakening', 'issuu', 'ivoox', 'jamiiforums',
                        'kali', 'kanogames', 'keybase', 'kickstarter',
                        'kinja', 'kiwi', 'klout', 'kongregate', 'kupika',
                        'lastfm', 'leakforums', 'linkedin', 'livejournal',
                        'looki', 'losviajeros', 'marca', 'mastodonsocial',
                        'mastodonxyz', 'matchdoctor', 'mcneel', 'mediavida',
                        'medium', 'meneame', 'mercadolibre', 'metacafe',
                        'meteor', 'migente', 'minecraft', 'moneymaker',
                        'mozilla', 'musicasacra', 'myeloma', 'myfitnesspal',
                        'myspace', 'nairaland', 'netlog', 'netvibes',
                        'newgrounds', 'notabug', 'occupywallst',
                        'odnoklassniki', 'okcupid', 'onename',
                        'openbugbounty', 'openframeworks', 'openstreetmap',
                        'papaly', 'pastebin', 'patreon', 'pearltrees',
                        'periscope', 'phishtank', 'photobucket', 'pixinsight',
                        'pixls', 'pjrc', 'pokerred', 'pokerstrategy',
                        'pornhub', 'proboards', 'pz', 'qq',
                        'quartermoonsaloon', 'rankia', 'rapid-i', 'ratemypoo',
                        'realcarders', 'rebelmouse', 'reddit', 'redtube',
                        'researchgate', 'reverbnation', 'ripenear',
                        'rojadirecta', 'ruby', 'sarahah', 'scribd',
                        'seatwish', 'sencha', 'sidereel', 'singletrackworld',
                        'slashdot', 'slideshare', 'smartcitizen', 'smugmug',
                        'soundcloud', 'soup', 'sourceforge', 'spaniards',
                        'spoj', 'spotify', 'spreaker', 'squidoo',
                        'steamcommunity', 'steemit', 'steinberg',
                        'streakgaming', 'taringa', 'teamtreehouse',
                        'techcrunch', 'technorati', 'thehoodup', 'thesims',
                        'thestudentroom', 'theverge', 'thiscrush', 'tipme',
                        'tradimo', 'trakt', 'translate_hola', 'trulia',
                        'tumblr', 'tune', 'tuporno', 'twicsy', 'twitch',
                        'twitter', 'twoplustwo', 'typepad', 'unioncarder',
                        'ustream', 'v7n', 'venmo', 'vexforum', 'viddler',
                        'videohelp', 'vimeo', 'virustotal', 'vk',
                        'warriorforum', 'webtv', 'wikia', 'wikipedia',
                        'winamp', 'wishlistr', 'witty', 'wykop', 'xanga',
                        'xing', 'xtube', 'younow', 'youtube', 'zabbix',
                        'zentyal', 'zotero']. More than one option can be
                        selected.
  -t <tag> [< tag > ...], --tags < tag > [< tag > ...]
                        select the list of tags that fit the platforms in
                        which you want to perform the search. More than one
                        option can be selected.
  -x <platform> [< platform > ...], --exclude < platform > [< platform > ...]
                        select the platforms that you want to exclude from the
                        processing.
 
Processing arguments:
  Configuring the way in which usufy will process the identified profiles.
 
  --avoid_download      argument to force usufy NOT to store the downloadable
                        version of the profiles.
  --avoid_processing    argument to force usufy NOT to perform any processing
                        task with the valid profiles.
  --fuzz_config <path_to_fuzz_list>
                        path to the fuzzing config details. Wildcards such as
                        the domains or the nicknames should come as: <DOMAIN>,
                        <USERNAME>.
  --nonvalid <not_valid_characters>
                        string containing the characters considered as not
                        valid for nicknames.
  -e <sum_ext> [ < sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -L <path_to_log_folder, --logfolder <path_to_log_folder
                        path to the log folder. If none was provided, ./logs
                        is assumed.
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy will try to create; if
                        this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -w, --web_browser     opening the uris returned in the default web browser.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>.
  -T <num_threads>, --threads <num_threads>
                        write down the number of threads to be used (default
                        32). If 0, the maximum number possible will be used,
                        which may make the system feel unstable.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  -v <verbosity>, --verbose <verbosity>
                        select the verbosity level: 0 - none; 1 - normal
                        (default); 2 - debug.
  --version             shows the version of the program and exists.

````
## domainfy Help

domainfy - Checking the existence of domains.

usage: 
`````
domainfy 
                (--license | -n <nicks> [< nicks > ...] | -N <nicks_file>)
                [-e < sum_ext > [< sum_ext > ...]] [-o < path_to_output_folder >]
                [-t < tld_type > [< tld_type > ...]]
                [-u < new_tld > [< new_tld > ...]] [-x < domain > [< domain > ...]]
                [--whois] [-F < alternative_header_file >] [-T < num_threads >]
                [--quiet] [-h] [--version]
Input options (one required):
  --license             shows the GPLv3+ license and exists.
  -n <nicks> [< nicks > ...], --nicks < nicks > [< nicks > ...]
                        the list of nicks to be checked in the domains
                        selected.
  -N <nicks_file>, --nicks_file <nicks_file>
                        the file with the list of nicks to be checked in the
                        domains selected.
 
Processing arguments:
  Configuring the way in which mailfy will process the identified profiles.
 
  -e <sum_ext> [< sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy.py will try to create;
                        if this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -t <tld_type> [< tld_type > ...], --tlds < tld_type > [< tld_type > ...]
                        List of tld types where the nick will be looked for.
  -u <new_tld> [< new_tld > ...], --user_defined < new_tld > [< new_tld > ...]
                        Additional TLD that will be searched.
  -x <domain> [< domain > ...], --exclude < domain > [< domain > ...]
                        select the domains to be avoided. The format should
                        include the initial '.'.
  --whois               tells the program to launch whois queries.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>.
  -T <num_threads>, --threads <num_threads>
                        write down the number of threads to be used (default
                        16). If 0, the maximum number possible will be used,
                        which may make the system feel unstable.
  --quiet               tells the program not to show anything.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.
`````

## mailfy Help

mailfy.py - Checking the existence of a given mail.

usage: 
````
mailfy.py
                 (--license | -m <emails> [< emails > ...] | -M < emails_file > | -n < nicks > [< nicks > ...] | -N <nicks_file> | --create_emails <nicks_file>)
                 [-e < sum_ext > [< sum_ext > ...]]
                 [-d < candidate_domains > [< candidate_domains > ...]]
                 [-o < path_to_output_folder >] [-x < domain > [< domain > ...]]
                 [-F < alternative_header_file >] [-T < num_threads >]
                 [--is_leaked] [--quiet] [-h] [--version]


Input options (one required):
  --license             shows the GPLv3+ license and exists.
  -m <emails> [< emails > ...], --emails < emails > [< emails > ...]
                        the list of emails to be checked.
  -M <emails_file>, --emails_file <emails_file>
                        the file with the list of emails.
  -n <nicks> [< nicks > ...], --nicks < nicks > [< nicks > ...]
                        the list of nicks to be checked in the domains
                        selected.
  -N <nicks_file>, --nicks_file <nicks_file>
                        the file with the list of nicks to be checked in the
                        domains selected.
  --create_emails <nicks_file>
                        the file with the list of nicks to be created in the
                        domains selected.
 
Processing arguments:
  Configuring the way in which mailfy will process the identified profiles.
 
  -e <sum_ext> [ < sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -d <candidate_domains> [< candidate_domains > ...], --domains < candidate_domains > [< candidate_domains > ...]
                        list of domains where the nick will be looked for.
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy.py will try to create;
                        if this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -x <domain> [< domain > ...], --exclude < domain > [< domain > ...]
                        select the domains to be excluded from the search.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>.
  -T <num_threads>, --threads <num_threads>
                        write down the number of threads to be used (default
                        16). If 0, the maximum number possible will be used,
                        which may make the system feel unstable.
  --is_leaked           Defines whether mailfy.py should search for leaked
                        emails instead of verifying them.
  --quiet               tells the program not to show anything.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.
`````

# searchfy Help
searchfy.py - Piece of software that performs a query on the platforms in OSRFramework.

usage: 
````
searchfy.py (--license | -q <searches> [< searches > ...])
                   [-e < sum_ext > [< sum_ext > ...]]
                   [-F < alternative_header_file >] [-o < path_to_output_folder >]
                   [-p < platform > [< platform > ...]] [--process] [-w]
                   [-x < platform > [< platform > ...]] [-h] [--version]

Input options (one required):
  --license             shows the GPLv3+ license and exists.
  -q <searches> [< searches > ...], --queries < searches > [< searches > ...]
                        the list of queries to be performed).
 
Processing arguments:
  Configuring the way in which searchfy will process the identified
  profiles.
 
  -e <sum_ext> [< sum_ext > ...], --extension < sum_ext > [< sum_ext > ...]
                        output extension for the summary files. Default: xls.
  -F <alternative_header_file>, --file_header <alternative_header_file>
                        Header for the output filenames to be generated. If
                        None was provided the following will be used:
                        profiles.<extension>
  -o <path_to_output_folder>, --output_folder <path_to_output_folder>
                        output folder for the generated documents. While if
                        the paths does not exist, usufy.py will try to create;
                        if this argument is not provided, usufy will NOT write
                        any down any data. Check permissions if something goes
                        wrong.
  -p <platform> [< platform > ...], --platforms < platform > [< platform > ...]
                        select the platforms where you want to perform the
                        search amongst the following: ['all', 'facebook',
                        'github', 'pgpmit', 'twitter', 'youtube']. More than
                        one option can be selected.
  --process             whether to process the info in the profiles recovered.
                        NOTE: this would be much slower.
  -w, --web_browser     opening the URIs returned in the default web browser.
  -x <platform> [< platform > ...], --exclude < platform > [< platform > ...]
                        select the platforms that you want to exclude from the
                        processing.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help            shows this help and exists.
  --version             shows the version of the program and exists.

````

# osrframework_maltego Help

OSRFramework Server - The tool that will start a local server.

usage: 
````
osrframework_server [--host < ip >] [--port < port >] [--debug] [-h]
                           [--version]
Configuration arguments:
  Configuring the processing parameters.
 
  --host <IP>    choose the host in which the server will be accesible. If
                 "0.0.0.0" is choosen, the server will be accesible by any
                 remote machine. Use this carefully. Default: localhost.
  --port <PORT>  choose the port in which the server will be accesible. Use
                 this carefully.
  --debug        choose whether error messages will be deployed. Do NOT use
                 this for production.
 
About arguments:
  Showing additional information about this program.
 
  -h, --help     shows this help and exists.
  --version      shows the version of the program and exists.
````

## OSRFramework Usage Example
Check all top-level domains (-t all) for a registered name (-n hackware):

`domainfy.py -n hackware -t all`
Check where this e-mail address was used on the Internet (-m 'me@spryt.ru'):

`mailfy.py -m 'me@spryt.ru'`
Search by user name (-n kalilinux) for all available services:


`usufy.py -n kalilinux`
Search for an e-mail address with a given nickname (-n ltorvalds) in different mail services:


`mailfy.py -n ltorvalds`
Search for the specified string (-q "dookie2000ca") in 'facebook', 'github', 'pgpmit', 'skype', 'twitter', 'youtube':


`searchfy.py -q "dookie2000ca"`

## How to install OSRFramework

Installation on Kali Linux

`sudo apt install osrframework`

Installation on Linux (Debian, Mint, Ubuntu)


```sudo apt update
sudo apt install python-pip python-setuptools
sudo pip install --upgrade pip
sudo pip install osrframework
````

For the following update

`sudo pip install osrframework --upgrade`

## Other utils

Previous versions of OSRFramework included several useful utils that now have been moved to separate packages. The server, the console UI and the Maltego transforms are packaged separatedly so as to make it easier the maintenance of these utils. Thus, you can still install this packages with:

`sudo pip install osrframework_server osrframework_console osrframework_maltego --user`

# OSRFramework Screenshots


<img width="692" height="440" alt="image" src="https://github.com/user-attachments/assets/ef5756fd-fc80-4a34-b73f-4e914d14e17f" />
<img width="941" height="933" alt="image" src="https://github.com/user-attachments/assets/ea259eda-01be-4e9a-9594-c6bcf59c8410" />
<img width="615" height="937" alt="image" src="https://github.com/user-attachments/assets/21c11a56-d281-4b17-97a3-5dc30c0fff90" />

# OSRFramework Tutorials

Open source research with OSRFramework (search by mail, nickname, domain)
# Related tools

iptodomain (73.6%)

Maltego (71.7%)

trackerjacker (51.9%)

dnsenum (51.9%)

DNSRecon (51.9%)

NBTscan (RANDOM - 51.9%)
