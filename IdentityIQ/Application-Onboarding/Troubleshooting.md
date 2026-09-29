# Application Onboarding — Troubleshooting

## Why this file exists

Onboarding rarely goes cleanly the first time. Something in the connector config is slightly off, the source data has quirks nobody mentioned, or provisioning works in testing but fails the moment it hits a real account. This is how I actually work through it when something breaks.

## My approach

The first thing I do is figure out which layer the problem is actually in — aggregation, correlation, or provisioning — because the fix looks completely different depending on where it sits. Chasing a provisioning error when the real problem is upstream in aggregation just wastes time.

## Tools I actually use

Task result logs, identity debug pages, and whatever connector-specific logs are available (for IIQ, that usually means digging through the server logs alongside the task results in the UI).

## How I work through it

1. Identify what kind of issue it looks like on the surface.
2. Check the connector — connectivity, credentials, configuration.
3. Validate the schema actually matches what the source is sending.
4. Re-run aggregation in isolation to see if the data comes through clean.
5. Review the logs for anything that points at a specific failure.
6. Fix and retry, one variable at a time rather than changing five things and hoping.

## The three buckets I usually find issues in

**Aggregation failure** — almost always a connector problem or bad credentials, occasionally a network path that got blocked after a firewall change nobody told IAM about.

**Correlation issue** — an attribute mismatch, most often the "unique" identifier not actually being unique, or being populated inconsistently across accounts.

**Provisioning failure** — usually a policy misconfiguration, or the service account not having the permission it needs on the target system even though the connection itself works fine.

## Interview framing

"My debugging approach is to isolate the layer first — is this aggregation, correlation, or provisioning — before I start changing configuration. Logs are non-negotiable; I don't guess at root cause without actually looking at what the system recorded."
