# SailPoint IdentityIQ Portfolio

## Objective
This section demonstrates my hands-on understanding of SailPoint IdentityIQ by simulating real-world IAM implementations across the full identity lifecycle.

It covers core IAM capabilities including lifecycle management, application onboarding, access certifications, and troubleshooting.

---

## Business Context
In a typical enterprise:
- Multiple applications exist across departments
- Access is often managed manually
- This leads to:
  - Security risks
  - Compliance issues
  - Lack of visibility

IdentityIQ solves this by providing centralized identity governance and automation.

---

## IAM Design Approach

This portfolio is structured to reflect how IdentityIQ is implemented in real-world environments:

1. Establish identity lifecycle (JML)
2. Onboard applications into IdentityIQ
3. Model access using roles (RBAC)
4. Enable provisioning and access requests
5. Govern access via certifications
6. Handle failures using structured troubleshooting

---

## Project Structure

### 🔹 JML Lifecycle
`JML-Lifecycle/`

Focus:
- Joiner-Mover-Leaver automation
- Identity creation and lifecycle events
- Role-based access assignment

Key Concepts:
- Identity Lifecycle
- RBAC
- Provisioning workflows

---

### Application Onboarding
`Application-Onboarding/`

Focus:
- Integrating applications into IdentityIQ
- Schema design and aggregation
- Entitlement modeling and provisioning

Key Concepts:
- Connectors (JDBC / REST / LDAP)
- Aggregation
- Correlation
- Provisioning policies

---

### 🔹 Certifications
`Certifications/`

Focus:
- Access review campaigns
- Reviewer workflows
- Compliance and audit readiness

Key Concepts:
- Certification campaigns
- Access reviews
- Remediation process

---

### Troubleshooting
`Troubleshooting/`

Focus:
- Debugging real-world IAM issues
- Aggregation failures
- Provisioning errors
- Certification issues

Key Concepts:
- Logs and debugging
- Root cause analysis
- Issue resolution

---

## End-to-End IdentityIQ Flow

This repository collectively represents a complete IAM lifecycle:

1. Identity created (JML)
2. Application onboarded
3. Accounts aggregated
4. Identity correlated
5. Access modeled (roles)
6. Provisioning enabled
7. Access requested by users
8. Lifecycle changes handled (JML)
9. Access reviewed (certifications)
10. Issues resolved (troubleshooting)

---

## How to Explain This in Interview

If asked:
“What have you worked on in IdentityIQ?”

You can say:

“I built a structured IAM portfolio where I covered the full IdentityIQ lifecycle—from JML automation to application onboarding, access certifications, and troubleshooting. Each module reflects real-world implementation scenarios, design decisions, and common challenges.”

---

## Key Strengths Demonstrated

- Strong understanding of IdentityIQ architecture
- End-to-end IAM lifecycle knowledge
- Practical approach to onboarding and provisioning
- Real-world troubleshooting mindset
- Focus on compliance and governance

---

## Notes for Reviewers

- Each folder represents a real IAM use case
- Documentation is simplified for clarity and interviews
- Focus is on design thinking, not just configuration

---
