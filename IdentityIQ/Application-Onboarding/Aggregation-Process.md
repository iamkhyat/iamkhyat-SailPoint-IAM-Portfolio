# Aggregation Process

## What it's for

Applications don't sit still. People get added, access changes, groups get renamed. IdentityIQ has to keep up with that or the data it's governing becomes stale and, frankly, useless. Aggregation is the mechanism that keeps the picture current.

## Approach

I usually run a full aggregation first to establish the baseline — every account and entitlement the application currently has — and then move to scheduled incremental aggregations to pick up just the changes after that. Running full aggregation constantly on a large application is a good way to make your nightly job take six hours instead of twenty minutes, so incremental matters more than it sounds like it should.

## Concepts

Aggregation tasks, full aggregation, incremental aggregation. Worth knowing the difference well enough to explain it without hedging, because it comes up in almost every onboarding interview question I've gotten.

## Step by step

1. Configure the aggregation task against the application.
2. Run the full aggregation first to pull everything in.
3. Confirm the accounts actually landed in IdentityIQ correctly.
4. Switch to incremental aggregation on a schedule.
5. Make sure correlation runs after aggregation so new or changed accounts actually get linked to identities.

## What goes wrong in practice

- **No data comes back** — usually a connector or credential problem, sometimes a query/filter that's scoped too narrowly.
- **Duplicate accounts** — happens when correlation logic isn't tight enough, or when a source system reuses identifiers in a way nobody anticipated.
- **Performance problems** — large applications with full aggregation running too frequently will eventually start timing out or slowing down other scheduled tasks.

## Interview talking points

Full vs. incremental aggregation, how I'd tune performance on a large application, and how scheduling decisions affect both data freshness and system load. I try to frame this as a tradeoff conversation rather than reciting definitions — that's usually what separates a junior answer from a senior one.
