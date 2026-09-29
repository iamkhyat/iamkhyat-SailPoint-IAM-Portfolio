# JML Lifecycle — Execution Flow

![JML Lifecycle Flow](../../Diagram/jml-lifecycle-flow.svg)

## What this is

This is the detailed, step-by-step version of how a JML event actually moves through IdentityIQ — from HR sending over a data change, all the way to access actually showing up (or disappearing) in a target system.

## The scenario

HR is the authoritative source. IdentityIQ consumes whatever HR sends and turns it into automated access decisions, rather than someone manually interpreting an HR change and filing tickets.

## What drives the flow

Aggregation pulls the data in, correlation matches it to an identity, lifecycle event detection figures out what kind of change this is, RBAC decides what access should look like, and the provisioning engine makes it real. The core idea I keep coming back to: any change in HR data eventually triggers a lifecycle event, and that event triggers an access change — there's no manual step required in between.

## Concepts in play

Aggregation tasks, the identity cube, correlation rules, lifecycle events, role assignment rules, provisioning plans, workflows, and task execution.

## Walking through it

**Step 1 — Data ingestion.** HR sends employee data over, via file or API, IdentityIQ runs an aggregation task against it, and the data lands in IdentityIQ as accounts.

**Step 2 — Identity correlation.** IdentityIQ tries to match incoming accounts to existing identities, usually using email or employee ID. If nothing matches, a new identity gets created — that's your joiner.

**Step 3 — Identity creation or update.** The identity cube gets created or refreshed, and attributes like department, title, manager, and location get populated.

**Step 4 — Lifecycle event detection.** This is really the decision engine of the whole process. A brand-new identity is a joiner. A changed attribute on an existing identity is a mover. A status flip to terminated is a leaver.

**Step 5 — Role assignment.** Attributes get evaluated against role assignment rules. Department equals Finance, you get the Finance role. Title equals Manager, you pick up the Manager role on top of that.

**Step 6 — Provisioning plan generation.** IdentityIQ builds a plan describing exactly what needs to change — which application, what operation, which entitlements to add or remove.

**Step 7 — Provisioning execution.** The provisioning engine actually does the work — creating an AD account, granting email access, pulling ERP access, whatever the plan calls for.

**Step 8 — Workflow execution.** Approvals (where required), notifications, and error handling all run through workflows rather than happening ad hoc.

**Step 9 — Post-provisioning validation.** I check that the account actually got created, that entitlements landed correctly, and that the result — success or failure — got logged somewhere I can find it later.

## The three flows side by side

A **joiner** moves from HR data through aggregation to identity creation, role assignment, a provisioning plan, account creation, and finally working access.

A **mover** starts from an HR update, goes through aggregation to an identity update, drops the old role, picks up the new one, and ends with access updated across every connected system.

A **leaver** starts at termination, goes through aggregation, disables the identity, strips every role, generates a provisioning plan for removal, and ends with accounts disabled or deleted.

## Where this breaks

Aggregation not firing the lifecycle change it should (usually a scheduling problem or a stale HR feed), lifecycle detection getting it wrong (attribute mapping or a misconfigured status field), mover access not updating because role rules aren't actually evaluated dynamically or there's a caching issue, and straightforward provisioning failures from connectivity or connector misconfiguration.

## How I'd explain this out loud

"The lifecycle flow starts with aggregation from HR, moves through identity correlation and creation, and then IdentityIQ detects whether this is a joiner, mover, or leaver event based on what changed. Roles get assigned through RBAC, a provisioning plan gets generated, and access gets created or removed across target systems through connectors and workflows."

## The bigger point

This whole thing is event-driven, not schedule-driven in the naive sense — it's not "check everyone once a day," it's "react to whatever HR actually changed." That's what makes it scale and stay auditable as the organization grows.
