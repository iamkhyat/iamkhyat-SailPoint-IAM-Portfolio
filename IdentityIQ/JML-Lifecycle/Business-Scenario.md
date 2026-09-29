# JML Lifecycle — Business Scenario

## Setting the scene

Picture a mid-to-large organization — finance or healthcare is a common example, since both tend to have strict compliance requirements — with somewhere north of 5,000 employees spread across HR, IT, Finance, and Operations, and 20+ applications in play: Active Directory, an ERP, email, an HRMS, and the usual long tail of smaller systems.

## What's actually happening today

Access management is still manual. IT creates accounts by hand, requests come in over email, and there's no central record of who has what or why.

### Problems on the joiner side

New hires routinely wait one to three days for accounts to get created, which means they can't be productive on day one — sometimes they're sitting there for half a week unable to log into anything.

### Problems on the mover side

When someone changes department or role, the old access doesn't get cleaned up and the new access doesn't show up quickly. Over time, people accumulate access from every role they've ever held, which is exactly the kind of privilege creep auditors flag.

### Problems on the leaver side

This is the one that should keep a security team up at night — accounts staying active after someone's already left the company. That's not a theoretical risk; it's a direct path to unauthorized access and a compliance violation waiting to be found.

### And underneath all of it

No audit trail explaining who has access and why, which makes SOX or GDPR audits painful, and a steadily growing manual workload for IT that doesn't scale as the company grows.

## What the business actually wants

Automate the lifecycle so accounts get created on joining, updated on role change, and removed immediately on termination. Move to RBAC so access gets assigned based on department, title, and location instead of one-off requests. Tighten security and compliance with least privilege and a real audit trail. And, frankly, get IT out of the business of manually provisioning every single access change.

## The solution shape

HR becomes the single authoritative source. IdentityIQ picks up changes from HR and fires joiner/mover/leaver events automatically. Roles get assigned based on identity attributes instead of manual requests, provisioning runs automatically across connected systems, and certifications plus audit logging keep the whole thing honest over time.

## What changes after implementation

New hires get access on day one instead of waiting days. Role changes happen quickly instead of leaving stale access lying around. Terminated employees lose access immediately rather than weeks later. Orphan accounts drop off. The system becomes audit-ready instead of audit-scramble. And IT's manual workload drops significantly because most of what they used to do by hand now just happens.

## How I'd describe this scenario in an interview

"In a typical enterprise, manual access management leads to delayed onboarding, accumulated excess access, and real compliance risk on the leaver side. Automating JML with IdentityIQ — using HR as the authoritative source — closes all three gaps: fast onboarding, clean role transitions, and immediate access removal when someone leaves."

## The underlying point

JML isn't just a technical configuration exercise. Done right, it's a business-critical process that protects productivity, security, and compliance all at once — and it's usually the first thing I'd point to as evidence that an IAM implementation is actually working, not just installed.
