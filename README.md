# Web Application & Network Security Portfolio

A curated repository of corporate-grade Vulnerability Assessment and Penetration Testing (VAPT) reports. This portfolio documents manual exploitation, attack chaining, and developer-focused remediation across simulated enterprise environments and live public targets.

---

## 📂 Flagship Assessments & Disclosures

### 1. Simulated Enterprise Compromise (HackTheBox / Custom Labs)
Full kill-chain documentation, from external reconnaissance and initial foothold to privilege escalation and data exfiltration.

| Target / Environment | Finding / Attack Chain | Severity | Report Link |
| :--- | :--- | :--- | :--- |
| **Target: Staging E-Commerce** (Web Security Academy) | Remote Code Execution via Polyglot Web Shell Upload | Critical (9.8) | [View VAPT Report](./reports/RCE-Polyglot-Upload.md) |
| **Target: Internal API** (Web Security Academy) | Arbitrary File Read via Null Byte Path Traversal | High (7.5) | [View VAPT Report](./reports/File-Read-Null-Byte.md) |
| **Target: Legacy Linux Server** (HackTheBox / VulnHub) | *[Insert HTB Box Name e.g., Initial Foothold via SQLi -> Root via Cronjob]* | Critical (9.8) | [View VAPT Report](./reports/HTB-BoxName-Report.md) |

### 2. Vulnerability Disclosure Programs (Live Targets)
Ethical disclosures on production infrastructure (HackerOne / Bugcrowd / Intigriti). *Note: Sensitive data and exact target names are redacted where non-disclosure agreements (NDAs) apply.*

| Target Industry | Vulnerability Class | Impact | Status |
| :--- | :--- | :--- | :--- |
| **Fintech / SaaS** | *[e.g., Insecure Direct Object Reference (IDOR)]* | High | Triaged / Resolved |
| **E-Commerce** | *[e.g., Business Logic Flaw in Checkout]* | Medium | Triaged / Resolved |

*(Link to your HackerOne/Bugcrowd public profile here if applicable, or link to redacted write-ups).*

---

## 🛠️ Assessment Methodology & Reporting Standard

To mirror industry-standard VAPT deliverables, all simulated engagements and public disclosures in this repository strictly adhere to the following documentation methodology:

1. **Executive Risk Profiling:** 
   Translating technical flaws into actionable business impact using standard CVSS v3.1 vector scoring and CWE classifications.
2. **Manual Attack Narrative (The Kill Chain):** 
   Step-by-step documentation of the exploitation lifecycle without reliance on automated vulnerability scanners (e.g., Nessus/Qualys). 
3. **Cryptographic & Traffic Proof of Concept (PoC):** 
   Provision of raw HTTP/HTTPS request and response artifacts intercepted via Burp Suite Professional/Community, ensuring 100% reproducibility for development teams.
4. **Developer-Ready Remediation:** 
   Moving beyond generic advice by providing specific architectural hardening guidelines, secure coding practices, and configuration adjustments to neutralize the root cause.
