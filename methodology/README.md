# Training Materials

This section includes onboarding content, lab exercises, and structured educational materials to improve red team skills.

## Training Tracks

### Beginner Track
- Intro to cybersecurity basics
- Linux command line fundamentals
- Networking basics and protocols
- Web application fundamentals
- Basic privilege escalation fundamentals
- Intro to adversary emulation

### Intermediate Track
- Python scripting for automation
- Active Directory basics
- PowerShell tradecraft
- Web exploitation fundamentals
- Lateral movement concepts
- Defense evasion techniques

### Advanced Track
- C2 infrastructure design
- EDR evasion and detection avoidance
- Cloud attack paths
- Kerberos exploitation
- Identity-based attacks
- Multi-step adversary emulation campaigns

---

## Lab Exercises

### Exercise 1: Reconnaissance
**Goal:** Discover subdomains, technologies, and public targets

**Tasks:**
- Perform DNS enumeration
- Identify exposed services
- Determine OS and versions
- Record findings in a structured report

### Exercise 2: Web Exploitation Basics
**Goal:** Identify and exploit common web vulnerabilities

**Tasks:**
- Fuzz parameters and endpoints
- Test for SQLi and XSS
- Validate impact and remediation path

### Exercise 3: Privilege Escalation
**Goal:** Escalate from standard account to admin/system access

**Tasks:**
- Enumerate local misconfigurations
- Review vulnerable binaries and services
- Validate root/system-level control

### Exercise 4: Active Directory Review
**Goal:** Explore domain trust and lateral movement paths

**Tasks:**
- Enumerate users and groups
- Test SMB and Kerberos paths
- Map privileged identities and trust boundaries

---

## Checklists

### Pre-Assessment Checklist
- [ ] Authorization and ROE reviewed
- [ ] Scope boundaries confirmed
- [ ] Stakeholder notifications sent
- [ ] Communication plan documented
- [ ] Lab environment ready
- [ ] Data handling and retention requirements known

### Post-Assessment Checklist
- [ ] Evidence collection complete
- [ ] Findings validated
- [ ] Remediation recommendations documented
- [ ] Detection suggestions recorded
- [ ] Executive summary prepared
- [ ] Cleanup performed for test artifacts

---

## Suggested Tools for Training

- Kali Linux / Parrot OS
- Burp Suite
- Nmap
- Metasploit
- PowerShell
- Python
- Wireshark
- DVWA / WebGoat
- HackTheBox / TryHackMe
- BloodHound (for AD-focused labs)

---

## Practical Guidance

- Always practice in isolated environments
- Keep notes of commands and outcomes
- Validate each step before progressing
- Review detection and mitigations after exploitation
- Focus on red team realism rather than noise

---

**Last Updated:** 2026


# Threat Modeling

Threat modeling helps identify weaknesses, attack paths, and strategic defenses before or during testing.

## Core Threat Modeling Methods

### STRIDE
- **S**poofing
- **T**ampering
- **R**epudiation
- **I**nformation Disclosure
- **D**enial of Service
- **E**levation of Privilege

### Attack Trees
Visual representation of paths an adversary may use to achieve a goal.

### Kill Chain Analysis
Maps the sequence of actions from reconnaissance through impact.

### MITRE ATT&CK Mapping
Maps observed techniques to known adversary behavior patterns.

---

## Threat Modeling Process

1. Define assets and trust boundaries
2. Identify actors and likely adversaries
3. Analyze threats and attack paths
4. Rank risk based on impact and likelihood
5. Prioritize mitigations and controls
6. Revalidate the model during changes or new releases

---

## Example Threat Model

**Asset:** Internal employee portal  
**Adversary:** External attacker with moderate capabilities  
**Primary risks:**
- SQL injection in public application
- Session hijacking via insecure cookies
- Weak MFA enforcement on admin accounts
- Insufficient network segmentation between DMZ and internal apps

**Attack Path:**
- Internet-facing portal -> credential theft -> lateral movement -> admin workstation -> data access

**Controls to add:**
- WAF and input validation
- Hardened cookie configuration
- MFA on all privileged accounts
- Enforced segmentation and logging

---

## Red Team Relevance

Threat modeling guides offensive activity by:
- Highlighting likely entry points
- Identifying valuable targets and high-impact assets
- Supporting realistic operation design
- Aligning security testing to risk and priorities

---

## Documentation Checklist

- [ ] Asset inventory
- [ ] Trust boundaries
- [ ] Threat actors and goals
- [ ] Attack paths and dependencies
- [ ] Mitigation recommendations
- [ ] Residual risk statement

---

**Last Updated:** 2026
