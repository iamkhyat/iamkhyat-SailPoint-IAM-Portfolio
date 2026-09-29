# Username Logic (Transforms)

## The scenario

New users need a username that's both consistent in format and guaranteed unique — and source systems don't reliably hand you one ready-made.

## Approach

Combine identity attributes through transform rules, and build in an explicit uniqueness check rather than assuming a naming pattern will never collide.

## Concepts

Transforms, identity attributes.

## Steps

1. Pull the attributes needed — typically first name and last name.
2. Apply the naming logic (something like `firstName.lastName`, lowercased).
3. Check uniqueness and append a number or similar suffix if a collision turns up.

## What goes wrong

Duplicate usernames when the uniqueness check isn't actually wired in, and missing attributes when a source doesn't reliably populate first or last name.

## Interview talking points

How transforms get used practically for something as simple-sounding as a username, and why uniqueness has to be handled explicitly rather than assumed.

## Takeaway

This is a small piece of the platform, but it's a good example of how automation removes a class of manual error — nobody has to remember to check whether "jsmith" already exists before creating the account.
