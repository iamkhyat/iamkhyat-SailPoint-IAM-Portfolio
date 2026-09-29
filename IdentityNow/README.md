# IdentityNow (SailPoint Identity Security Cloud)

## Where this fits

Most of my hands-on years have been in IdentityIQ, so this section is partly where I've been deliberately closing a gap — getting comfortable with how SailPoint's cloud platform does things differently. The two products solve the same underlying problem but make some genuinely different architectural choices, and I think being able to speak to both honestly is more useful than pretending they're interchangeable.

## The scenario IdentityNow is built for

Modern organizations run on SaaS — Workday for HR, Salesforce, ServiceNow, plus AD for the on-prem pieces that haven't gone away. Access ends up distributed across all of it, with no centralized control and the same compliance pressure as ever.

## How IdentityNow approaches it

Cloud-native by design, with sources doing the identity aggregation, access profiles standing in for the heavier role hierarchies IdentityIQ tends to use, API-driven provisioning, and governance that's meant to run continuously rather than as a periodic event.

## Concepts that come up constantly

Sources (the IdentityNow term for applications), identity profiles, access profiles, transforms, lifecycle states, certifications, and provisioning policies.

## What's covered in this section

App onboarding, access profiles, transforms, and certifications — covering roughly the same ground as the IdentityIQ section, but through IdentityNow's lens.

## How I'd describe it in an interview

"IdentityNow is SailPoint's cloud IAM platform. Identities get managed through sources, access gets modeled through access profiles instead of traditional role hierarchies, and governance runs through certifications and lifecycle states rather than periodic manual reviews."
