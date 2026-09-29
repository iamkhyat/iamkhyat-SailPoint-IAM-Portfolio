# Certifications (Architect View)

## The scenario

An organization needs to comply with frameworks like SOX and GDPR, and the usual symptoms of not doing this well are excess access piling up, orphan accounts surviving long past when they should have been removed, and audit findings that trace back to both.

## Core principle

I'd frame the goal here as continuous access governance — certifications aren't a once-a-year cleanup exercise, they're a recurring control that has to actually run on a cadence and produce real evidence each time.

## Strategy

**Campaign types** — manager certifications for reviewing a user's overall access, application owner certifications for reviewing access at the app level. Which one makes sense depends on who actually has the context to make a good decision.

**Scope design** — high-risk applications get reviewed more frequently, lower-risk ones on a more relaxed cadence. Treating every application identically wastes reviewer attention on low-risk access while under-reviewing the stuff that actually matters.

## Decisions I'd defend

Risk-based certification, mainly because it cuts down reviewer fatigue — nobody does a careful job reviewing their three-hundredth low-stakes item of the week. And matching reviewer type (manager vs. owner) to the kind of access being reviewed, rather than defaulting to manager certification for everything regardless of whether the manager actually understands the access in question.

## Where this fails

Reviewer overload from too many items at once, ineffective reviews from reviewers lacking real context on what they're approving, and remediation delays when a revoke decision doesn't translate cleanly into a provisioning action.

## Architect-level answer

"I design certification campaigns around risk rather than blanket coverage — high-risk applications get reviewed more often, and reviewer assignments are matched to whoever actually has the context to make a real decision. The goal is reducing fatigue without sacrificing accountability."

## Files here

- `Campaign-Setup.md` — the practical steps for standing up a campaign
- `Reviewer-Workflow.md` — what the review experience looks like
- `Remediation.md` — turning a revoke decision into actual access removal
