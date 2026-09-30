# Threat Modeling & Adversary Emulation

Frameworks for identifying threats, modeling attacks, and emulating adversary TTPs.

---

## 1. Threat Actor Profiles

### Profile 1: Opportunistic Cybercriminals
**Capability Level:** Low to Medium  
**Motivation:** Financial gain  
**Sophistication:** Limited

**Typical Attacks:**
- Phishing for credentials
- Brute force attacks
- SQL injection
- Website defacement
- Ransomware deployment

**Indicators:**
- High volume of attacks
- Common vulnerabilities targeted
- Minimal stealth
- Script-based tools

**Mitigation:**
- Basic security controls
- User awareness training
- Patch management
- Multi-factor authentication

---

### Profile 2: Organized Crime Syndicate
**Capability Level:** High  
**Motivation:** Financial/Data theft  
**Sophistication:** Moderate-High

**Typical Attacks:**
- Targeted phishing campaigns
- Credential harvesting
- Lateral movement
- Data exfiltration
- Ransomware with negotiation

**Indicators:**
- Targeted reconnaissance
- Persistence mechanisms
- Data staging
- Ransom demands

**Mitigation:**
- Network segmentation
- EDR deployment
- Incident response plan
- Data encryption

---

### Profile 3: Nation-State APT
**Capability Level:** Very High  
**Motivation:** Espionage/Sabotage  
**Sophistication:** Very High

**Typical Attacks:**
- Supply chain compromise
- Zero-day exploitation
- Advanced persistence
- Sophisticated C2 channels
- Long-term presence

**Indicators:**
- Targeted spear-phishing
- Custom malware
- Multi-stage attacks
- Living-off-the-land techniques
- Operational security excellence

**Mitigation:**
- Advanced monitoring
- Threat intelligence
- Incident response
- Security culture

---

## 2. STRIDE Threat Modeling

### Threat Categories

```
S - Spoofing           Impersonating a user/system
T - Tampering          Modifying data or system state
R - Repudiation        Denying actions taken
I - Information Disclosure   Unauthorized data access
D - Denial of Service  Preventing legitimate use
E - Elevation of Privilege   Gaining unauthorized access
```

### Example: Web Application STRIDE Analysis

**Component:** User Login Form

**Threats:**
1. **Spoofing:**
   - Username impersonation
   - Email spoofing
   - Session hijacking
   
   **Mitigation:**
   - Account verification
   - HTTPS enforcement
   - Secure session management

2. **Tampering:**
   - Password modification
   - Login request manipulation
   - Cookie modification
   
   **Mitigation:**
   - Input validation
   - Signed cookies
   - Secure hashing

3. **Repudiation:**
   - User denies login
   - Deny changing password
   
   **Mitigation:**
   - Detailed logging
   - Audit trails
   - Digital signatures

4. **Information Disclosure:**
   - Password interception
   - Session token theft
   - Username enumeration
   
   **Mitigation:**
   - HTTPS/TLS
   - Secure token storage
   - Generic error messages

5. **Denial of Service:**
   - Brute force attacks
   - Account lockout abuse
   - Credential stuffing
   
   **Mitigation:**
   - Rate limiting
   - Account lockout policy
   - CAPTCHA
   - Anomaly detection

6. **Elevation of Privilege:**
   - Privilege escalation
   - Role manipulation
   - Admin bypass
   
   **Mitigation:**
   - Principle of least privilege
   - Access control enforcement
   - Admin verification

---

## 3. Attack Tree Analysis

### Example: Compromise Executive Email Account

```
                    Compromise Executive Email
                              |
                 _____________|_____________
                |             |             |
             Phishing    Credential    Insider
             Attack      Theft         Threat
                |
      __________|__________
     |                     |
  Click Link         Credential Harvesting
     |                     |
  ___| ___                _|_
 |       |              |    |
 JS    Malware      Fake   Replay
 Code              Page    Attack

Success: Access to executive inbox -> Lateral movement -> Data theft
```

---

## 4. Kill Chain Analysis

### Lockheed Martin Kill Chain Mapping

**Step 1: Reconnaissance**
- Target identification
- Employee profiling
- Technology assessment
- Vulnerability research

**Detection Indicators:**
- OSINT tool usage
- Scanning activities
- Domain queries
- Social media profiling

**Mitigation:**
- Security awareness training
- Threat intelligence
- Network monitoring

---

**Step 2: Weaponization**
- Exploit development
- Payload creation
- Tool development
- Delivery mechanism preparation

**Detection Indicators:**
- Malware development
- Proof-of-concept creation
- Tool compilation

**Mitigation:**
- EDR (Endpoint Detection & Response)
- Behavioral analysis
- Signature detection

---

**Step 3: Delivery**
- Email delivery
- Website compromise
- USB/Physical delivery
- Supply chain injection

**Detection Indicators:**
- Phishing emails
- Malicious URLs
- Suspicious attachments
- DNS requests to malicious sites

**Mitigation:**
- Email filtering
- URL reputational checking
- DKIM/SPF/DMARC
- Endpoint detection

---

**Step 4: Exploitation**
- Vulnerability trigger
- Exploit execution
- Payload installation
- Initial code execution

**Detection Indicators:**
- Abnormal process behavior
- System calls anomalies
- File system changes
- Memory access patterns

**Mitigation:**
- Patch management
- Application whitelisting
- Behavioral analysis
- Memory protection

---

**Step 5: Installation**
- Backdoor installation
- Persistence mechanism
- Rootkit deployment
- Service creation

**Detection Indicators:**
- Registry changes
- Startup folder modifications
- Scheduled tasks creation
- Service installation
- Boot sector modifications

**Mitigation:**
- File integrity monitoring
- Registry monitoring
- Host-based IDS
- EDR tools

---

**Step 6: Command & Control**
- C2 channel establishment
- Beaconing
- Remote access
- Command execution

**Detection Indicators:**
- Unusual network traffic
- DNS queries to DGA domains
- Outbound connections to unknown IPs
- Protocol anomalies
- Data exfiltration patterns

**Mitigation:**
- Network monitoring
- Firewall rules
- DNS filtering
- Proxy logging
- Network segmentation

---

**Step 7: Actions on Objectives**
- Data exfiltration
- Privilege escalation
- Lateral movement
- System destruction
- Ransom deployment

**Detection Indicators:**
- Large data transfers
- File encryption
- User account creation
- Administrative access
- Mass file deletion

**Mitigation:**
- Data loss prevention (DLP)
- Access controls
- Data classification
- Backup and recovery
- Incident response

---

## 5. Adversary Emulation Scenarios

### Scenario: Simulated APT Campaign

**Duration:** 2 weeks  
**Team Size:** 3-5 red teamers  
**Objective:** Test detection and response capabilities

**Phase 1: Reconnaissance (Days 1-2)**
- OSINT on organization
- Employee targeting
- Technology discovery
- Vulnerability research

**Phase 2: Weaponization & Delivery (Days 3-4)**
- Phishing campaign creation
- Landing page development
- Payload preparation
- Email deployment

**Phase 3: Initial Compromise (Days 5-6)**
- Phishing link clicks
- Credential harvesting
- Low-privilege shell access
- Beacon establishment

**Phase 4: Expansion (Days 7-10)**
- Credential theft via keylogging
- Privilege escalation
- Lateral movement to critical systems
- Persistence establishment

**Phase 5: Objectives (Days 11-14)**
- Sensitive data access
- Data staging
- C2 stabilization
- Exfiltration initiation
- Blue team response

---

## 6. Risk Assessment Using Threat Modeling

### Risk Calculation

```
Risk = Threat Likelihood × Vulnerability Severity × Asset Value

Example:
Threat: APT targeting financial data
Likelihood: 0.6 (High)
Vulnerability: Unpatched RCE
Severity: 0.9 (Critical)
Asset Value: $10M (customer data)

Risk = 0.6 × 0.9 × $10M = $5.4M
```

---

## 7. Threat Intelligence Integration

### Sources
- CVE Databases
- Dark web monitoring
- Vendor advisories
- Industry reports
- Competitor analysis
- Dark web forums

### Application
- Prioritize vulnerability patching
- Adjust detection rules
- Update security policies
- Target red team exercises
- Inform incident response

---

## 8. Adversary Technique Mapping (MITRE ATT&CK)

### Mapping Example: Phishing Campaign

**Initial Access (TA0001)**
- T1566: Phishing
  - T1566.001: Phishing: Spearphishing Attachment
  - T1566.002: Phishing: Spearphishing Link

**Execution (TA0002)**
- T1204: User Execution
- T1059: Command and Scripting Interpreter

**Persistence (TA0003)**
- T1547.001: Registry Run Keys / Start Folder
- T1547.004: Winlogon Helper DLL

**Privilege Escalation (TA0004)**
- T1548.002: Abuse Elevation Control Mechanism: Bypass User Account Control

**Defense Evasion (TA0005)**
- T1140: Deobfuscate/Decode Files or Information
- T1036: Masquerading

---

## 9. Defensive Measures Mapping

### For Each Phase of Kill Chain

| Phase | Detection | Prevention | Response |
|-------|-----------|------------|----------|
| Reconnaissance | Threat intel, OSINT monitoring | Limited | Investigate |
| Weaponization | Endpoint tools | Code signing | Block |
| Delivery | Email filtering, DNS filtering | MX records, DNS | Quarantine |
| Exploitation | EDR, behavioral analysis | Patching, WAF | Isolate |
| Installation | File monitoring, registry | Whitelisting | Remove |
| Command & Control | Network monitoring, DNS | Firewall, proxy | Block, sinkhole |
| Actions on Objectives | DLP, audit logs | Access controls | Respond, recover |

---

**Last Updated:** 2026  
**Maintained by:** Red Team Documentation
