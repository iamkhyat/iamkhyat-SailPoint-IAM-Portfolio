# IdentityNow – Access Model

## The scenario

Users need access spread across finance tools, HR systems, and CRM, and that access has to be both understandable to a business reviewer and governable through certifications — not just a list of raw permission codes nobody outside IT can interpret.

## Approach

IdentityNow steps away from deep RBAC hierarchies and instead groups entitlements into access profiles. I'd describe it simply as: an access profile is a grouped, business-friendly bundle of entitlements rather than a deep role tree.

## Concepts

Entitlements, access profiles, identity profiles, lifecycle states.

## Step by step

**Entitlement discovery** — pulled in via aggregation from each source, things like AD groups or Salesforce roles.

**Access profile creation** — related entitlements get grouped together and given a name a non-technical reviewer would actually recognize.

**Assignment** — profiles get assigned to identities either manually (for exceptions) or through rules (for anything standard).

**Provisioning** — assigning an access profile is what actually triggers the provisioning action on the target system.

## The flow in short

Entitlements get grouped into access profiles, those profiles get assigned to identities, and that assignment drives provisioning.

## What goes wrong

Overlapping profiles that grant the same access two different ways, poor grouping that doesn't reflect how access is actually used, and a lack of naming standards that leaves reviewers guessing what a given profile actually does.

## Interview answer

"IdentityNow uses access profiles instead of traditional roles — grouping entitlements into business-friendly units that can be assigned and provisioned without the overhead of a deep role hierarchy. It's a simpler model, which is exactly the point in a SaaS-heavy environment where you want governance to stay manageable as the number of applications grows."
