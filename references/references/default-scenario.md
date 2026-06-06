# Default Scenario

Use these defaults when the user asks to draft a DPA for a Chinese outbound company and does not provide contrary facts.

---

## Regulatory Currency Note

Data protection frameworks covered by this skill are subject to active regulatory change. Key items to flag with `[model knowledge — verify]` before relying:

- **EU SCCs**: 2021/06/04 modules remain the current standard; verify no new modules or replacement decisions have been adopted.
- **UK IDTA / Addendum**: The UK IDTA entered force 21 March 2022; the UK Addendum to EU SCCs entered force 21 March 2022. Verify whether the transition period for old EU SCCs has expired (scheduled: 21 March 2024).
- **CCPA/CPRA**: CPRA enforcement posture and rulemaking (especially on risk assessments, cybersecurity audits, and automated decision-making) remains in flux `[model knowledge — verify]`.
- **PIPL**: Implementation rules on cross-border data transfer mechanisms (security assessment, standard contract filing, certification) and entrusted processing are evolving `[model knowledge — verify]`.
- **U.S. state comprehensive privacy laws**: An expanding number of U.S. states (beyond California) have enacted comprehensive privacy laws with processor obligations. Flag if Party A operates in multiple U.S. states `[model knowledge — verify]`.

This list is not exhaustive. When drafting, apply the currency trigger rule from the main SKILL.md.

---

## Parties and Roles

- Party A / Customer: enterprise customer that purchases Party B's products or services.
- Party B / Service Provider: Chinese company providing products or services to Party A.
- Party A's customers or individual users are not the direct customer of Party B unless the user says otherwise.
- Party A acts as the personal data controller.
- Party B acts as the party entrusted to process personal information on Party A's behalf.
- Do not assume joint controllership unless the user provides facts showing both parties jointly determine processing purposes and means.

### Role Edge Cases

| Scenario | Handling |
|----------|----------|
| User claims Party B is an independent controller | Flag `[review]` — this fundamentally changes the DPA structure. Ask the user to confirm with rationale. |
| User claims joint controllership | Draft a joint controllership addendum instead of a processor DPA; flag `[review]`. |
| Party B sub-processes to its own China infrastructure providers (e.g., Alibaba Cloud, Tencent Cloud) | Treat as non-affiliate sub-processors requiring Party A's prior written consent unless already listed in Annex 3. |

---

## Main Agreement

- Form: DPA as an annex or addendum to the main services agreement.
- Placeholder main agreement name: `[XX Service Agreement] / [XX服务协议]`.
- The DPA should prevail over conflicting main agreement terms only for personal data processing matters, while liability and commercial limitations should align with the main agreement unless the user requests otherwise.

---

## Applicable Frameworks

Cover these frameworks at a contract-drafting level:

- EU GDPR.
- UK GDPR and UK Data Protection Act where relevant.
- CCPA/CPRA for California personal information, including service provider/contractor restrictions.
- PIPL, focused on entrusted processing concepts and Chinese service provider operations.

### Framework Scope Boundaries

- **GDPR**: Article 28 processor obligations, Article 44-49 transfer restrictions (SCCs mechanism), Article 32 security measures.
- **UK GDPR**: Mirrors EU GDPR pre-Brexit; divergences are minor for DPA purposes. Use UK-specific transfer mechanisms (IDTA or Addendum).
- **CCPA/CPRA**: Focus on service provider / contractor restrictions (no sale, no sharing, no use outside business purpose, no combining except as permitted). CPRA adds contractor as a distinct category `[model knowledge — verify]`.
- **PIPL**: Articles 21-23 (entrusted processing), Article 38 (cross-border transfer conditions — but NOT triggered in the default scenario). Do not over-apply.

Add a verification note when current statutory or regulatory changes may need source checking.

---

## Processing Activities

- Services: providing products or services purchased by Party A under the main agreement.
- Purpose: performance of the main agreement, service delivery, operation, maintenance, troubleshooting, security, customer support, and other documented instructions from Party A.
- Processing duration: term of the main agreement plus one year after expiration or termination, unless earlier deletion/return is requested by Party A or longer retention is required by law.

---

## Personal Data Categories

Make the personal data categories selectable or table-based.

Use a selectable checklist. Instruct Party A to tick the applicable categories based on the actual service scenario. Unselected categories should not be deemed included in the processing scope.

General personal data or general personal information examples:

- Name.
- Gender.
- Age.
- Basic identity or profile information.
- Mobile phone number.
- Email address.
- Contact address.
- Account identifiers and business contact details if relevant.
- Online identifiers, device information, IP addresses, logs, access records, and service usage data where relevant.

Sensitive personal information or special category examples:

- PIPL sensitive personal information: biometrics, religious belief, specific identity, medical health, financial accounts, location tracking, and personal information of minors under 14.
- GDPR/UK GDPR special categories: racial or ethnic origin, political opinions, religious or philosophical beliefs, trade union membership, genetic data, biometric data for identification, health data, sex life, or sexual orientation data.
- Criminal offence data: criminal convictions, offence records, alleged offences, or related security measures.
- CCPA/CPRA sensitive personal information: government identifiers, account credentials, precise geolocation, racial or ethnic origin, religious or philosophical beliefs, union membership, contents of communications, genetic data, biometric information, health information, sex life, or sexual orientation information.

Avoid assuming sensitive data is processed unless the user asks to include it or the service scenario requires it.

---

## Data Subjects

- Individual users.
- Individual authorized users of enterprise customers.

---

## Cross-Border Transfer and Remote Access

- Assume cross-border transfer relates to Party A's jurisdiction: Party A may transfer or make data accessible to Party B in China so Party B can provide services.
- Assume Party B's China-based operations, support, or engineering personnel may remotely access customer data for troubleshooting, maintenance, support, security, or user request handling.
- **Do not** characterize this as China personal information export unless the data was collected or generated in China and exported from China.
- Include a placeholder for SCCs, UK Addendum/IDTA, transfer impact assessment, or other transfer mechanism if EU/UK personal data is involved.

### Transfer Mechanism Selection (for EU/UK personal data)

| Mechanism | When to Use | Placeholder Text |
|-----------|-------------|------------------|
| EU SCCs (2021/06/04) | EU personal data transferred to China (no adequacy decision for China) | `[SCCs — Module Two (Controller to Processor) or Module Three (Processor to Processor), as applicable]` |
| UK IDTA | UK personal data; new contracts from 21 March 2024 onward | `[UK International Data Transfer Agreement]` |
| UK Addendum to EU SCCs | UK personal data; transitional or existing contracts | `[UK Addendum to the EU Standard Contractual Clauses]` |
| Transfer Impact Assessment (TIA) | Required alongside SCCs/IDTA | `[Party A and Party B shall cooperate to conduct a transfer impact assessment]` |

Flag the choice for attorney review: `[review]`.

### When the Scenario IS China Personal Information Export

If the user's facts indicate data was collected or generated **in China** and will be exported to Party A's jurisdiction:

- Flag immediately: PIPL Article 38 export mechanisms apply (security assessment by CAC, standard contract filing, or certification).
- The DPA structure may need to be reversed (Party B as the personal information handler entrusting Party A as the overseas recipient).
- Mark all affected clauses `[review]` and recommend separate PIPL export analysis.

---

## Sub-Processors

- Party B's affiliates are authorized sub-processors under the DPA.
- Party B must ensure affiliates are bound by written obligations no less protective than the DPA.
- Party B remains responsible for affiliate sub-processor performance.
- Non-affiliate sub-processors require Party A's prior written consent on a case-by-case basis.

---

## Security Measures

Use a general TOMs annex unless the user provides specific measures. Include:

- Transmission encryption.
- Storage encryption where appropriate.
- Access control and least privilege.
- Account and credential management.
- Logging and monitoring.
- Backup and resilience.
- Vulnerability and incident management.
- Personnel confidentiality and security awareness.
- Data deletion or return process.

### Infrastructure Note

If Party B uses third-party cloud infrastructure (AWS, Azure, Alibaba Cloud, etc.), consider whether the shared responsibility model should be noted in Annex 2. Flag if Party A's industry (financial services, healthcare) imposes specific security requirements beyond the general TOMs.
