# Drafting Framework

## Recommended Document Structure

1. Title: Data Processing Agreement / 数据处理协议.
2. Preamble: relationship to `[XX Service Agreement] / [XX服务协议]`.
3. Definitions.
4. Roles of the Parties.
5. Scope and Documented Instructions.
6. Party B Processing Obligations.
7. Confidentiality.
8. Security Measures.
9. Data Subject Requests.
10. Personal Data Breach Notification and Assistance.
11. Sub-Processors.
12. Cross-Border Transfers and Remote Access.
13. Return, Deletion, and Retention.
14. Audit and Compliance Information.
15. Term, Effect, Conflicts, and Liability.
16. Annex 1: Processing Details.
17. Annex 2: Technical and Organizational Measures.
18. Annex 3: Authorized Sub-Processors.

---

## Bilingual Drafting Style

- Use Chinese heading followed by English heading, or paired bilingual clauses.
- Prefer clause pairing:
  - Chinese paragraph.
  - English paragraph.
- Keep English legally functional, not a literal word-for-word translation.
- Use bracketed placeholders for unknown facts: `[●]`, `[XX Service Agreement]`, `[XX服务协议]`.
- Define personal data broadly enough to cover personal information, personal data, and personal information under covered laws.

---

## Client-Friendly Defaults (Party B Position)

- Party B processes only on Party A's documented instructions.
- Party B assists Party A with data subject requests, breach response, DPIAs, and transfer assessments on reasonable request.
- Breach notice should be without undue delay and, where feasible, within 48 hours after confirmation or awareness of a personal data breach affecting Party A personal data.
- Audit rights can be satisfied first through documentation, certifications, security summaries, or third-party reports; further audits are available where legally required or after a material incident, at Party A's expense and subject to confidentiality, reasonable prior notice, and non-disruption of Party B's normal business operations.
- Party B may use affiliates as pre-authorized sub-processors but must remain liable for them.
- Non-affiliate sub-processors require Party A's prior written consent.

---

## Negotiation Positions by Clause

For each key clause, the drafting position below represents the client-friendly (Party B) starting point. When the user requests a more neutral or Party A-friendly position, adjust accordingly.

### Definitions

| Position | Approach | Tag |
|----------|----------|-----|
| **Client-friendly (default)** | Define only personal data / personal information, processing, controller, entrusted processing. Do not define processor / service provider as standalone concepts. | — |
| **Fallback** | Add `处理者 / processor` and `服务提供方 / service provider` as defined terms if Party A insists. | `[review]` |
| **Avoid** | Defining all GDPR Article 4 terms — invites cross-framework conflicts. | — |

### Breach Notification Timing

| Position | Timing | Tag |
|----------|--------|-----|
| **Client-friendly (default)** | "without undue delay and, where feasible, within 48 hours after confirmation or awareness" | — |
| **Fallback** | "without undue delay and in any event within 48 hours after becoming aware" | `[review]` |
| **Party A position** | "within 24 hours" or "immediately upon discovery" | Reject unless regulatory requirement |

### Audit Rights

| Position | Approach | Tag |
|----------|----------|-----|
| **Client-friendly (default)** | Documentation first → third-party reports → on-site audit only where legally required or after material incident, at Party A's expense, with reasonable notice, subject to confidentiality and non-disruption | — |
| **Fallback** | On-site audit once per 12-month period, at Party A's expense, with 30 days' notice | `[review]` |
| **Avoid** | Unrestricted audit rights, Party B's cost, or short-notice access | — |

### Sub-Processors

| Position | Approach | Tag |
|----------|----------|-----|
| **Client-friendly (default)** | Affiliates pre-authorized; non-affiliates require prior written consent (case-by-case) | — |
| **Fallback** | Affiliates pre-authorized with notice-and-objection mechanism; non-affiliates require prior written consent | `[review]` |
| **Party A position** | All sub-processors require prior written consent, including affiliates; or general prior consent required | Reject for affiliates |

### Liability Alignment

| Position | Approach | Tag |
|----------|----------|-----|
| **Client-friendly (default)** | DPA liability cap aligns with main agreement cap; no separate DPA liability stack | — |
| **Party A position** | DPA has its own liability cap, or certain breaches (data breach, SCCs violation) are uncapped | Flag `[review]`; most Party Bs should resist separate caps |

### Governing Law and Dispute Resolution

| Position | Approach | Tag |
|----------|----------|-----|
| **Client-friendly (default)** | Align governing law with main agreement; if silent, default to Hong Kong or Singapore arbitration for neutrality | — |
| **Party A position** | Party A's home jurisdiction law and courts | `[review]` — common and generally acceptable for EU/UK/US customers |

---

## Key Clause Positions

### Definitions

Define or cross-reference personal data / personal information, processing, controller, and entrusted processing. Do not include `处理者 / processor` or `服务提供方 / service provider` in the default list of defined terms unless the user expressly asks for those concepts.

### Scope and Instructions

State that Party B processes personal data solely to provide the products or services purchased by Party A, perform the main agreement, comply with Party A's documented instructions, and satisfy applicable law.

### CCPA/CPRA — Service Provider and Contractor Restrictions

Under CCPA/CPRA, a "service provider" and a "contractor" are distinct categories with overlapping but not identical obligations `[model knowledge — verify]`. Draft to cover both:

- No selling or sharing personal information.
- No retaining, using, or disclosing personal information outside the business purpose specified in the agreement.
- No combining personal information across customers except as permitted by CCPA/CPRA.
- Assistance with consumer requests where Party B holds relevant information.
- Certify compliance with these restrictions.

If Party B receives personal information both as a service provider AND a contractor (e.g., for different processing activities), consider adding a dual-role clause or separate processing-purpose rows in Annex 1.

### PIPL — Entrusted Processing Integration

Do not include a standalone PIPL entrusted processing clause by default. Instead, reflect PIPL-style entrusted processing requirements in:

- **Role clause**: State Party B acts as the entrusted party (受托方) under PIPL.
- **Instructions clause**: Documented instructions from Party A.
- **Annex 1**: Processing purpose, method, categories of personal information, retention period.
- **Annex 2**: Security measures — PIPL Article 51 requires specific technical and organizational measures.
- **Return/deletion**: Return or deletion upon termination (PIPL Article 22).

PIPL does not use the GDPR processor/controller taxonomy — it uses "personal information handler" (个人信息处理者) and "entrusted party" (受托方). Reflect this in the Chinese text while keeping English text GDPR-aligned for consistency.

### Cross-Border Transfers

Draft carefully:

- If EU/UK personal data is transferred to or accessed from China, include placeholders for SCCs, UK transfer addendum or IDTA, and transfer impact assessment.
- If the facts do not involve China-origin personal information export, do not add China outbound transfer mechanism obligations.
- If China-origin personal information is later in scope, flag that PIPL export mechanisms may need separate analysis.

### UK Transfer Mechanism — IDTA vs Addendum

- **UK IDTA**: Standalone agreement. Required for new contracts from 21 March 2024. Replaces the old EU SCCs for UK transfers.
- **UK Addendum to EU SCCs**: Attached to the EU SCCs, adapting them for UK law. Useful for contracts that already have EU SCCs in place.
- Drafting approach: Include a placeholder that covers both options; let the parties select. Do not choose for them.

### Sub-Processors

Use a two-tier consent mechanism:

- Affiliates: expressly authorized in the DPA, with written back-to-back obligations.
- Non-affiliates: prior written consent required for each appointment.

---

## Annex 1 Table Fields

Use a table with these rows:

- Main agreement.
- Services.
- Processing purpose.
- Processing activities.
- Personal data categories: include checkboxes and instruct Party A to select applicable categories.
- Sensitive/special category data.
- Data subject categories.
- Processing duration.
- Processing locations and remote access.
- Authorized sub-processors.
- Deletion/return timeline.

---

## Annex 2 TOMs Table Fields

Use concise descriptions for:

- Transmission encryption.
- Storage encryption.
- Access control.
- Identity and account management.
- Logging and monitoring.
- Backup and resilience.
- Vulnerability management.
- Incident response.
- Personnel confidentiality.
- Data deletion and return.

### Risk Tiering for TOMs

| Risk Level | Circumstances | TOMs Detail Required |
|------------|--------------|---------------------|
| 🟢 Standard | No sensitive data; standard SaaS services | General descriptions sufficient |
| 🟡 Elevated | Sensitive/special category data; financial or health data | Specific controls for each domain; reference certifications (ISO 27001, SOC 2) |
| 🔴 High | Criminal offence data; biometrics; regulated industry (banking, healthcare) | Detailed controls; may require country/region-specific security schedules; flag `[review]` |

If the user hasn't specified the sensitivity level, default to standard TOMs and note in the reviewer note.
