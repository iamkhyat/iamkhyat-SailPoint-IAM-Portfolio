# Remediation

## What this covers

What actually happens after a reviewer decides to revoke access in an IdentityNow certification.

## Approach

Automate the removal rather than relying on a manual follow-up step, and make sure the whole thing is auditable enough to satisfy compliance.

## Steps

1. A revoke decision gets made.
2. That decision triggers provisioning.
3. Access gets removed on the target system.

## What goes wrong

Provisioning failures that prevent the removal from actually completing, and delays between the decision and the action actually executing.

## Interview talking points

Why automated enforcement matters here — a revoke decision that doesn't reliably turn into removed access isn't really governance, it's just a recorded opinion.

## Takeaway

This step is critical for security. Certifications without reliable remediation just produce a paper trail of intentions, not actual risk reduction.
