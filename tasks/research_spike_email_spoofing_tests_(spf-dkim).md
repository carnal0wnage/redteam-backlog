# 📧 Research Spike: Email Spoofing Tests (SPF/DKIM/DMARC)

**Goal:**  
Evaluate the organization’s email domains to determine whether they are vulnerable to external spoofing due to missing, misconfigured, or overly permissive SPF, DKIM, or DMARC records.

**Why It Matters:**  
Email spoofing is a common precursor to phishing and business email compromise (BEC). Strong DNS-based email authentication helps prevent impersonation of internal domains. Understanding how to test and validate these records is foundational knowledge for red teamers and defenders alike.

---

### 🔍 Scope
- Primary email domain(s) used by the organization
- Known aliases, marketing domains, legacy or subdomains
- Publicly visible DNS records: SPF, DKIM, DMARC
- Email delivery to trusted and external mailboxes for test validation

---

### ✅ Tasks
- [ ] Identify all internal email-sending domains (e.g., `example.com`, `marketing.example.com`)
- [ ] Use DNS tools to retrieve and inspect:
  - SPF records: `dig txt example.com`
  - DKIM selectors: `dig txt selector._domainkey.example.com`
  - DMARC policy: `dig txt _dmarc.example.com`
- [ ] Use online testing tools to validate:
  - [dmarcian](https://dmarcian.com/)
  - [MXToolbox SPF/DKIM/DMARC testers](https://mxtoolbox.com/)
  - [Google Admin Toolbox CheckMX](https://toolbox.googleapps.com/apps/checkmx/)
- [ ] Attempt to spoof emails from a test domain:
  - Use a third-party service like [Mailtrap](https://mailtrap.io/), [Swaks](https://github.com/DomainTools/svaks), or a local mail client
  - Send test emails *from* `spoofed@company.com` *to* internal and external inboxes
- [ ] Record delivery success, SPF/DKIM/DMARC results, and failure modes
- [ ] Note differences between strict vs. relaxed configurations

---

### 🎯 Deliverables
- Internal report or wiki entry with:
  - Table of email domains and current SPF/DKIM/DMARC status
  - Screenshots or logs of DNS lookups and spoofing attempts
  - Summary of spoofing test results (which domains allowed spoofing)
  - Recommendations to tighten policies (`p=reject`, strict alignment)
  - Draft guidance for blue team to monitor and alert on spoofing attempts

---

### 📚 Reference Materials
- dmarcian SPF/DKIM/DMARC Inspector: https://dmarcian.com  
- MXToolbox Email Tools: https://mxtoolbox.com  
- Google CheckMX: https://toolbox.googleapps.com/apps/checkmx/  
- Swaks (Swiss Army Knife for SMTP): https://github.com/DomainTools/svaks  
- SPF Specification: https://datatracker.ietf.org/doc/html/rfc7208  
- DKIM Specification: https://datatracker.ietf.org/doc/html/rfc6376  
- DMARC Specification: https://dmarc.org/specification/

---

### 🏷️ Tags / Labels
`junior-friendly` `email-security` `spf` `dmarc` `dkim` `recon` `phishing-prevention`

---

### 📈 Effort Level
**Small (S)** — research, DNS inspection, and controlled spoofing are low-lift but high-value.

---

### ✅ Acceptance Criteria
- [ ] At least 2 internal domains evaluated
- [ ] SPF/DKIM/DMARC records documented
- [ ] Spoofing attempts conducted and delivery behavior analyzed
- [