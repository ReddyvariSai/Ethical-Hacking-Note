# Harvester

The Harvester is a powerful, Python-based `Open-Source Intelligence (OSINT)` tool designed for the early stages of a penetration test or web reconnaissance.

It is used to gather a wide variety of information about a target domain from public sources, allowing a researcher to map out a company's external perimeter and human targets without directly interacting with the organization's infrastructure.

<img width="1126" height="352" alt="image" src="https://github.com/user-attachments/assets/21da7921-ec21-42ab-9d25-ea850e7c8fe4" />

<img width="1137" height="692" alt="image" src="https://github.com/user-attachments/assets/608f6c71-5000-40c2-8f9e-c6d65d023a59" />

## How the Harvester Works

The Harvester functions by querying `diverse public data sources` and aggregating the results into a single view. Its primary mechanisms include:

• Source Aggregation:- It scours search engines (like DuckDuckGo or Bing), PGP key servers, and specialized databases to find "traces" left behind by the target.

• Data Extraction:- It specifically looks for email addresses, subdomains, hostnames, employee names, open ports, and banners.

• Database Integration:- It can interact with powerful third-party databases like Shodan and VirusTotal to discover internet-facing devices (IoT), servers, and historical security data.


<img width="1138" height="773" alt="Screenshot 2026-01-04 133510" src="https://github.com/user-attachments/assets/44d4eb9c-a8e5-4d5e-9179-34ad43d7252f" />

<img width="1135" height="767" alt="Screenshot 2026-01-04 133542" src="https://github.com/user-attachments/assets/bfcd21e4-d9a5-48ac-8014-9c44b1def504" />


<img width="1139" height="751" alt="Screenshot 2026-01-04 133607" src="https://github.com/user-attachments/assets/31f5e00d-f658-406d-ab40-1f698f4dcf42" />

<img width="1076" height="700" alt="Screenshot 2026-01-04 133636" src="https://github.com/user-attachments/assets/fffbbad9-9368-4d81-9459-19db2fc81937" />

## Configuration and API Keys

While the Harvester can perform basic searches using public engines, it requires API keys to unlock its full potential for deeper research.

1. Obtaining Keys:- A user must create accounts on platforms like Shodan or VirusTotal to generate a unique API key, which identifies their client application to the website.

2. Editing the Config:- In environments like Kali Linux, these keys are stored in a configuration file located at /etc/theHarvester/api-keys.yaml.

3. Root Privileges:- Because this is a system file, it must be edited using root privileges (e.g., using sudo nano or sudo mousepad).

4. Formatting:- When adding the key to the .yaml file, it is crucial to add a space after the colon before pasting the key string (e.g., shodan: <key>).

## Usage and Common Commands

The tool is operated via the command line. A typical query structure looks like this:

`theHarvester -d [domain] -l [limit] -b [source]`
### Key Flags and Examples:

• -d (Domain): Specifies the target domain (e.g., -d eccouncil.org).

• -l (Limit): Restricts the number of results to search through (e.g., -l 500).

• -b (Source): Defines the engine to use, such as duckduckgo, bing, or google.

• -s (Shodan): Enables a search of the Shodan database for IoT devices and open ports.

• -f (File): Outputs the findings to a file, typically saving both XML and JSON formats.

## Analyzing the Results

The Harvester's console output is often more detailed than its exported files.

For example, while the console might show specific open ports and server details found via Shodan, the exported XML file might only list the discovered hostnames and IP addresses.

### Analogy:

Using the Harvester is like being a digital private investigator who, instead of hacking into a building, spends their time in the public library and records office.

By cross-referencing phone books (DNS), business directories (Shodan), and public employee listings (LinkedIn/PGP), they can map out the entire "corporate office" and its staff without ever setting foot on the property.


