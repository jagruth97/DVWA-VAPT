# 🔓 Vulnerability Assessment & Pentesting Lab (DVWA)

This project simulates real-world web attacks on the Damn Vulnerable Web Application (DVWA) hosted on Metasploitable, using Kali Linux as the attacker. It demonstrates core OWASP vulnerabilities with tools like SQLmap, Hydra, Burp Suite, and manual testing techniques.

## ⚙️ Lab Setup

| VM           | Role      | Description                             |
|--------------|-----------|-----------------------------------------|
| Kali Linux   | Attacker  | Nmap, SQLmap, Hydra, Burp Suite         |
| Metasploitable | Target   | DVWA (SQLi, XSS, CSRF, CMD Injection)   |

Network: Bridged, same subnet

## Project Structure

<pre>
dvwa-vapt-lab/
├── docs/
│   ├── DVWA_VAPT_Report.docx
│   └── DVWA_VAPT_Report.pdf
├── screenshots/
├── README.md
├── attack_walkthrough.md
├── vulnerability_findings.md
└── csrf_attack.html (PoC file if CSRF-medium)
</pre>

## 🧪 Simulated Attacks

| Attack Type          | Tool       | Notes                                  |
|----------------------|------------|----------------------------------------|
| SQL Injection        | SQLmap     | DB enumeration, bypass login           |
| Command Injection    | Browser/Burp | Executed `id`, `uname -a`             |
| Auth Bypass          | Manual     | `' or '1'='1` exploited login form     |
| FTP Brute Force      | Hydra      | Cracked `msfadmin` via vsftpd          |
| XSS (Reflected/Stored) | Browser   | Alert popups captured                  |
| CSRF (Medium Security) | HTML PoC | Tokenless GET attack crafted & worked  |

## 📄 Documentation

- Full walkthrough: [`attack_walkthrough.md`](attack_walkthrough.md)
- Vulnerability descriptions: [`vulnerability_findings.md`](vulnerability_findings.md)
- Final report: [`docs/DVWA_VAPT_Report.docx`](docs/DVWA_VAPT_Report.docx)

## 📸 Screenshots

Found in `/screenshots` folder — includes commands, Burp Suite captures, payloads, and success indicators.

## ✅ Resume Value

This project demonstrates practical offensive security skills, tool usage, manual and automated exploitation, and modern reporting — all documented in a reproducible GitHub repository.
