# FlyThe BG — Privacy Operations Runbook

Updated: 2026-10-24

This is an operational engineering runbook, not legal advice.

## Privacy request intake

Primary contact: support@flythebg.com (verify that this is a live, monitored mailbox before production claims rely on it).

Requests to classify:
- access / confirmation of processing
- correction or update
- erasure
- consent withdrawal
- grievance
- child-data concern
- security or personal-data incident
- processor/privacy disclosure question

Do not ask a requester to email an uploaded photograph when a safer description or secure transfer method is sufficient.

## Intake record

For each request, record only what is needed to manage the request:
- received timestamp
- request category
- requester's contact channel
- status
- responsible operator
- outcome and completion timestamp
- relevant legal/policy basis where applicable

Do not store uploaded media in the request ledger.

## Consent

The website's consent UI records a consent ID, policy version, timestamp, source and category choices in browser storage. This is a user-visible preference record, not an immutable audit ledger.

If a processing activity requires stronger evidence, implement a server-side consent ledger before relying on that evidence operationally.

## Children

A checkbox is not treated as verifiable parental/legal-guardian consent. If a request knowingly involves children's personal data, pause the processing decision and route it for manual compliance review unless an applicable documented mechanism/exemption has been established.

## Provider register

Before enabling analytics, advertising, affiliate attribution, email processing, or any new processor:
1. record the provider;
2. document the data categories and purpose;
3. identify where processing occurs;
4. review the provider's contractual/privacy terms;
5. confirm the website consent gate required for the activity;
6. document retention/deletion behavior;
7. record the owner responsible for the integration.

## Review cadence

Review this runbook whenever a new processor, advertising platform, analytics tool, affiliate network, upload workflow, or material privacy-policy change is introduced.


## Requests when there is no account system

Do not ask a requester to log in or to delete a nonexistent account. Classify the request and search only the systems relevant to the stated purpose: support mailbox/correspondence, any relevant security records controlled by the project, and the relevant provider escalation route where data may be held by Cloudflare or Hugging Face/Gradio. Explain when the requested upload/result is not retained by FlyThe BG and therefore cannot be exported or remotely deleted by the project. Distinguish that from actual retained personal data; apply correction/erasure or other rights to that data where the law requires it. Use proportionate verification and do not collect extra identification documents by default.

Before launch, confirm that the support mailbox is monitored, record a responsible reviewer, test the request and escalation process, and periodically check whether the live contact details still work.

## Consent storage

The consent manager stores choices in browser localStorage. It does not create a server-side ledger, and it no longer mirrors choices to a first-party consent cookie. Do not call the browser record immutable evidence. The script expires the legacy consent cookie set by earlier versions when it loads; the first request that fetches the updated script may still carry a legacy cookie that was already present in the browser.
