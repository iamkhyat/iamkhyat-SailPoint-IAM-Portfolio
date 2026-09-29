# Remediation Process

## What this covers

A revoke decision in a certification campaign is meaningless if it doesn't actually remove access. Remediation is the bridge between "a reviewer said no" and "the access is actually gone from the target system." This is where I've seen otherwise well-designed certification programs quietly fail — the decision gets logged, but nothing happens downstream.

## The scenario

After a campaign closes, some access gets approved and some gets revoked. Revocation has to turn into enforcement automatically — you can't rely on someone remembering to go remove it manually a week later.

## Approach

Convert every revocation decision into an actual provisioning action, make sure that enforcement happens automatically rather than depending on a follow-up task, and track remediation status so you can prove (to an auditor or to yourself) that it actually happened.

## Concepts

Revocation requests, provisioning plans, workflows, connectors.

## Steps

1. Reviewer selects "revoke" on an item.
2. IdentityIQ generates a revocation request from that decision.
3. A provisioning plan gets created from the request.
4. The provisioning engine executes the removal against the target system.
5. Status gets updated so there's a record the removal actually completed.

## Where this goes wrong

- **Revocation logged but never executed** — usually a downstream provisioning failure that nobody caught because the certification itself showed as "complete."
- **Delayed removal** — a workflow bottleneck somewhere between the decision and the actual provisioning action.
- **Partial removal** — happens when the entitlement mapping doesn't fully capture everything that should come off, leaving a sliver of access behind.

## Interview answer

"Remediation is the part of certifications people undervalue. A revoke decision that doesn't reliably turn into a provisioning action isn't really governance — it's just a record that someone clicked a button. I always want to verify that the loop closes, not just that the decision got captured."
