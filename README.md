<!-- TOP BANNER -->
<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=CC0000,8B0000&height=220&section=header&text=wyllowDev&fontSize=70&fontColor=ffffff&fontAlignY=38&desc=Red%20Team%20Operator%20%7C%20Offensive%20Security&descSize=18&descAlignY=58&descColor=ffcccc&animation=fadeIn"/>

<div align="center">

[

![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1000&color=FF2020&center=true&vCenter=true&width=650&lines=Red+Team+%7C+Offensive+Security+Specialist;Web+%26+Network+Pentesting+%7C+Bug+Bounty+Hunter;Vulnerability+Research+%7C+Exploit+Development;Breaking+Things+To+Make+Them+Stronger)

](https://git.io/typing-svg)

<br>

<img src="https://img.shields.io/badge/🎯_Focus-Offensive%20Security-CC0000?style=for-the-badge"/>
<img src="https://img.shields.io/badge/🏢_Company-HugeNetwork-1a1a2e?style=for-the-badge"/>
<img src="https://img.shields.io/badge/💀_Mode-Always%20Hacking-000000?style=for-the-badge"/>
<img src="https://img.shields.io/badge/🐛_Bug%20Bounty-Active-CC0000?style=for-the-badge"/>

</div>

---

## `> whoami`

```bash
┌──(wyllowDev㉿kali)-[~]
└─$ id
uid=1337(wyllowDev) gid=1337(redteam) groups=1337(redteam),0(root)

┌──(wyllowDev㉿kali)-[~]
└─$ cat about.txt
Pentester focado em segurança ofensiva, exploração de vulnerabilidades
e análise profunda de aplicações web e infraestruturas.
Atualmente atuando na HugeNetwork com experiência prática em
ambientes reais, bug bounty e automação de testes de segurança.
```

---

## `> tech_stack --list-all`

<details>
<summary><b>💻 Linguagens de Programação</b></summary>
<br>
<div align="center">

<img src="https://skillicons.dev/icons?i=php,c,cpp,cs,js,ts,python,java,rust,go,lua,html,css&theme=dark&perline=7"/>

</div>
</details>

<details>
<summary><b>🧩 Frameworks & Frontend</b></summary>
<br>
<div align="center">

<img src="https://skillicons.dev/icons?i=laravel,vue,vite,tailwind,bootstrap&theme=dark"/>

</div>
</details>

<details>
<summary><b>⚙️ DevOps & Infraestrutura</b></summary>
<br>
<div align="center">

<img src="https://skillicons.dev/icons?i=docker,kubernetes,githubactions,terraform,ansible&theme=dark"/>

</div>
</details>

<details>
<summary><b>🔒 Security & OS</b></summary>
<br>
<div align="center">

<img src="https://skillicons.dev/icons?i=linux,kali,bash,git,github,aws,azure,gcp&theme=dark"/>

</div>
</details>

---

## `> pentest --skills --verbose`

<table>
<tr>
<td width="50%" valign="top">

### 🕸️ Web Application Pentest
```
[✓] XSS — Stored, Reflected, DOM
[✓] SQL Injection
[✓] CSRF / SSRF
[✓] IDOR
[✓] File Upload Bypass
[✓] LFI / RFI
[✓] Open Redirect
[✓] Race Conditions
[✓] WAF Bypass
[✓] Payload Obfuscation & Encoding
[✓] Fuzzing Avançado
[✓] Exploração Manual
[✓] XXE Injection
[✓] SSTI (Template Injection)
[✓] HTTP Request Smuggling
[✓] Insecure Deserialization
[✓] CORS Misconfiguration
[✓] Clickjacking
```

### 🔐 Auth & Session Attacks
```
[✓] Broken Authentication
[✓] Session Hijacking & Fixation
[✓] JWT Attacks (alg:none, RS→HS)
[✓] OAuth 2.0 Flaws
[✓] Brute Force / Credential Stuffing
[✓] Rate Limit Bypass
[✓] 2FA Bypass
[✓] Password Reset Poisoning
```

</td>
<td width="50%" valign="top">

### 🌐 Network Pentest
```
[✓] Enumeração de Rede
[✓] Nmap Avançado (NSE Scripts)
[✓] FTP • SMB • SSH • RDP
[✓] SNMP Enumeration
[✓] DNS Zone Transfer
[✓] Pivoting
[✓] Port Forwarding
[✓] Tunneling (Chisel, Ligolo-ng)
[✓] ARP Spoofing / MITM
[✓] Pass-the-Hash / Pass-the-Ticket
```

### ☁️ Cloud Security
```
[✓] AWS — S3, IAM, EC2, Lambda
[✓] Azure AD Attacks
[✓] GCP Misconfigurations
[✓] Privilege Escalation
[✓] SSRF → Cloud Metadata
[✓] Exposed Keys & Secrets
[✓] Container Escape (Docker/K8s)
```

### 🔌 API Security
```
[✓] REST & GraphQL
[✓] IDOR em APIs
[✓] Mass Assignment
[✓] Rate Limiting Bypass
[✓] GraphQL Introspection Abuse
[✓] Broken Object Level Auth
[✓] API Key Leakage
```

</td>
</tr>
</table>

---

## `> recon --automate`

```python
#!/usr/bin/env python3
# wyllowDev — Recon Pipeline

scope = "target.com"

tools = {
    "Amass":      f"amass enum -d {scope} -o recon/subdomains.txt",
    "Subfinder":  f"subfinder -d {scope} -o recon/subfinder.txt",
    "httpx":      f"httpx -l recon/subdomains.txt -o recon/live_hosts.txt",
    "FFUF":       f"ffuf -u https://{scope}/FUZZ -w wordlist.txt -o recon/dirs.txt",
    "Nuclei":     f"nuclei -l recon/live_hosts.txt -t ~/nuclei-templates/ -o recon/nuclei.txt",
    "gau":        f"gau {scope} | tee recon/endpoints.txt",
    "LinkFinder": f"python3 linkfinder.py -i https://{scope} -o cli",
    "Wayback":    f"waybackurls {scope} | tee recon/wayback.txt",
    "Katana":     f"katana -u https://{scope} -o recon/crawl.txt",
    "TruffleHog": f"trufflehog git https://github.com/target/repo",
}

for name, cmd in tools.items():
    print(f"[*] Running {name}...")
    os.system(cmd)
```

---

## `> arsenal --list --full`

<div align="center">

### 🔴 Exploitation & Web

| Tool | Badge | Uso |
|------|-------|-----|
| Burp Suite Pro | 

![Burp](https://img.shields.io/badge/Burp%20Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white)

 | Proxy, Scanner, Intruder |
| OWASP ZAP | 

![ZAP](https://img.shields.io/badge/OWASP%20ZAP-00549E?style=flat-square&logo=owasp&logoColor=white)

 | Análise Automatizada |
| SQLmap | 

![SQLmap](https://img.shields.io/badge/SQLmap-CC0000?style=flat-square&logoColor=white)

 | SQL Injection Automation |
| XSStrike | 

![XSStrike](https://img.shields.io/badge/XSStrike-FF4500?style=flat-square&logoColor=white)

 | XSS Detection & Exploitation |
| Dalfox | 

![Dalfox](https://img.shields.io/badge/Dalfox-FF0055?style=flat-square&logoColor=white)

 | XSS Scanner Avançado |
| Commix | 

![Commix](https://img.shields.io/badge/Commix-8B0000?style=flat-square&logoColor=white)

 | Command Injection |

### 🌐 Network & Infrastructure

| Tool | Badge | Uso |
|------|-------|-----|
| Nmap | 

![Nmap](https://img.shields.io/badge/Nmap-004170?style=flat-square&logoColor=white)

 | Port Scan & NSE Scripts |
| Metasploit | 

![MSF](https://img.shields.io/badge/Metasploit-2596CD?style=flat-square&logoColor=white)

 | Exploitation Framework |
| Impacket | 

![Impacket](https://img.shields.io/badge/Impacket-1a1a1a?style=flat-square&logoColor=white)

 | SMB & Kerberos Attacks |
| CrackMapExec | 

![CME](https://img.shields.io/badge/CrackMapExec-CC0000?style=flat-square&logoColor=white)

 | AD & Lateral Movement |
| Chisel | 

![Chisel](https://img.shields.io/badge/Chisel-444444?style=flat-square&logoColor=white)

 | Tunneling & Pivoting |
| Ligolo-ng | 

![Ligolo](https://img.shields.io/badge/Ligolo--ng-222222?style=flat-square&logoColor=white)

 | Advanced Pivoting |

### 🔎 Recon & Fuzzing

| Tool | Badge | Uso |
|------|-------|-----|
| FFUF | 

![FFUF](https://img.shields.io/badge/FFUF-39FF14?style=flat-square&logoColor=black)

 | Directory & Parameter Fuzzing |
| Nuclei | 

![Nuclei](https://img.shields.io/badge/Nuclei-00BFFF?style=flat-square&logoColor=white)

 | Templates de Vulnerabilidades |
| Amass | 

![Amass](https://img.shields.io/badge/Amass-FF8C00?style=flat-square&logoColor=white)

 | Subdomain Enumeration |
| Subfinder | 

![Subfinder](https://img.shields.io/badge/Subfinder-00BFFF?style=flat-square&logoColor=white)

 | Passive Recon |
| Katana | 

![Katana](https://img.shields.io/badge/Katana-DC143C?style=flat-square&logoColor=white)

 | Web Crawler Avançado |
| TruffleHog | 

![Trufflehog](https://img.shields.io/badge/TruffleHog-B8860B?style=flat-square&logoColor=white)

 | Secrets & Credential Leaks |

### 🔐 Password & Auth Attacks

| Tool | Badge | Uso |
|------|-------|-----|
| Hashcat | 

![Hashcat](https://img.shields.io/badge/Hashcat-CC0000?style=flat-square&logoColor=white)

 | GPU Password Cracking |
| John the Ripper | 

![John](https://img.shields.io/badge/John%20The%20Ripper-8B0000?style=flat-square&logoColor=white)

 | Hash Cracking |
| Hydra | 

![Hydra](https://img.shields.io/badge/THC%20Hydra-FF4500?style=flat-square&logoColor=white)

 | Brute Force Online |
| Medusa | 

![Medusa](https://img.shields.io/badge/Medusa-6A0DAD?style=flat-square&logoColor=white)

 | Parallel Login Brute Force |

</div>

---

## `> stats --github`

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=wyllowDev&show_icons=true&theme=dark&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=CC0000&icon_color=CC0000&text_color=ffffff"/>
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=wyllowDev&layout=compact&langs_count=8&theme=dark&hide_border=true&bg_color=0d1117&title_color=CC0000&text_color=ffffff"/>

</div>

<br>

<div align="center">

[

![GitHub Streak](https://streak-stats.demolab.com?user=wyllowDev&theme=dark&hide_border=true&background=0D1117&stroke=CC0000&ring=CC0000&fire=FF6633&currStreakLabel=CC0000&sideLabels=ffffff&dates=888888)

](https://git.io/streak-stats)

</div>

<br>

<div align="center">

<img src="https://github-profile-trophy.vercel.app/?username=wyllowDev&theme=onedark&no-frame=true&no-bg=true&margin-w=6&column=7"/>

</div>

<br>

<div align="center">

<img width="100%" src="https://github-readme-activity-graph.vercel.app/graph?username=wyllowDev&bg_color=0d1117&color=CC0000&line=CC0000&point=ffffff&area=true&area_color=8B0000&hide_border=true&title_color=CC0000"/>

</div>

---

## `> contact --connect`

<div align="center">

[

![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)

](https://linkedin.com/in/wyllowDev)
[

![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)

](https://twitter.com/wyllowDev)
[

![HackerOne](https://img.shields.io/badge/HackerOne-494649?style=for-the-badge&logo=hackerone&logoColor=white)

](https://hackerone.com/wyllowDev)
[

![Bugcrowd](https://img.shields.io/badge/Bugcrowd-F26822?style=for-the-badge&logo=bugcrowd&logoColor=white)

](https://bugcrowd.com/wyllowDev)

</div>

<br>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=CC0000,8B0000&height=120&section=footer&text=The+quieter+you+become%2C+the+more+you+are+able+to+hear.&fontSize=13&fontColor=ffcccc&fontAlignY=65&animation=fadeIn"/>

<div align="center">



![Visitor Count](https://komarev.com/ghpvc/?username=wyllowDev&color=CC0000&style=flat-square&label=profile+views)



</div>