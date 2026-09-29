# Audit & Compliance Considerations

## Why this matters

Certifications exist partly to keep access clean, but a huge part of their actual purpose is producing evidence — something an auditor can look at and say "yes, this organization actually reviews access regularly and acts on what it finds." Without that evidence trail, even a well-run certification program looks, from the outside, indistinguishable from one that never happened.

## The compliance pressure behind this

SOX, GDPR, and plenty of internal security policies all expect the same basic things: proof that access gets reviewed, a record of who decided what, and confirmation that revoked access was actually removed.

## My approach

Keep audit logs intact and untouched, track every certification decision (not just the final outcome but who made it and when), and be ready to produce reports without having to reconstruct anything after the fact.

## Concepts

Audit logs, certification reports, SoD policies, compliance tracking.

## How it flows

1. A campaign runs to completion.
2. Decisions get recorded as they're made.
3. Revocations get processed through remediation.
4. Audit logs capture all of it.
5. Reports get generated for whoever's asking — internal audit, external auditor, security leadership.

## Where it breaks

- **Missing logs** — usually a misconfiguration somewhere in logging settings, and you don't find out until you actually need the evidence.
- **Incomplete campaigns** — a campaign that never closes out properly is a compliance risk in itself, even if every individual decision in it was fine.
- **No evidence to show** — the worst version of this; the review may have happened, but if you can't prove it happened, an auditor treats it as if it didn't.

## Interview answer

"Certifications support compliance by creating a documented, repeatable review cycle — not just a one-time access cleanup. I make sure the audit trail is intact from decision through remediation, because the evidence is honestly as important as the access change itself when it comes to passing an audit."
