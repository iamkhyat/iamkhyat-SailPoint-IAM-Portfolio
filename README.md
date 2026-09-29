# SailPoint IAM Portfolio

Hi, I'm Binaya — a SailPoint engineer with 4+ years working in IdentityIQ and, more recently, IdentityNow. I put this repo together during a stretch between roles, mainly to keep my hands on the tools and to have something concrete to point to when people ask "what have you actually built?"

Most of what's here isn't a screenshot of a single client project (I can't share that, obviously — NDAs), but a set of lab builds and write-ups that mirror the exact problems I've solved on the job: onboarding a new application, automating joiner-mover-leaver, running certification campaigns, and chasing down the kind of provisioning failures that show up at 2 AM during a production aggregation run.

## Why this exists

I spent a chunk of my gap rebuilding a home lab around IdentityIQ and exploring IdentityNow more deeply (most of my paid work had been IIQ-heavy, so IDN was the gap I wanted to close). Writing these notes forced me to actually explain *why* a design choice works, not just *that* it works — which, honestly, is closer to what an architect-level interview actually tests.

## What's in here

- **IdentityIQ/** — JML lifecycle automation, application onboarding, certifications, and troubleshooting, written the way I'd walk a teammate through it on a whiteboard.
- **IdentityNow/** — Access profiles vs. roles, source/app onboarding, transforms, and certification campaigns in the cloud platform.
- **Architecture-Overview.md** — the 30,000-foot view tying the IIQ pieces together end to end.

## A bit about me

SailPoint engineer, mostly IdentityIQ, increasingly comfortable with IdentityNow. I've spent most of my career around provisioning, certifications, RBAC design, and application onboarding — the stuff that doesn't show up in a sales deck but is 80% of what actually keeps an IAM program running. I'm currently looking for my next Senior IAM Engineer / IAM Architect role.

## Skills

SailPoint IdentityIQ, SailPoint IdentityNow (Identity Security Cloud), provisioning and lifecycle management, access certifications, RBAC and access governance, application onboarding (LDAP/JDBC/REST/SCIM connectors), REST APIs, JSON/XML, BeanShell rules, and a fair amount of log-diving when things go sideways.

## How I'd suggest reading this

Each folder is a self-contained topic — business problem, how I approached it, the steps, and the things that go wrong in practice. If you're interviewing me, the troubleshooting files are probably the most honest representation of what day-to-day work in this space actually looks like.
