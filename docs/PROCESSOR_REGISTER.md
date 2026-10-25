# FlyThe BG — Processor / Third-Party Register

Updated: 2026-10-25

This register is an engineering inventory, not a substitute for provider contracts or legal review.

| Provider / system | Current use observed in repository | Personal-data role | Website consent gate |
|---|---|---|---|
| Cloudflare Workers / Assets | Hosting, routing, API execution and static delivery | Infrastructure / processor where applicable; may receive IP address, request headers/metadata, timestamps and security signals | Strictly necessary for core service |
| Hugging Face Space / Gradio | Protected background-removal processing route | Processing provider for selected images and technical request information sent for Remove Background; transient runtime files/logs depend on actual configuration | Tool-specific processing notice/affirmative action; not a marketing-cookie consent |
| Google advertising entry in ads.txt | ads.txt contains a Google publisher entry; this alone does not prove a runtime ad script is active | No runtime advertising provider is assumed solely from this file | Any actual optional advertising/measurement technology must be reviewed and gated before activation |
| Google Fonts | External font files referenced by the site shell | Receives normal network/request metadata when fonts are fetched | Required by current page shell; assess self-hosting or transfer/privacy needs |
| CloudFront media-asset distribution | Serves externally hosted page media assets referenced by the application | Receives normal network/request metadata when assets are fetched | Required for those assets; assess whether to self-host |
| GitHub public API | Used by the application to display a public repository statistic | Receives normal request metadata; no GitHub token is intentionally sent by the browser | Feature request; document if removed or replaced |
| Support mailbox provider | Processes incoming/outgoing email sent to the public support address | Receives email addresses, message content and attachments a sender includes | Used when someone contacts the project; identify actual provider and configure retention |
| Analytics provider | No runtime analytics provider is intentionally enabled by the current source bundle reviewed for this change | None intentionally enabled by this control layer | Analytics category; verify the actual production bundle before claiming inactive |
| Affiliate/referral provider | No specific affiliate network is currently asserted by the website | None currently enabled by this control layer | Affiliate category |

| FlyThe BG contact-details endpoint | Same-origin POST /api/contact-details returns the operator phone number from Worker secret CONTACT_PHONE after the page's explicit acknowledgement flow | Cloudflare infrastructure processes request metadata; response is marked no-store and the number is not embedded in the client bundle | Explicit safety acknowledgement; optional remembered state uses the first-party flythebg_contact_reveal cookie. This is not authentication/access control |
| Contact preference cookie | First-party cookie flythebg_contact_reveal with value 1 and a 30-day expiry | Stores only that the visitor chose to remember the phone reveal state, not the phone number | Set only when the visitor checks the optional remember-choice checkbox and reveals the number; Hide action clears it |

## Activation rule

Before adding a runtime third-party script, pixel, SDK, referral identifier, or advertising tag:
1. name the provider in the privacy/cookie notice;
2. document its purpose and data categories;
3. document international processing/transfer considerations;
4. review its contractual/privacy terms;
5. connect it to the correct consent category;
6. verify that rejection prevents its optional activation;
7. document retention and deletion behavior.

Do not treat ads.txt as proof that advertising cookies or tracking are active.


## Consent preference storage

The current consent manager stores consent choices in browser localStorage only. It clears the legacy first-party consent cookie from earlier versions and no longer writes that cookie on preference changes. There is no server-side consent ledger, so do not rely on this record as an immutable audit proof.


## Consent preference storage

The current consent manager stores general privacy choices in browser localStorage only. It clears the legacy first-party consent cookie from earlier versions and no longer writes that cookie on general preference changes. There is no server-side consent ledger, so do not rely on this record as immutable audit proof.
