# Entitlement Mapping

![Entitlement Mapping to RBAC](../../Diagram/entitlement-mapping-rbac.svg)

## The problem

Applications hand you raw, technical entitlements — `READ_DB_042`, `GRP_FIN_AP_L2`, things that mean nothing to a manager approving access. Business owners don't think in permission codes, they think in "this person needs finance access" or "this person needs to be able to approve invoices." Entitlement mapping is the translation layer between those two worlds.

## Approach

I group raw entitlements logically first — figure out which permission codes actually cluster together functionally — and then build roles (RBAC) on top of those groupings. The goal is access management that a non-technical reviewer can actually look at and make a sensible decision on, instead of squinting at a permission code and approving it because revoking it feels risky.

## Concepts

Entitlements, roles, RBAC. The distinction between an IT role (a technical bundle of entitlements) and a business role (something tied to a job function) matters more here than the textbook definition suggests.

## Steps

1. Analyze what entitlements an application actually has and what each one really does.
2. Group them logically based on function, not just naming convention.
3. Build IT roles from those groupings.
4. Map IT roles up to business roles that reflect actual job functions.
5. Assign users to roles instead of individual entitlements wherever possible.

## Common failure modes

- **Role explosion** — creating a new role for every minor variation in access until you have more roles than users, which defeats the entire point of RBAC.
- **Bad grouping** — bundling entitlements together that don't actually belong together just because they showed up in the same aggregation batch.
- **Overlapping roles** — multiple roles granting the same entitlement, which makes certifications confusing and SoD analysis basically impossible.

## How I'd talk about this in an interview

"RBAC only works if the roles actually map to something real in the business. I spend more time on the grouping and naming than on the technical mapping itself, because a role nobody understands is a role nobody can review properly during a certification."
