# Attack Techniques & TTPs

This section documents tactics, techniques, and procedures (TTPs) aligned with the MITRE ATT&CK framework. Each technique includes real-world examples, detection methods, and mitigation strategies.

## MITRE ATT&CK Framework Categories

### 1. Reconnaissance (TA0043)
Gathering information about targets without direct interaction.

**Key Techniques:**
- T1590: Gather Victim Network Information
- T1591: Gather Victim Org Information
- T1592: Gather Victim Host Information
- T1598: Phishing for Information
- T1597: Search Open Websites/Domains
- T1589: Gather Victim Identity Information

**Examples:**
- OSINT on target organization
- Domain enumeration
- Employee information gathering
- Technology stack identification

---

### 2. Initial Access (TA0001)
Techniques used to get an initial foothold in a target network.

**Key Techniques:**
- T1189: Drive-by Compromise
- T1190: Exploit Public-Facing Application
- T1133: External Remote Services
- T1200: Hardware Additions
- T1566: Phishing (Email, Spearphishing, etc.)
- T1195: Supply Chain Compromise

**Examples:**
- SQL Injection on web applications
- VPN/RDP credential exploitation
- Malicious email attachments
- USB drop attacks

---

### 3. Execution (TA0002)
Running malicious code on target systems.

**Key Techniques:**
- T1059: Command and Scripting Interpreter
- T1609: Container Administration Command
- T1559: Inter-Process Communication
- T1053: Scheduled Task/Job
- T1648: Serverless Execution
- T1204: User Execution

**Examples:**
- PowerShell script execution
- Bash/Shell command execution
- Python/Perl interpreter abuse
- Windows batch file execution

---

### 4. Persistence (TA0003)
Maintaining access to compromised systems.

**Key Techniques:**
- T1098: Account Manipulation
- T1197: BITS Jobs
- T1547: Boot or Logon Autostart Execution
- T1547.001: Registry Run Keys / Start Folder
- T1547.004: Winlogon Helper DLL
- T1547.014: Startup Folder
- T1547.015: Login Hook
- T1137: Office Application Startup
- T1547.009: Shortcut Modification
- T1547.008: LSASS Driver

**Examples:**
- Registry modification for autostart
- Scheduled tasks for persistence
- DLL hijacking
- Web shell installation
- Cron job abuse (Linux/Mac)

---

### 5. Privilege Escalation (TA0004)
Gaining higher-level permissions on a system.

**Key Techniques:**
- T1548: Abuse Elevation Control Mechanism
- T1548.002: Bypass User Account Control
- T1548.003: Sudo and Sudo Caching
- T1548.004: Elevated Execution with Prompt
- T1134: Access Token Manipulation
- T1037: Boot or Logon Initialization Scripts
- T1547: Boot or Logon Autostart Execution
- T1053: Scheduled Task/Job
- T1543: Create or Modify System Process
- T1611: Escape to Host

**Examples:**
- UAC bypass techniques
- Sudo privilege abuse
- Kernel exploitation
- DLL hijacking
- Service binary manipulation

---

### 6. Defense Evasion (TA0005)
Avoiding detection by defensive systems.

**Key Techniques:**
- T1548: Abuse Elevation Control Mechanism
- T1197: BITS Jobs
- T1612: Build Image on Host
- T1140: Deobfuscate/Decode Files or Information
- T1480: Execution Guardrails
- T1222: File and Directory Permissions Modification
- T1564: Hide Artifacts
- T1564.001: Hidden Files and Directories
- T1564.004: Hidden Window
- T1562: Indicator Removal
- T1036: Masquerading
- T1556: Modify Authentication Process

**Examples:**
- Code obfuscation
- Living-off-the-land binaries (LOLBins)
- Timestomping
- Registry/log clearing
- Polymorphic payloads

---

### 7. Credential Access (TA0006)
Obtaining valid credentials for system access.

**Key Techniques:**
- T1110: Brute Force
- T1555: Credentials from Password Managers
- T1187: Forced Authentication
- T1056: Input Capture
- T1056.001: Keylogging
- T1040: Network Sniffing
- T1111: Multi-Factor Authentication Interception
- T1621: Multi-Factor Authentication Request Generation
- T1040: Network Sniffing
- T1556.006: Modify Authentication Process: Multi-Factor Authentication
- T1040: Network Sniffing
- T1040: Network Sniffing
- T1589: Gather Victim Identity Information
- T1110.001: Brute Force: Password Guessing
- T1110.002: Brute Force: Password Cracking
- T1110.003: Brute Force: Credential Stuffing
- T1110.004: Brute Force: Credential Dumping

**Examples:**
- Credential dumping (mimikatz, pypykatz)
- Phishing for credentials
- Keylogging
- Password spraying
- Rainbow table attacks

---

### 8. Discovery (TA0007)
Identifying systems, services, and network details.

**Key Techniques:**
- T1580: Cloud Infrastructure Discovery
- T1538: Cloud Service Dashboard
- T1526: Cloud Service Discovery
- T1619: Cloud Storage Object Discovery
- T1217: Browser Bookmark Discovery
- T1580: Cloud Infrastructure Discovery
- T1538: Cloud Service Dashboard
- T1622: Debugger Evasion
- T1622: Debugger Evasion
- T1087: Account Discovery
- T1010: Application Window Discovery
- T1217: Browser Bookmark Discovery
- T1580: Cloud Infrastructure Discovery
- T1538: Cloud Service Dashboard
- T1526: Cloud Service Discovery
- T1619: Cloud Storage Object Discovery
- T1622: Debugger Evasion
- T1538: Cloud Service Dashboard

**Examples:**
- Network scanning (nmap, masscan)
- Service enumeration
- File/directory discovery
- System information gathering
- Active Directory enumeration

---

### 9. Lateral Movement (TA0008)
Moving between systems on a network.

**Key Techniques:**
- T1570: Lateral Tool Transfer
- T1210: Exploitation of Remote Services
- T1534: Internal Spearphishing
- T1570: Lateral Tool Transfer
- T1021: Remote Services
- T1021.001: Remote Desktop Protocol
- T1021.002: SSH
- T1021.003: Distributed Component Object Model
- T1021.004: SSH
- T1021.005: VNC
- T1021.006: Windows Admin Shares

**Examples:**
- Pass-the-hash attacks
- Kerberoasting
- Hop through compromised systems
- RDP exploitation
- SSH key reuse

---

### 10. Collection (TA0009)
Gathering information and data from target systems.

**Key Techniques:**
- T1557: Adversary-in-the-Middle
- T1123: Audio Capture
- T1119: Automated Exfiltration
- T1185: Browser Session Hijacking
- T1115: Clipboard Data
- T1530: Data from Cloud Storage
- T1602: Data from Network Device CLI
- T1213: Data from Information Repositories
- T1005: Data from Local System
- T1039: Data from Network Shared Drive
- T1025: Data Staged
- T1123: Audio Capture
- T1119: Automated Exfiltration

**Examples:**
- Screenshotting
- Email collection
- Document theft
- Browser history/credentials
- Database extraction

---

### 11. Exfiltration (TA0010)
Stealing data and information from the target network.

**Key Techniques:**
- T1020: Automated Exfiltration
- T1030: Data Transfer Size Limits
- T1048: Exfiltration Over Alternative Protocol
- T1041: Exfiltration Over C2 Channel
- T1011: Exfiltration Over Other Network Medium
- T1052: Exfiltration Over Physical Medium
- T1048.003: Exfiltration Over Unencrypted Non-C2 Protocol

**Examples:**
- DNS tunneling
- HTTPS exfiltration
- FTP/SFTP data transfer
- Steganography
- Cloud storage uploads

---

### 12. Command & Control (TA0011)
Maintaining communication with compromised systems.

**Key Techniques:**
- T1071: Application Layer Protocol
- T1092: Communication Through Removable Media
- T1001: Data Obfuscation
- T1008: Fallback Channels
- T1105: Ingress Tool Transfer
- T1571: Non-Standard Port
- T1572: Protocol Tunneling
- T1090: Proxy
- T1205: Traffic Signaling

**Examples:**
- DNS beaconing
- HTTP/HTTPS C2
- Encrypted channels
- Proxy chains
- Domain generation algorithms (DGA)

---

### 13. Impact (TA0040)
Disrupting, denying, or destroying systems and data.

**Key Techniques:**
- T1531: Account Access Removal
- T1531: Account Access Removal
- T1499: Endpoint Denial of Service
- T1561: Disk Wipe
- T1485: Data Destruction
- T1491: Defacement
- T1561: Disk Wipe
- T1499: Endpoint Denial of Service
- T1561: Disk Wipe
- T1561.001: Disk Wipe: Wipe After Free
- T1561.002: Disk Wipe: Wipe Free Space
- T1485: Data Destruction
- T1491: Defacement
- T1561: Disk Wipe

**Examples:**
- Ransomware deployment
- File encryption/deletion
- Service disruption
- Website defacement
- Data wiping

---

## Detection & Mitigation

For each technique, consider:

1. **Detection:**
   - Log sources (Windows Event Logs, Sysmon, EDR)
   - Anomalous behavior patterns
   - Signature-based detection
   - Behavioral analysis

2. **Mitigation:**
   - Security controls (MFA, EDR, DLP)
   - Network segmentation
   - Access controls and least privilege
   - User awareness training
   - Patch management

---

## Reference

- MITRE ATT&CK Framework: https://attack.mitre.org/
- Full technique details in individual technique files

---

## Document Updates

Last Updated: 2026
Maintained by: Red Team Documentation
