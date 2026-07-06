<div align="center">

# 🔍 Dripping Blues – Penetration Testing Project

### Discover • Enumerate • Exploit • Analyze • Report

![Kali Linux](https://img.shields.io/badge/Kali-Linux-268BEE?style=for-the-badge&logo=kalilinux&logoColor=white)
![Target](https://img.shields.io/badge/Target-Dripping%20Blues-red?style=for-the-badge)
![Nmap](https://img.shields.io/badge/Nmap-Network%20Scanner-blue?style=for-the-badge)
![FTP](https://img.shields.io/badge/FTP-Enumeration-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-blueviolet?style=for-the-badge)

<a href="https://github.com/abhiramyadav03">
<img src="https://img.shields.io/badge/GitHub-abhiramyadav03-181717?style=for-the-badge&logo=github"/>
</a>

<a href="https://www.linkedin.com/in/rapothulaabhiram/">
<img src="https://img.shields.io/badge/LinkedIn-Abhiram%20Rapothula-0A66C2?style=for-the-badge&logo=linkedin"/>
</a>

</div>

---

# 📖 Overview

The **Dripping Blues** machine is a beginner-friendly penetration testing lab designed to simulate a real-world attack against a vulnerable Linux server.

This project demonstrates a structured penetration testing methodology beginning with reconnaissance, host discovery, service enumeration, vulnerability identification, exploitation, password cracking, sensitive file discovery, and post-exploitation analysis.

The assessment follows industry-standard penetration testing practices while documenting each phase of the attack lifecycle and highlighting the associated security risks.

---

# 🎯 Objectives

- Discover live hosts
- Perform network reconnaissance
- Identify open ports
- Enumerate network services
- Analyze FTP service
- Retrieve exposed files
- Crack password-protected ZIP archive
- Identify sensitive information
- Demonstrate exploitation workflow
- Document security findings

---

# 📑 Table of Contents

- Overview
- Objectives
- Lab Environment
- Tools Used
- Attack Methodology
- Reconnaissance
- Network Enumeration
- FTP Enumeration
- Password Cracking
- Sensitive File Discovery
- Security Findings
- MITRE ATT&CK Mapping
- Results
- Screenshot Gallery
- Skills Demonstrated
- Learning Outcomes
- References
- License
- Author

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|----------|
| Operating System | Kali Linux |
| Target Machine | Dripping Blues |
| Virtualization | VMware Workstation |
| Network | NAT |
| Attack Machine | Kali Linux |
| Target OS | Linux |

---

# 🛠️ Tools Used

| Tool | Purpose |
|------|---------|
| Nmap | Host discovery & port scanning |
| FTP Client | File retrieval |
| zip2john | ZIP hash extraction |
| John the Ripper | Password cracking |
| Linux Terminal | Enumeration |
| VMware Workstation | Virtual lab |

---

# 🗺️ Attack Methodology

```
Target Discovery

      │

      ▼

Host Identification

      │

      ▼

Port Scanning

      │

      ▼

Service Enumeration

      │

      ▼

FTP Enumeration

      │

      ▼

File Discovery

      │

      ▼

Password Cracking

      │

      ▼

Sensitive Information Collection

      │

      ▼

Security Assessment
```

---

# 🌐 Reconnaissance

The first phase involved identifying the target machine within the local network.

### Activities Performed

- Host discovery
- IP identification
- Network validation
- Connectivity testing

### Objective

Locate the vulnerable machine before beginning enumeration.

---

# 🔎 Network Enumeration

After identifying the target, Nmap was used to enumerate exposed network services.

### Scan Performed

```bash
nmap -sV -sC <Target-IP>
```

### Information Gathered

- Open TCP ports
- Running services
- Service versions
- Default NSE scripts
- Banner information

### Purpose

Identify potential attack vectors exposed by the target.

---

# 📡 Service Discovery

The Nmap scan identified several services available on the target.

| Service | Purpose |
|----------|---------|
| FTP | File Transfer |
| SSH | Remote Access |
| HTTP | Web Service |

Each discovered service was analyzed to determine whether it could be leveraged during the assessment.

---

# 📂 FTP Enumeration

FTP enumeration was performed to determine whether anonymous access or exposed files were available.

### Activities

- Connected to FTP
- Listed available files
- Downloaded accessible content
- Reviewed directory structure

### Findings

Sensitive files were successfully retrieved from the FTP server for further investigation.

---

# 🔐 Password Cracking

One of the downloaded files contained a password-protected ZIP archive.

The following workflow was used:

### Step 1

Extract the ZIP password hash.

```bash
zip2john secret.zip > hash.txt
```

### Step 2

Crack the password using John the Ripper.

```bash
john hash.txt
```

### Objective

Recover the archive password and access the protected contents.

---

# 📁 Sensitive File Analysis

After extracting the archive, the recovered files were analyzed for useful information.

Items reviewed included:

- Credentials
- Notes
- Configuration files
- User information
- Potential attack paths

The discovered information assisted in understanding the overall security posture of the target.

---

# 🛡️ MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1595 | Active Scanning |
| T1046 | Network Service Discovery |
| T1083 | File and Directory Discovery |
| T1003 | Credential Access |
| T1110 | Password Cracking |
| T1078 | Valid Accounts |

---

# 🚨 Security Findings

The penetration test revealed several security weaknesses that could be exploited by an attacker.

## Key Findings

| Finding | Risk |
|----------|------|
| FTP Service Exposed | Medium |
| Sensitive Files Accessible | High |
| Password-Protected ZIP Archive | Medium |
| Weak Password | High |
| Information Disclosure | High |

---

## Risk Assessment

| Category | Severity |
|-----------|----------|
| Confidentiality | High |
| Integrity | Medium |
| Availability | Low |

---

# 📊 Results

The assessment successfully demonstrated the complete penetration testing lifecycle.

### Reconnaissance

✅ Target identified

---

### Enumeration

✅ Services discovered

---

### FTP Enumeration

✅ Files successfully downloaded

---

### Password Cracking

✅ ZIP password recovered

---

### Sensitive File Discovery

✅ Confidential information extracted

---

### Documentation

✅ Findings documented

---

# 📸 Screenshot Gallery

## Target Discovery

```text
01-target-discovery.png
```

---

## Nmap Scan

```text
02-nmap-scan.png
```

---

## FTP Enumeration

```text
03-ftp-enumeration.png
```

---

## Downloaded Files

```text
04-downloaded-files.png
```

---

## ZIP Password Cracking

```text
05-john-the-ripper.png
```

---

## Extracted Sensitive Files

```text
06-sensitive-files.png
```

---

# 💡 Skills Demonstrated

- Penetration Testing
- Network Enumeration
- Nmap Scanning
- FTP Enumeration
- Password Cracking
- John the Ripper
- Linux Enumeration
- File Analysis
- Security Assessment
- Documentation
- Reporting

---

# 🎓 Learning Outcomes

After completing this project, I gained practical experience in:

- Performing network reconnaissance.
- Enumerating exposed services.
- Identifying vulnerable network services.
- Downloading files from exposed FTP servers.
- Extracting password hashes.
- Cracking passwords using John the Ripper.
- Analyzing recovered files.
- Documenting penetration testing findings.
- Following a structured penetration testing methodology.

---

# 🚀 Future Improvements

Potential enhancements include:

- Perform full vulnerability scanning before exploitation.
- Automate enumeration using Bash or Python.
- Integrate Nmap NSE scripts for deeper analysis.
- Document CVSS scores for identified weaknesses.
- Map findings to CIS Controls.
- Include remediation recommendations for each finding.

---

# 📚 References

- Nmap Documentation  
  https://nmap.org/book/

- John the Ripper Documentation  
  https://www.openwall.com/john/

- MITRE ATT&CK Framework  
  https://attack.mitre.org/

- OWASP Web Security Testing Guide  
  https://owasp.org/www-project-web-security-testing-guide/

- PTES – Penetration Testing Execution Standard  
  http://www.pentest-standard.org/

---

# 📄 License

This project is intended for educational and cybersecurity learning purposes only.

The activities documented in this repository were performed in a controlled lab environment.

Do not attempt these techniques against systems you do not own or have explicit permission to test.

---

# 👨‍💻 Author

**Abhiram Rapothula**

🎓 B.Tech – Computer Science & Engineering (Cybersecurity)

📍 Hyderabad, Telangana, India

### Connect with Me

- GitHub: https://github.com/abhiramyadav03
- LinkedIn: https://www.linkedin.com/in/rapothulaabhiram/
- TryHackMe: https://tryhackme.com/p/rapothula1907

---

<div align="center">

## ⭐ If you found this project useful, consider giving it a Star!

**Hack Responsibly • Learn Continuously • Secure Everything 🔐**

</div>
