# FlyThe BG — Data Retention Schedule

Updated: 2026-10-25

This schedule is an engineering baseline and must be reconciled with the actual providers and applicable legal requirements before production use.

| Data / record | Purpose | Baseline retention |
|---|---|---|
| Browser consent record | Remember optional technology choice | Browser localStorage until the user changes/clears it or browser data is removed; no server-side ledger |
| Uploaded image for background removal | Perform the requested transformation | No FlyThe BG media library; do not intentionally retain after the processing workflow |
| Browser-local image/video source | Local compression | Remains on user's device unless the browser/tool itself stores it |
| Application/security infrastructure logs | Detect, investigate and remediate abuse/incidents | Provider/configuration-specific; confirm actual Cloudflare and processor settings. Prepare for applicable Rule 6 log/personal-data retention requirements from their commencement date; do not apply a generic period to all user data |
| Privacy request record | Handle rights/grievances | Retain only as long as necessary to manage the request, demonstrate handling, and meet applicable legal obligations |
| Consent audit ledger, if later implemented | Demonstrate consent decisions | Define purpose-specific period before enabling; do not store uploaded media |

## Rules

- Never create a general-purpose media archive for uploaded files.
- Do not keep personal data merely because storage is convenient.
- Processor retention periods must be checked against the processor's actual configuration and contract.
- Delete or anonymize records when the documented purpose ends, unless retention is required by law or necessary for a documented legal/security purpose.


## No-account rights requests

There is no user-account profile or persistent media library to export/delete. Support correspondence and technical/security records may still contain personal data; retain them only for documented support, security, legal or grievance purposes and handle rights requests under applicable law. Records held independently by external providers require provider-specific review/escalation. The support inbox must be verified as operational and monitored.

| Contact-number reveal preference cookie | Remember that the visitor requested phone-number display | 30 days, only if the visitor checks the separate remember-choice checkbox; stores only a 1 flag, not the number; cleared by Hide action |
