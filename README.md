# 🔎 Dripping Blues – Penetration Testing Project

## 📌 Project Overview

This project demonstrates a structured penetration testing process performed against a vulnerable Linux machine in a controlled lab environment.

The objective was to identify exposed services, exploit misconfigurations, retrieve sensitive files, and perform password cracking to demonstrate real-world security risks.

---

## 🎯 Objectives

- Discover live hosts in the network  
- Identify open ports and services  
- Exploit misconfigured FTP service  
- Retrieve sensitive files  
- Crack password-protected ZIP files  
- Analyze security weaknesses  

---

## 🛠 Tools Used

- Kali Linux  
- Nmap  
- Netdiscover  
- FTP Client  
- zip2john  
- John the Ripper  

---

## 🔎 Step-by-Step Methodology

### 1️⃣ Identify Live Hosts

```bash
netdiscover -r 192.168.26.0/24
```

Used to detect active devices in the local network.

---

### 2️⃣ Scan All Open Ports

```bash
nmap -p- 192.168.26.133
```

Scanned all 65,535 TCP ports to identify running services.

**Discovered Services:**
- FTP
- SSH
- HTTP

---

### 3️⃣ Exploit Anonymous FTP Access

```bash
ftp 192.168.26.133
```

Anonymous login was enabled, allowing file access without authentication.

---

### 4️⃣ Download Sensitive ZIP File

```bash
get respectmydrip.zip
```

Downloaded ZIP file from target system.

---

### 5️⃣ Extract ZIP Hash

```bash
zip2john respectmydrip.zip > drip.hash
```

Converted ZIP password into crackable hash format.

---

### 6️⃣ Crack ZIP Password

```bash
john drip.hash --wordlist=/usr/share/wordlists/rockyou.txt
```

Performed dictionary attack using common wordlist.

Password successfully cracked.

---

### 7️⃣ Crack Second ZIP File

```bash
zip2john secret.zip > secret.hash
john secret.hash --wordlist=/usr/share/wordlists/rockyou.txt
```

Second ZIP password cracked successfully.

---

### 8️⃣ Final Verification

```bash
john --show secret.hash
```

Displayed cracked password for confirmation.

---

## 🚨 Vulnerabilities Identified

| Service | Issue | Risk Level |
|----------|--------|------------|
| FTP | Anonymous login enabled | High |
| File Security | Weak password protection | High |
| Monitoring | No brute-force detection | Medium |

---

## 🛡 Security Risks

The vulnerable system allowed:

- Unauthorized file access  
- Sensitive file retrieval  
- Password cracking using common wordlists  
- Exposure due to poor service configuration  

If deployed in production, this could lead to full data compromise.

---

## 🔐 Mitigation Recommendations

- Disable anonymous FTP access  
- Enforce strong password policies  
- Monitor abnormal file downloads  
- Implement brute-force detection mechanisms  
- Regularly audit and patch services  

---

## 📊 Skills Demonstrated

✔ Network Discovery  
✔ Full Port Scanning  
✔ Service Enumeration  
✔ FTP Exploitation  
✔ Hash Extraction  
✔ Password Cracking  
✔ Risk Assessment & Reporting  

---

## 📌 Conclusion

The Dripping Blues machine was successfully compromised due to insecure service configuration and weak password protection.

This project highlights the importance of secure service configuration, monitoring, and strong authentication practices.

All testing was performed in a controlled lab environment.
