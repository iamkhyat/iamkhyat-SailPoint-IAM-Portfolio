# Access Profile Design

## The scenario

A large enterprise with thousands of entitlements spread across multiple departments needs an access model simple enough that people outside IT can actually understand and review it.

## Approach

Group entitlements by job function, department, and how the application is actually used — not just by whatever the source system's native grouping happens to be.

## Concepts

Access profiles, entitlements, least privilege.

## Steps

1. Analyze the entitlements actually available.
2. Group them logically based on real usage patterns.
3. Build the profile.
4. Validate it with the business side before rolling it out — IT's idea of a sensible grouping doesn't always match what the business actually does day to day.

## Common issues

Too many profiles ending up created (which just re-creates role explosion under a different name), and grouping that doesn't actually reflect how access is used in practice.

## Interview talking points

The tension between role explosion and oversimplification, and why getting business alignment matters as much as the technical grouping itself.

## Takeaway

Design choices here directly affect how scalable the model is later. Keeping profiles simple, even at the cost of some granularity, tends to pay off when certification time comes around.
