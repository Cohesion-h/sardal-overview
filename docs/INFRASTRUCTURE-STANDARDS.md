# Infrastructure Standards — Consultation Brief

**To:** ICTC / CITRA / Relevant Kuwait Government IT Authorities
**From:** Cohesion Holding (Sardal Project)
**Date:** 2026-05-14
**Contact:** Hamad Alotaibi (Founder)
- Email: cohesionkw@gmail.com
- Phone: +965 5117 9990

## Purpose

This brief requests official guidance and written recommendations from government IT authorities regarding infrastructure standards, data residency, security, and approved hosting providers for deployment of the Sardal system (Sovereign Arabic-Islamic AI Operating System). Sardal will be delivered as part of government contracts and must comply with national digital sovereignty objectives.

## Executive summary

Cohesion Holding intends to deploy Sardal for government and critical national use-cases. Before finalizing infrastructure vendor selection and system architecture, we request government clarification on:

1. Approved data center facilities (government-owned or government-approved regional centers).
2. Mandatory data residency / cross-border data transfer restrictions for AI systems and personal data.
3. Required encryption standards, key management rules, and approved vault/key management providers.
4. Acceptable cloud providers (if any) and any required attestations or certifications.
5. Network and integration security requirements for connecting to government systems (APIs, central bank, CITRA services).
6. Audit, logging, and retention policies for government-held data.
7. Any procurement or approval process required prior to signing hosting/operation contracts.

## Deployment contexts & risks

Sardal will operate in the following contexts:

- Production deployments for government agencies (sensitive and regulated datasets).
- Research/test environments for R&D (no production data stored in dev/test).
- Integrations with central government systems (CITRA, CBK, Ministry systems).

Risks to address:
- Data exfiltration or unauthorized access if hosted in non-approved jurisdictions.
- Non-compliance with government rules resulting in contract delays or invalidation.
- Use of third-party managed keys or vendor-hosted secrets that violate residency rules.

## Requested clarifications & specific questions

Please provide written guidance on the following items (numbered for response):

1. Data residency
   - Are there mandatory data residency requirements for AI systems serving government agencies? If yes, which classes of data MUST remain in Kuwait (e.g., personal data, metadata, model weights, logs)?
   - Are there permitted exceptions for anonymized or aggregated datasets to leave the jurisdiction under strict controls?

2. Approved hosting locations & facilities
   - Does the government maintain a list of approved data centers (Kuwait-run or certified regional facilities)? Please provide contact points and technical standards (Tier, certifications).
   - If no official list exists, what is the approval process for a private or regional data center to be authorized for government workloads?

3. Cloud provider policy
   - Is the use of international commercial cloud providers (AWS, Azure, Google Cloud) permitted for any Sardal components? If so, which components (non-sensitive analytics, model training, backups) and under what controls?
   - Are there specific contractual terms or attestations (e.g., customer-managed encryption keys, contractual data residency clauses) required from cloud providers?

4. Encryption & key management
   - Minimum encryption standards for data at rest and in transit (e.g., AES-256, TLS 1.3).
   - Are hardware security modules (HSM) required for key storage for government deployments? If yes, do you require HSMs to be located in-country?
   - Are government-managed KMS/HSM services available for approved projects (contact and onboarding steps)?

5. Identity, access management & operations
   - Requirements for user authentication (MFA, SSO, government identity federation).
   - Privileged access rules for operators, engineers, and vendors (just-in-time, least privilege, break-glass procedures).
   - Requirements for vulnerability management, patching cadence, and change control approvals.

6. API & integration security
   - Standards for integrating Sardal with government systems (mutual TLS, IP allowlisting, signed requests).
   - Logging and audit trail requirements for integration calls and data access.

7. Monitoring, logging & retention
   - Required retention periods for logs, access records, and audit trails for government contracts.
   - Requirements for where logs must be stored and whether they can be exported for analysis outside Kuwait.

8. Certifications & compliance
   - Which certifications are required or recommended for data centers and service providers (e.g., ISO 27001, SOC 2, local government accreditation)?
   - Are there special compliance requirements for AI systems (model auditability, explainability, human-in-the-loop controls)?

9. Disaster recovery & business continuity
   - Acceptable DR site locations and recovery time objectives (RTO) and recovery point objectives (RPO) for critical government workloads.
   - Any mandated failover / switchover constraints (e.g., cannot failover across certain borders without approval).

10. Procurement & approval workflow
   - Steps required from Cohesion Holding to obtain formal approval for the selected infrastructure and vendor contracts prior to signing.
   - Expected timelines for approval, required documents, and contact points.

## Proposed initial architecture (for government review)

We propose the following modular architecture options and request government feedback on acceptability:

Option A — Government-Hosted (Preferred)
- Production compute and storage hosted in government data center in Kuwait.
- Model weights and sensitive datasets remain in-country.
- Use government-managed HSM/KMS for keys.
- Direct private network link (VPN/MPLS) between government networks and Sardal hosts.
- Vendor staff operate under privileged access rules and on-site controls.

Option B — Regional Sovereign Cloud
- Production hosted in a government-approved regional data center (UAE / KSA / Egypt) with data residency agreements.
- Customer-managed encryption keys; HSM located in approved region.
- Strict contractual clauses preventing data export outside approved regions.

Option C — Hybrid (Non-Sensitive Workloads Offloaded)
- Sensitive workloads (inference for government datasets) in-country; heavy model training on approved regional facility under data handling contract.
- All backups encrypted with in-country keys; model checkpoints only moved after anonymization and approval.

## Proposed timeline & next steps

- Week 0–1: Government receives this brief and assigns point of contact.
- Week 1–3: Clarification responses from ICTC/CITRA + optional technical Q&A session.
- Week 3–5: Cohesion prepares vendor short-list based on recommendations and submits approval request.
- Week 6–8: Government review and formal approval (timeline subject to agency processes).

## Attachments & references

- Link to full Sardal Legal & Infrastructure policy (docs/01-legal-framework.md)
- Proposed operator security playbook (available upon request)
- Draft contract clauses for data residency, KMS, and auditability (available upon request)

## Decision/request

Cohesion Holding requests:
1. Written guidance addressing questions 1–10 above.
2. A named technical contact (email + phone) for follow-up Q&A and architecture review.
3. Any existing forms, templates, or procurement checklists required for infrastructure approval.

We appreciate your support and look forward to aligning Sardal's infrastructure with Kuwait's national digital sovereignty objectives.

---

Cohesion Holding
Founder: Hamad Alotaibi
Email: cohesionkw@gmail.com
Phone: +965 5117 9990
