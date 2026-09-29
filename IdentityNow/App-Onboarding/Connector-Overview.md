# IdentityNow – Connector Overview

![IdentityNow Connector Architecture](../../Diagram/idn-connector-architecture.svg)

## The scenario

An enterprise running a mix of cloud and on-prem systems — Workday for HR, AD for the directory, Salesforce, ServiceNow — each storing its own copy of user accounts and permissions. The organization needs centralized visibility and automated access control across all of it, and connectors are the mechanism that actually makes that integration possible.

## Approach

IdentityNow treats every connected application as a "source," and connectors handle three things underneath that: authentication, aggregation (pulling data out), and provisioning (pushing changes back). The way I'd summarize it: source system, connector, IdentityNow — that's the chain, and each link matters.

## Concepts

Sources, connectors (SaaS-based vs. Virtual Appliance-based), aggregation, provisioning policies, identity profiles, API integration, and authentication methods like OAuth, basic auth, or token-based auth.

## The two connector types that matter most

**SaaS connectors** integrate directly through APIs with no extra infrastructure needed — think Salesforce, ServiceNow, Workday. These are the easy case.

**Virtual Appliance connectors** are needed for anything on-prem — AD, LDAP, internal databases — where the Virtual Appliance acts as a secure bridge between the cloud platform and systems that aren't internet-facing.

## How onboarding a source actually goes

1. Add the source in IdentityNow and pick the connector type.
2. Configure authentication — OAuth, an API token, or username/password depending on what the connector supports. Credential storage security matters more here than people initially think, since you're often dealing with a service account that has broad access.
3. Let IdentityNow discover the schema — account attributes like username and email, entitlement attributes like group memberships.
4. Set up the aggregation schedule, deciding what's full vs. incremental.
5. Configure identity correlation, usually against email or employee ID.
6. Enable provisioning operations and set the actual policies governing create/update/delete.

## What I've seen go wrong

**Authentication failures** — invalid credentials or expired tokens, more common than you'd expect with OAuth-based connectors since tokens silently expire. Fix is reconfiguring authentication and double-checking the API permissions actually granted.

**Aggregation failures** — API rate limits or a wrong endpoint. Fix is checking logs first, then validating connectivity directly against the API.

**Missing attributes** — schema mapping that's off. Fix is going back through the schema configuration carefully rather than assuming the auto-discovery got everything right.

**Provisioning not working** — either disabled outright or misconfigured policy. Fix is confirming operations are actually enabled and the policy logic matches what you intended.

## Interview answer

"IdentityNow connects applications as sources, using API-based connectors for SaaS and a Virtual Appliance for anything on-prem. Connectors handle both aggregation and provisioning, which is really what lets IdentityNow centrally manage access across a mix of cloud and legacy systems without forcing everything onto one integration pattern."
