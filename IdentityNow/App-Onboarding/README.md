# IdentityNow – Application Onboarding (Architect View)

![IdentityNow Connector Architecture](../../Diagram/idn-connector-architecture.svg)

## The scenario

A large enterprise running Workday as HR, AD for authentication, Salesforce for CRM, ServiceNow for ITSM, plus the usual long tail of SaaS and legacy applications. The pain points are familiar: identity data scattered across systems that don't agree with each other, provisioning delays running two to five days, and audit findings tracing back to orphan accounts nobody caught in time. The goal is a cloud IAM onboarding model that's actually scalable and secure rather than just functional.

## Core principle

I think of IdentityNow as fundamentally three layers stacked on top of each other: aggregation, correlation, and governance. Onboarding decisions need to be made with all three in mind, not just whichever one is easiest to configure first.

## Source classification

I classify every source as one of three things. An **authoritative source** like Workday drives the identity lifecycle directly. A **managed source** like AD or Salesforce supports provisioning but doesn't define identity itself. An **entitlement source** like a database or SaaS app exists purely for access governance. Keeping this distinction clear avoids conflicting identity data and keeps ownership unambiguous — without it, you get situations where two systems both think they're authoritative for the same field.

## Connector strategy

SaaS applications get API-based connectors — fast, scalable, no extra infrastructure. On-prem systems need a Virtual Appliance acting as a secure bridge between cloud and on-prem. Genuinely custom systems sometimes need REST or web service integration built specifically for them. The trade-off is straightforward: API connectors are quick to stand up, while VA-based connectors are necessary for legacy systems but add real infrastructure overhead.

## End-to-end flow, as I'd design it

1. Onboard the source and decide whether it's authoritative or managed.
2. Standardize schema across sources so the same logical attribute doesn't end up named five different things.
3. Run full aggregation for the initial load, then switch to incremental for ongoing sync.
4. Build correlation logic around a stable primary key — usually email or employee ID — with a sensible fallback for when that key is missing or inconsistent.
5. Map identity profiles, which drive lifecycle state and identity creation.
6. Model access through access profiles rather than traditional roles.
7. Enable provisioning only where it's actually needed, rather than turning it on everywhere by default.

## Decisions I'd defend

A single authoritative source to avoid identity conflicts. Email as a correlation key where it's reliable, knowing the trade-off — easy to use but risky if it changes, versus employee ID which is more stable but not always available from every source. Incremental aggregation for performance and to avoid hammering SaaS APIs. And limiting provisioning scope deliberately, since not every application needs it and every enabled provisioning path is one more thing that can fail.

## Failure scenarios I plan around

Duplicate identities from weak correlation logic (fixed with composite keys rather than relying on a single field), aggregation overload on large datasets (fixed by moving to incremental), API throttling against SaaS rate limits (fixed by staggering schedules instead of running everything at once), and provisioning failures from endpoint issues (handled with retry logic and alerting rather than silent failure).

## Architect-level answer

"When I onboard an application into IdentityNow, I start by classifying it as authoritative or managed. From there I work through schema normalization, correlation logic built on stable identifiers, and aggregation with incremental updates layered on top of an initial full load. I keep provisioning scope deliberately limited and model access through access profiles for the sake of long-term scalability."

## Files in this folder

- `Connector-Overview.md` — connector types and how they actually integrate
- `Aggregation-Flow.md` — how data moves from source into IdentityNow
- `Access-Model.md` — access profiles and entitlements in practice
