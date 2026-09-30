# Red Team Methodology Framework

## Overview

This framework provides a structured approach to red team assessments, including planning, execution, validation, and reporting.

## Engagement Lifecycle

### Phase 1: Planning & Preparation

**Objectives:**
- Define scope and goals
- Establish rules of engagement
- Identify target systems and stakeholders
- Confirm time windows and asset boundaries
- Review legal and compliance constraints

**Required Activities:**
- Kickoff meeting
- Asset inventory review
- Threat model creation
- Team assignment and roles
- Communication plan
- Escalation paths

**Deliverables:**
- Scope document
- Rules of engagement
- Threat matrix
- Work plan
- Roles and responsibilities

---

### Phase 2: Reconnaissance

**Objectives:**
- Identify internet-facing assets
- Discover attack surface
- Gather intel on target environment
- Validate system architecture

**Focus Areas:**
- Domain records and subdomains
- Public services and technologies
- Employee and organization profiles
- Cloud footprints
- Third-party dependencies

**Key Techniques:**
- OSINT data collection
- DNS enumeration
- Subdomain discovery
- Technology profiling
- Asset prioritization

---

### Phase 3: Initial Access & Foothold

**Objectives:**
- Gain initial access
- Identify exploitable pathways
- Validate persistence opportunities

**Possible Paths:**
- Web vulnerabilities
- User credential abuse
- Supply chain weaknesses
- Misconfigured external services
- Social engineering vectors

**Validation Criteria:**
- Achieved foothold in target environment
- Access is stable and controlled
- Permissions are understood
- Activity is sufficiently isolated

---

### Phase 4: Lateral Movement & Privilege Escalation

**Objectives:**
- Move deeper into the environment
- Learn trust relationships
- Escalate access to high-value systems
- Determine paths to sensitive assets

**Priority Areas:**
- Domain controllers
- Admin workstations
- Cloud admin consoles
- Database systems
- Key management services

**Techniques:**
- Credential dumping
- Pass-the-hash
- Kerberoasting
- SMB exploitation
- Token impersonation
- Service abuse

---

### Phase 5: Persistence & Defense Evasion

**Objectives:**
- Maintain access without detection
- Validate adversary durability
- Measure detection gaps

**Common Approaches:**
- Scheduled tasks
- Registry autostart
- WMI persistence
- Hidden services
- Web shells
- Legitimate tooling abuse

**Considerations:**
- Detection evasion
- Operating system coverage
- recovery and cleanup strategy

---

### Phase 6: Collection & Exfiltration

**Objectives:**
- Identify sensitive data stores
- Access critical information
- Evaluate exfiltration paths

**Examples:**
- Database extraction
- File share data access
- Email archive collection
- Cloud object enumeration
- Browser secrets and tokens

**Validation Criteria:**
- Data is relevant and sensitive
- Access path is realistic
- Impact is measurable
- Defense controls are tested

---

### Phase 7: Reporting & Remediation Guidance

**Required Outputs:**
- Executive summary
- Technical findings
- Attack paths and narratives
- Risk ratings
- Detection gaps
- Recommended remediations

**Report Structure:**
1. Scope and methodology
2. Executive summary
3. Detailed findings
4. Attack chain overview
5. Risk scoring results
6. Remediation recommendations
7. Lessons learned and next steps

---

## Framework Principles

- **Least intrusion:** Do not exceed authorized scope
- **Evidence-based findings:** Validate all conclusions
- **Tactical realism:** Simulate realistic adversary tradecraft
- **Clear reporting:** Communicate risks in business context
- **Defensive value:** Prioritize findings that improve detection and prevention

---

## Roles & Responsibilities

### Red Team Lead
- Coordinates engagement
- Ensures scope and safety
- Reviews findings and risk prioritization

### Operator / Tester
- Executes techniques within scope
- Documents results and evidence
- Maintains session notes

### Threat Hunter / Defender Liaison
- Maps findings to detection opportunities
- Identifies gaps in telemetry and control coverage

### Reporting Analyst
- Produces final deliverables
- Converts technical findings into actionable recommendations

---

## Rules of Engagement (ROE)

A good ROE should define:
- In-scope assets and systems
- Methods allowed and prohibited
- Time windows and blackout periods
- Data handling and storage expectations
- Communication escalation procedures
- Password and credential usage rules
- Safety and containment requirements

---

## Risk Scoring

Common approaches include:
- CVSS for individual vulnerabilities
- Business impact for data or service sensitivity
- Attacker path complexity and likelihood
- Detection and remediation difficulty

---

## Attack Path Documentation Template

```text
1. Initial access from internet-facing web application
2. Credential harvesting from session cookies
3. Lateral movement via SMB and domain admin access
4. Privilege escalation to local system and service account
5. Sensitive data collection from file servers
6. Exfiltration through HTTPS tunnel to external endpoint
7. Persistence using scheduled task to maintain access
```

---

## Recommended Controls to Validate

- MFA for privileged access
- Endpoint detection and response (EDR)
- Network segmentation
- Least-privilege access controls
- Logging and alerting coverage
- Application hardening
- Cloud security posture validation

---

**Last Updated:** 2026
