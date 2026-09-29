# Application Onboarding — Why It Matters

## The scenario

Most organizations I've worked with end up managing access to AD, a couple of databases, and a growing pile of SaaS tools completely separately. There's no shared definition of "this is an application" — each one has its own admin, its own process, and its own blind spots. The security team finds out about half of it during an audit, usually the hard way.

## The approach

The fix is conceptually simple, even if the execution takes work: treat every system, no matter how different it is technically, as a managed application inside IdentityIQ. Standardize the onboarding steps so a database and a SaaS app go through the same general process, and let IdentityIQ become the single place governance actually happens.

## Concepts in play

Applications, connectors, schema, aggregation — these four show up in basically every onboarding conversation. An "application" in IdentityIQ terms isn't really the software itself, it's the connector configuration plus the schema that tells IdentityIQ how to read accounts and entitlements out of it.

## How it plays out step by step

1. Figure out what kind of system you're actually dealing with — is it LDAP-based, does it expose a REST API, is it a flat database table?
2. Pick the connector that matches (LDAP, JDBC, REST — occasionally a flat file connector for legacy systems that nobody wants to rebuild).
3. Configure the connection — endpoint, credentials, whatever the connector needs.
4. Define the schema so IdentityIQ knows what an account record and an entitlement look like for this app.
5. Test connectivity before running anything real.
6. Run an aggregation and actually look at what came back.

## Where this trips people up

- **Connection failures** — usually credentials, sometimes a firewall rule that was never opened for the IdentityIQ server.
- **Unsupported APIs** — older or oddly-built systems sometimes need a custom connector, which is its own project.
- **Schema mapping mistakes** — mapping the wrong source field to the wrong IdentityIQ attribute is subtle and doesn't always throw an obvious error; it just quietly produces bad data.

## Interview angle

If someone asks why onboarding matters at all, my answer is usually: every application you don't onboard is a blind spot. It's not really about the technical integration — it's about closing the gap between "we think we know who has access" and "we can actually prove it."
