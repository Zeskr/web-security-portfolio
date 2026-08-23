# Web Security & Vulnerability Research Portfolio

A central repository documenting manual web application security assessments, vulnerability reproduction (PoCs), and remediation strategies across laboratory environments and live targets.

---

## 📂 Research Directory

| Category | Platform / Scope | Focus Areas | Write-ups |
| :--- | :--- | :--- | :--- |
| **Access Control** | PortSwigger Web Security Academy | IDOR, Privilege Escalation, URL Bypasses | [View Reports](./portswigger/access-control/) |
| **Server-Side Flaws** | PortSwigger / Bug Bounty | SSRF, SQL Injection, File Uploads | *Coming Soon* |
| **Client-Side Attacks** | PortSwigger / Labs | Reflected/Stored XSS, CSRF, CORS | *Coming Soon* |
| **Network & CTF** | TryHackMe | Full-scope methodology & network auditing | [View Rooms](./tryhackme/) |
| **VDP Findings** | HackerOne / Bugcrowd | Disclosed production findings | [View Disclosures](./bug-bounty-vdp/) |

---

## 🛠️ Assessment Methodology
Every finding in this repository includes:
1. **Executive Summary:** Business impact and technical risk breakdown.
2. **Reproduction Steps:** Step-by-step manual replication process without reliance on automated tools.
3. **Proof of Concept (PoC):** Raw HTTP requests and responses intercepted via Burp Suite.
4. **Remediation:** Specific code and architecture hardening guidelines for development teams.
