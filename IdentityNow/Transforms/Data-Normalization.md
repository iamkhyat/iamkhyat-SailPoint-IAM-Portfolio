# Data Normalization

## The scenario

Different systems store the same conceptual data in different ways — department names that don't match between HR and AD, status codes that mean different things in different feeds. None of it lines up cleanly out of the box.

## Approach

Use transforms to normalize values into a consistent form before identity data depends on them downstream.

## Concepts

Transforms, identity profiles.

## Steps

1. Identify where the inconsistencies actually are.
2. Apply transform rules to fix them.
3. Confirm the data's actually standardized after the fact, not just assumed to be.

## What goes wrong

Inconsistent formats slipping through despite a transform being in place, and missing mappings for values nobody anticipated showing up in the source data.

## Interview talking points

Why data quality is foundational to everything else IAM does — it's easy to treat this as boring plumbing work, but it's usually where the real problems originate.

## Takeaway

Clean data is what makes accurate IAM possible. Skipping normalization doesn't save time — it just defers the problem to a much harder debugging session later.
