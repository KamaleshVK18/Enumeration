## NAME: Kamalesh Vijayakumar V
## REG. NO.: 212224110028


# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
SITE:
<img width="951" height="1016" alt="image" src="https://github.com/user-attachments/assets/c316f8cc-8859-4a46-8815-998b64d58398" />


INURL:
<img width="1837" height="991" alt="image" src="https://github.com/user-attachments/assets/78fb537a-2f19-406d-8d39-8ce94a554465" />

INTITLE:
<img width="953" height="671" alt="image" src="https://github.com/user-attachments/assets/c354fba4-35ed-4539-a1eb-486833b5877b" />

FILETYPE.PDF
<img width="949" height="998" alt="image" src="https://github.com/user-attachments/assets/fb79d3d5-146f-4ec9-aec1-e1980d0fcc9f" />



INTEXT:
<img width="956" height="977" alt="image" src="https://github.com/user-attachments/assets/d3a5cea9-6789-44cf-b77b-88271ebf08c4" />


LINK:
<img width="949" height="894" alt="image" src="https://github.com/user-attachments/assets/8a783ee6-8d60-47ad-b854-7ed966f9a14c" />

CACHE:
<img width="957" height="1014" alt="image" src="https://github.com/user-attachments/assets/f1f8760a-50b3-4d38-9c94-9ca77eabefd4" />

---

## Explanation of Google Dork Operators

### `site:example.com`
**Explanation:** Restricts search results to a specific domain.  
**Purpose:** Helps find all indexed pages and possible exposed content.

### `inurl:admin`
**Explanation:** Searches URLs containing specific keywords.  
**Purpose:** Useful for finding admin panels or login pages.

### `intitle:"index of"`
**Explanation:** Searches for keywords in page titles.  
**Purpose:** Helps identify open directories.

### `filetype:pdf`
**Explanation:** Filters results by file type.  
**Purpose:** Used to find downloadable documents.

### `intext:"confidential"`
**Explanation:** Searches for keywords inside page content.  
**Purpose:** Helps detect sensitive information.

### `link:example.com`
**Explanation:** Shows pages linking to a domain.  
**Purpose:** Useful for backlink analysis.

### `cache:example.com`
**Explanation:** Displays cached version of a page.  
**Purpose:** Helps view removed or unavailable content.


---


## DNS Recon

| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

### NSLOOKUP:
<img width="692" height="542" alt="image" src="https://github.com/user-attachments/assets/db297880-6a49-450e-b081-a9e767205aa6" />



### DIG:
<img width="702" height="453" alt="image" src="https://github.com/user-attachments/assets/61691d25-48c7-4faf-9e9c-dec22eebc781" />


### HOST:
<img width="712" height="354" alt="image" src="https://github.com/user-attachments/assets/5e3c197f-91be-4da6-a166-54d1f6216316" />


### DNSENUM:
<img width="712" height="214" alt="image" src="https://github.com/user-attachments/assets/fa25bb4b-7e34-44b2-9c2d-290c0d7c7ea7" />




### FIERCE:
<img width="785" height="858" alt="Screenshot 2025-08-30 155317" src="https://github.com/user-attachments/assets/a6a67848-6a35-4a7c-8ffc-3bc41a01b97c" />


### theHarvester:
<img width="887" height="818" alt="image" src="https://github.com/user-attachments/assets/e1f7f5b3-ee0d-4711-9b5e-b9826d645e27" />


## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:
<img width="712" height="214" alt="image" src="https://github.com/user-attachments/assets/fa25bb4b-7e34-44b2-9c2d-290c0d7c7ea7" />



## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```

## Explanation of DNS Tools

### `nslookup example.com`
**Explanation:** Queries DNS to get IP address info.  
**Purpose:** Basic DNS lookup and troubleshooting.

### `dig example.com any`
**Explanation:** Provides detailed DNS records.  
**Purpose:** Used for advanced DNS analysis.

### `host example.com`
**Explanation:** Resolves domain to IP quickly.  
**Purpose:** Simple DNS checking tool.

### `dnsenum example.com`
**Explanation:** Automates DNS enumeration.  
**Purpose:** Finds subdomains and performs zone transfers.

### `fierce -dns example.com`
**Explanation:** Scans DNS for hidden subdomains.  
**Purpose:** Helps discover network infrastructure.

### `theHarvester -d example.com -b google`
**Explanation:** Collects emails and subdomains from public sources.  
**Purpose:** Used for OSINT reconnaissance.
 ## Output
<img width="938" height="525" alt="image" src="https://github.com/user-attachments/assets/965af7ce-4f58-444f-b19d-b892306a4e7b" />



## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```

##  SMTP Enumeration Commands Explanation

### `dnsenum example.com`
**Explanation:** Enumerates DNS records and subdomains.  
**Purpose:** Helps understand domain structure.

### `smtp-user-enum -M VRFY -U users.txt -t <target-ip>`
**Explanation:** Uses SMTP commands to verify users.  
**Purpose:** Identifies valid email accounts.

### `nmap -p 25 --script smtp-enum-users.nse <target-ip>`
**Explanation:** Uses Nmap script to enumerate SMTP users.  
**Purpose:** Automates email account discovery.
## OUTPUT:

<img width="904" height="174" alt="image" src="https://github.com/user-attachments/assets/4f28211b-3a1a-4ee5-8c06-246fbbbd45b9" />


## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
