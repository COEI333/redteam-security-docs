# Red Team Methodology & Engagement Frameworks

Structured approaches and playbooks for conducting authorized red team security assessments.

---

## 1. NIST Cybersecurity Framework for Red Teams

### Engagement Phases

#### Phase 1: Planning & Scoping
**Duration:** 1-2 weeks

**Activities:**
- Define assessment objectives
- Identify target systems and scope
- Determine testing methods
- Establish success criteria
- Document assumptions and constraints

**Deliverables:**
- Scope of Work (SOW)
- Rules of Engagement (ROE)
- Risk Assessment Matrix
- Timeline and Resource Plan

**Key Questions:**
- What systems are in scope?
- What attacks are authorized?
- What's the impact tolerance?
- Who are the key stakeholders?
- What's the success metric?

---

#### Phase 2: Reconnaissance
**Duration:** 1-3 weeks
**Objective:** Gather passive intelligence about targets

**Activities:**
- OSINT collection
- Domain enumeration
- Email harvesting
- Technology stack identification
- Employee profiling
- Physical location reconnaissance
- Public data analysis

**Tools:**
- Shodan, TheHarvester, DNSRecon, Whois
- LinkedIn, Google Dorks
- GitHub repositories
- Job postings analysis

**Deliverables:**
- Target organization profile
- Technology inventory
- Personnel directory
- Physical security assessment
- Digital footprint report

---

#### Phase 3: Scanning & Enumeration
**Duration:** 1-2 weeks
**Objective:** Active discovery of systems and services

**Activities:**
- Network scanning (Nmap)
- Vulnerability scanning (Nessus, OpenVAS)
- Web application scanning (Burp Suite)
- DNS enumeration
- Service version detection
- OS fingerprinting
- Port enumeration

**Tools:**
- Nmap, Masscan, Shodan
- Nessus, OpenVAS, Qualys
- Burp Suite, OWASP ZAP
- Nikto

**Deliverables:**
- Network map
- Service inventory
- Vulnerability list (preliminary)
- Technology stack documentation
- Exploitable services analysis

---

#### Phase 4: Exploitation
**Duration:** 2-4 weeks
**Objective:** Compromise target systems

**Activities:**
- Initial access attempts
- Vulnerability exploitation
- Payload delivery
- Privilege escalation
- Post-exploitation activities
- Lateral movement
- Persistence establishment

**Tools:**
- Metasploit, Cobalt Strike
- SQLmap, BeEF, Burp Suite
- Custom exploits
- Living-off-the-land techniques

**Documentation:**
- Exploitation timeline
- Command logs
- Evidence collection
- System access proof

---

#### Phase 5: Post-Exploitation
**Duration:** 1-3 weeks
**Objective:** Maximize access and demonstrate impact

**Activities:**
- Credential dumping
- Lateral movement
- Persistence mechanisms
- Data collection
- Privilege escalation to domain admin
- Sensitive data access
- Business impact demonstration

**Tools:**
- Mimikatz, CrackMapExec
- Responder, Impacket
- Empire, PowerShell
- WinRM, RDP

**Deliverables:**
- Access chain documentation
- Credential inventory
- Sensitive data accessed
- Business impact assessment

---

#### Phase 6: Reporting & Remediation
**Duration:** 1-2 weeks
**Objective:** Communicate findings and support remediation

**Report Contents:**
- Executive Summary
- Detailed Findings
- Technical Details
- Risk Assessment
- Remediation Recommendations
- Timeline for Fixes
- Lessons Learned

**Deliverables:**
- Final Assessment Report
- Vulnerability List with CVSS Scores
- Remediation Roadmap
- Lessons Learned Document
- Post-Assessment Debriefing

---

## 2. PTES (Penetration Testing Execution Standard)

### Kill Chain Model

```
┌──────────────────────────────────────────────────────────┐
│                    KILL CHAIN PHASES                     │
├──────────────────────────────────────────────────────────┤
│ 1. Reconnaissance      │ Gather intelligence               │
│ 2. Weaponization      │ Create attack tools               │
│ 3. Delivery            │ Get payload to target            │
│ 4. Exploitation       │ Execute attack code               │
│ 5. Installation        │ Install persistence              │
│ 6. Command & Control   │ Establish communication          │
│ 7. Actions on Objectives │ Execute mission               │
└──────────────────────────────────────────────────────────┘
```

---

## 3. Rules of Engagement (ROE) Template

### Must-Include Elements

```
1. AUTHORIZATION
   - Written approval required
   - Scope boundaries defined
   - Approved systems list
   - Restrictions on testing

2. TESTING METHODS
   - Allowed attack vectors
   - Social engineering approval
   - Physical testing approval
   - Prohibited techniques

3. BOUNDARIES
   - In-scope systems
   - Out-of-scope systems
   - Geographic boundaries
   - Time windows for testing
   - Business hours considerations

4. COMMUNICATIONS
   - Emergency contact information
   - Escalation procedures
   - Status reporting frequency
   - Issue notification process
   - Incident response coordination

5. DATA HANDLING
   - Sensitive data protection
   - Credential storage
   - Evidence preservation
   - Data destruction requirements

6. LEGAL & LIABILITY
   - Liability limitations
   - Insurance requirements
   - Legal jurisdiction
   - Compliance requirements
   - NDA terms
```

---

## 4. Assessment Timeline Example

### Week-by-Week Breakdown

**Week 1: Planning & Reconnaissance**
- Day 1-2: Requirements gathering
- Day 3-5: OSINT and passive reconnaissance
- Day 5: Team meeting and findings review

**Week 2-3: Active Scanning**
- Day 1-3: Network scanning and enumeration
- Day 3-4: Vulnerability scanning
- Day 5: Analysis and prioritization

**Week 4-6: Exploitation**
- Day 1-4: Initial access attempts
- Day 5: Privilege escalation
- Day 1-3 (next week): Lateral movement
- Day 4-5: Post-exploitation

**Week 7-8: Reporting**
- Day 1-3: Report writing
- Day 4: Review and validation
- Day 5: Client presentation

---

## 5. Escalation Procedures

### Incident Escalation Matrix

```
SEVERITY LEVEL    RESPONSE TIME    NOTIFICATION    ACTION
─────────────────────────────────────────────────────────────
Critical          Immediate        Phone call       Stop testing
                                   Text message    

High              1 hour          Email           Notify client
                                  Phone call      Get approval

Medium            4 hours         Email           Document
                                                  Continue if approved

Low               End of day       Email           Log for report
```

### Incident Response Contacts
- Primary contact: [Name]
- Backup contact: [Name]
- Security team: [Contact info]
- Executive sponsor: [Contact info]
- Legal: [Contact info]

---

## 6. Evasion & Detection Avoidance Strategy

### Operational Security (OPSEC) Checklist

- [ ] Use VPN/proxy for all connections
- [ ] Rotate source IPs
- [ ] Randomize timing of activities
- [ ] Vary attack patterns
- [ ] Use legitimate credentials when available
- [ ] Leverage living-off-the-land binaries
- [ ] Minimize malware signatures
- [ ] Avoid known malicious IPs
- [ ] Monitor for detection indicators
- [ ] Have exit strategy prepared

---

## 7. Documentation Standards

### Command Logging Template

```
[TIMESTAMP] [SYSTEM] [COMMAND] [OUTPUT]
2026-09-30 10:15:23 192.168.1.100 whoami DOMAIN\administrator
2026-09-30 10:16:05 192.168.1.100 ipconfig Configuration details...
```

### Screenshot Naming Convention
```
[Phase]_[SystemIP]_[Function]_[Timestamp].png
Exploit_192.168.1.100_ReverseShell_20260930_101523.png
PostEx_192.168.1.100_CredDump_20260930_102145.png
```

---

## 8. Risk Assessment & Reporting

### CVSS Score Interpretation

```
CVSS 0.0          Information
CVSS 0.1-3.9      Low
CVSS 4.0-6.9      Medium
CVSS 7.0-8.9      High
CVSS 9.0-10.0     Critical
```

### Risk Rating Matrix

```
              LIKELIHOOD
         Low    Medium    High
I   High   M      H       C
m   Med    L      M       H
p   Low    L      L       M
act
```

---

## 9. Team Roles & Responsibilities

**Team Lead:**
- Overall assessment coordination
- Client communication
- Risk management
- Report compilation

**Penetration Testers:**
- Technical assessment execution
- Exploitation and post-exploitation
- Evidence documentation
- Finding validation

**Social Engineers:**
- Phishing campaigns
- Pretexting
- Physical testing
- Security awareness evaluation

**Report Writer:**
- Documentation compilation
- Finding validation
- Remediation guidance
- Executive summary preparation

---

## 10. Post-Assessment Activities

### Client Debriefing
- [ ] Present findings overview
- [ ] Discuss critical vulnerabilities
- [ ] Explain exploitation chain
- [ ] Answer technical questions
- [ ] Discuss remediation priority
- [ ] Schedule follow-up assessment

### Remediation Verification
- [ ] Validate fixes applied
- [ ] Retest critical findings
- [ ] Document remediation success
- [ ] Provide verification report
- [ ] Schedule re-assessment

---

## 11. Quality Assurance Checklist

- [ ] All findings validated
- [ ] Screenshots collected
- [ ] Commands documented
- [ ] Timeline documented
- [ ] CVSS scores accurate
- [ ] Remediation guidance clear
- [ ] Report proofread
- [ ] No sensitive data exposed
- [ ] Executive summary ready
- [ ] Client approves findings

---

## 12. Lessons Learned Template

**What went well:**
- Quick initial access
- Effective lateral movement

**What could be improved:**
- Detection avoidance techniques
- Tool optimization
- Time management

**Recommendations for future assessments:**
- Different approach for this scenario
- Tool recommendations
- Team structure adjustments

---

**Last Updated:** 2026  
**Maintained by:** Red Team Documentation
