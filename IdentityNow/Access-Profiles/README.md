# Access Profiles (Architect View)

![Access Profiles vs Roles](../../Diagram/idn-access-profiles.svg)

## The scenario

Picture an enterprise with 5,000+ entitlements spread across 200+ applications. Without a deliberate model, users end up with inconsistent access depending on who provisioned them and when, and a legacy IAM approach tends to spiral into role explosion — hundreds of near-duplicate roles that nobody can actually tell apart anymore. The goal in IdentityNow is to avoid repeating that mistake with a simpler access model suited to a cloud-first environment.

## The core principle

I think of access profiles as a simplified RBAC layer — a way to group entitlements into something business-friendly without recreating the full complexity of IdentityIQ-style role hierarchies.

## Design strategy

**Entitlement grouping** — group based on job function, application usage, and least privilege, not just whatever the source system happens to call things.

**Naming convention** — something like `APP_SALESFORCE_READ_ONLY` rather than a cryptic permission code. It looks like a small thing, but readable naming is what makes a certification campaign actually auditable instead of a guessing exercise for reviewers.

**Assignment strategy** — manual assignment for genuine exceptions, rule-based assignment for anything that should follow a standard pattern. Leaning too heavily on manual assignment is how you end up rebuilding the same access-sprawl problem you were trying to avoid.

## Key decisions I'd defend

**Avoiding role explosion** — keep profiles broad enough to be manageable but still controlled, rather than creating a new profile for every minor variation.

**Balancing granularity** — too broad and you risk granting more than someone needs; too granular and the whole model becomes too complex to maintain or certify properly. I aim for a balanced middle rather than optimizing hard for either extreme.

## Where this fails if you're not careful

Overlapping profiles that quietly grant the same access through two different paths, and naming that's inconsistent enough to confuse auditors during a review.

## Architect-level interview answer

"I design access profiles by grouping entitlements around job function and actual application usage, and I deliberately avoid role explosion by keeping the model broad-but-controlled. The balance between granularity and simplicity is really the core design tension in cloud IAM, and I'd rather lean toward simplicity since that's what keeps the model auditable over time."

## Files in this folder

- `Profile-Design.md` — the practical steps for building a profile
- `Role-vs-AccessProfile.md` — how this compares to IdentityIQ's role model
