# drvikram.in - Vulnerability Assessment Report

## Executive Summary
Target: https://drvikram.in
Host: Netlify
Tech Stack: Firebase (Firestore), Netlify
Type: Static website (Homeopathic Clinic)

---

## Recon Findings

### Subdomains Found
- drvikram.in (main)
- www.drvikram.in
- cpanel.drvikram.in
- cpcalendars.drvikram.in
- cpcontacts.drvikram.in

Note: Subdomains lead to generic parking pages or are inaccessible.

### Technology Stack
- Hosting: Netlify
- Frontend: Static HTML/JS
- Backend: Firebase (Firestore for data)
- No CMS detected (no WordPress, no PHP)

---

## Scanning Results

### Nuclei Vulnerability Scan
- No critical/high/medium vulnerabilities detected
- Default Netlify security headers present

### Directory Fuzzing
- No interesting directories found (admin, api, login all 404)
- Limited attack surface (static site)

### Sensitive Files Check
- .env: Not accessible
- .git: Not exposed
- wp-config.php: Not applicable (not WordPress)
- phpinfo.php: Not found

---

## Findings Summary

| Severity | Finding | Status |
|----------|---------|--------|
| N/A | Subdomain enumeration | 5 subdomains found |
| N/A | Technology stack | Netlify + Firebase |
| N/A | Vulnerabilities | None found |

---

## Recommendations
1. **Secure Firebase Rules** - Ensure Firestore rules are properly configured (no public read/write)
2. **Netlify Headers** - Already has HSTS enabled
3. **API Keys** - Ensure no hardcoded Firebase API keys in client-side code

---

## Conclusion
drvikram.in is a static Netlify-hosted website with minimal attack surface. No critical vulnerabilities found during this scan. The main concern would be improper Firebase security rules if there's backend data.

*Scan Date: 2026-02-28*
*Tools Used: subfinder, amass, httpx, nuclei, ffuf*