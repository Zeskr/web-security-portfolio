# Vulnerability Report: Unprotected Administrative Interface (Broken Access Control)

- **Platform:** PortSwigger Web Security Academy
- **Vulnerability Class:** Broken Access Control / Missing Authentication for Critical Function ([CWE-306](https://cwe.mitre.org/data/definitions/306.html))
- **Severity:** High (CVSS: 7.5)
- **Target Route:** `/administrator-panel`
- **Status:** Validated & Solved

---

## 1. Executive Summary
The target web application fails to enforce authentication or authorization middleware on its administrative endpoint. During passive reconnaissance of public crawler directives (`/robots.txt`), an administrative path (`/administrator-panel`) was discovered. An unauthenticated attacker can navigate directly to this panel and execute sensitive administrative actions, including the arbitrary deletion of user accounts.

---

## 2. Technical Reproduction Steps

### Phase 1: Passive Reconnaissance (`/robots.txt`)
Queried the publicly accessible `/robots.txt` endpoint at the root of the domain to identify restricted paths:

```http
GET /robots.txt HTTP/1.1
Host: <LAB-ID>.web-security-academy.net
```

**Response:**
```http
User-agent: *
Disallow: /administrator-panel
```

![Robots.txt Reconnaissance](./images/robots-txt.png)

---

### Phase 2: Direct Endpoint Access & Privilege Bypass
Navigated directly to `https://<LAB-ID>.web-security-academy.net/administrator-panel` without supplying credentials or a privileged session cookie. 

* The application returned an `HTTP 200 OK` status.
* The administrative user management dashboard rendered fully without authentication validation.

---

### Phase 3: Exploitation (Arbitrary User Deletion)
Triggered the deletion endpoint for the user `carlos` by selecting the "Delete" action.

**Execution URL:**
```text
https://<LAB-ID>.web-security-academy.net/administrator-panel/delete?username=carlos
```

**Result:**
The server processed the deletion request with an `HTTP 302 Found` redirect, confirming the deletion of the user.

![Lab Solved & User Deletion Proof](./images/carlos-deleted.png)

---

## 3. Impact Assessment
* **Confidentiality:** Exposure of administrative endpoints and registered user accounts.
* **Integrity:** Unauthorized deletion and modification of user accounts without audit trails.
* **Access Control Failure:** Complete reliance on "Security through Obscurity" by assuming unlinked URLs cannot be discovered.

---

## 4. Remediation & Hardening

1. **Implement Server-Side Access Control Checks:**
   Enforce Role-Based Access Control (RBAC) middleware on all routes matching `/administrator-panel/*`. Ensure the server verifies that the requesting session has an active, authenticated `admin` role.

2. **Remove Sensitive Paths from `robots.txt`:**
   Do not list internal administrative routes in crawler directives. The `robots.txt` file is world-readable and provides an enumeration vector for attackers.

3. **Adopt Default-Deny Architecture:**
   Configure access control rules so all administrative interfaces deny access by default unless explicitly permitted by an authorized session.
