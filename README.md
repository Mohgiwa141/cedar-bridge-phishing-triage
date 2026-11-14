# Cedar Bridge — Phishing Investigation & Alert Triage

**Role:** SOC Analyst · **Date:** 25 Oct 2026 (simulated) · **Verdict:** High Severity — Confirmed Account Takeover

A comprehensive Tier 1 SOC investigation focusing on alert triage, email header analysis, and web vulnerability review. This case highlights the difference between an alert and an incident, and demonstrates how to analyze lookalike domains using prefix attacks.

## Scenario
A reported invoice-themed phishing email was sent to a Cedar Bridge accounts-payable analyst. The email passed SPF/DKIM/DMARC because the attacker controlled their own lookalike domain (`invoice-review.example`). Minutes after delivery, three failed sign-ins preceded a successful external authentication, leading to unauthorized reads of a cloud finance bucket. 

## Skills demonstrated
- **Alert Triage:** Prioritized a queue of four alerts (A01-A04), distinguishing between a benign true positive (authorized scanner), a credible attempted attack (WAF block), and a true positive account takeover.
- **Email Header Forensics:** Analyzed a prefix-attack link where the displayed domain (`portal.cedarbridge.example`) was a strict prefix of the actual malicious destination. Deconstructed why SPF/DKIM/DMARC passing does *not* mean an email is safe.
- **Web & Vulnerability Review:** Evaluated SQLi, XSS, and IDOR findings. Clearly differentiated between a vulnerability *finding* (potential weakness) and *exploitation* (demonstrated activity).
- **Timeline Normalization:** Correlated logs across multiple time zones (UTC, WAT, +01:00 local) to build an accurate, chronological event sequence.
- **Incident Response:** Formulated evidence requests and safe contact procedures (contacting the user out-of-band, not via the phishing email).

## Repository contents
- `report/`: The sanitized final investigation report (PDF).

## Sanitization note
All IPs are RFC 5737 documentation ranges, all domains use the reserved `.example` TLD, and all data is fictional. No real client data, credentials, or live infrastructure is included.

## Author
**Umar Mohammed**
