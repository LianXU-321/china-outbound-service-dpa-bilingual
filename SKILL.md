---
name: china-outbound-service-dpa-bilingual
description: >
  Draft, review, localize, redline, and format bilingual Chinese-English DPA annexes for Chinese outbound
  service companies providing products or services to overseas enterprise customers. Use when Codex needs to
  create or revise China outbound service DPA Word drafts, DPA annexes to service agreements, GDPR/UK GDPR/
  CCPA-CPRA/PIPL data processing clauses, affiliate sub-processor terms, cross-border remote access terms,
  technical and organizational measures, or client-friendly negotiation positions for this specific scenario.
version: 1.1.0
metadata:
  author: "XU Lian（徐莲）"
  license: "CC-BY-NC-4.0"
  certification: "L3"
  jurisdiction: "Multi-jurisdiction (EU/UK/California/PRC)"
  practice_areas: ["data-compliance", "corporate", "cross-border"]
  supported_languages: ["zh", "en"]
argument-hint: "[起草 / 审阅 / 修订 / Redline / 格式化为Word] — 中国企业出海服务DPA中英双语版"
---

# China Outbound Service DPA Bilingual

## Purpose

Use this skill to draft or review a bilingual Data Processing Agreement (DPA) for a Chinese company providing products or services to enterprise customers outside China. The default scenario is:

- The Chinese company (Party B) is entrusted to process personal information on behalf of the overseas enterprise customer (Party A, the personal data controller).
- The DPA is an annex to the main services agreement.
- Covers GDPR, UK GDPR, CCPA/CPRA, and PIPL at a framework level.

This skill produces a client-friendly but commercially workable draft — protecting Party B's interests to a reasonable extent while meeting the compliance expectations of overseas enterprise customers.

This skill is adapted in part from `compliance-anthropic`, licensed under Apache-2.0. Preserve `LICENSE.txt` and `NOTICE.txt` when copying or distributing this skill.

---

## Default Scenario

When the user does not provide different facts, apply the defaults in `references/default-scenario.md`.

Key defaults:

- Party A is the personal data controller; Party B is the Chinese outbound service provider entrusted to process personal information on Party A's behalf.
- The DPA is an annex to the main agreement, named `[XX Service Agreement] / [XX服务协议]` unless the user provides the actual title.
- Cover GDPR, UK GDPR, CCPA/CPRA, and PIPL at a framework level.
- Treat cross-border transfer as customer-jurisdiction outbound transfer or remote access to customer data by Party B's China-based operations team, **not** as China personal information export unless user facts say otherwise.
- Allow Party B affiliates as authorized sub-processors; require prior written consent for non-affiliate sub-processors.

---

## Workflow

1. **Identify the task type**: draft from scratch / revise an existing DPA / produce comments / create a redline / generate a Word document.
2. **Gather missing business facts** — only those that materially affect the draft. When facts are absent but the default scenario covers them, proceed with bracketed placeholders `[●]`. Collect all missing facts in one pass; do not ask the user question by question.
3. **Draft** using `references/drafting-framework.md` for clause structure, bilingual drafting rules, client-friendly positions, and annex formats.
4. **For Word output**, follow `references/word-output.md`. Use the Documents skill/plugin when available for `.docx` creation, formatting, comments, tracked changes, rendering, and visual QA.
5. **For review tasks**, lead with high-impact legal and negotiation issues, then provide proposed clause language or redline instructions. Apply the reviewer note format (see Outputs).

---

## Drafting Rules

- Write in Chinese and English, with Chinese first unless the user requests otherwise.
- Keep clauses clear, contract-ready, and capable of being used as an annex to a main services agreement.
- Use defined terms consistently: Party A is the personal data controller; Party B is the party entrusted to process personal information on Party A's behalf.
- In the default Definitions clause, define or reference only terms such as personal data / personal information, processing, controller, and entrusted processing. Do not list `处理者 / processor` or `服务提供方 / service provider` as defined concepts unless the user expressly asks.
- State that Party B processes personal data only to provide the purchased products or services and to perform the main agreement.
- For the cover drafting note, use: `本初稿基于中国企业作为服务提供方，向境外企业客户提供产品或服务的常见场景拟定。`
- Do not include generic "draft for discussion" language or a bilingual draft footer unless the user requests it.
- Do not include a standalone PIPL entrusted processing clause by default; reflect PIPL classification and entrusted-processing concepts in definitions, processing details, role clauses, and annexes instead.
- Keep security measures practical and general unless the user provides specific controls or certifications.
- Avoid over-promising regulatory outcomes. Draft assistance obligations, cooperation duties, and reasonable support standards.
- Flag where local counsel review is recommended, especially for SCCs, UK IDTA/Addendum, transfer impact assessments, China PIPL export analysis, and U.S. state privacy law updates.
- Apply source attribution tags inline where appropriate (see Guardrails).

---

## Output Expectations

For a new DPA draft, produce:

- Main bilingual DPA body.
- Annex 1: Processing details (with selectable personal data categories checklist).
- Annex 2: Technical and organizational measures.
- Annex 3: Authorized affiliate sub-processors and non-affiliate approval rule.
- Optional drafting notes or bracketed alternatives when facts are missing.

For a Word draft, create a polished `.docx` with clear headings, bilingual clause pairing, tables for annexes, footer placeholders, and revision/comment support when the user requests changes to an existing draft.

---

## Quality Gates

| Gate | When | Requirement |
|------|------|-------------|
| **Scenario confirmation** | Before drafting | Confirm whether facts match the default scenario; if the user's scenario involves China-origin personal information export, flag and adjust frameworks |
| **Processing scope** | Before drafting | Confirm whether sensitive / special category data is in scope; if unclear, include checkboxes and a note to Party A |
| **Cross-border direction** | Before drafting | Verify: data flows from customer jurisdiction → China (default), not China → overseas (PIPL export) |
| **Multi-jurisdiction coverage** | During drafting | Confirm GDPR, UK GDPR, CCPA/CPRA, and PIPL are each addressed at the appropriate level |
| **Disclaimer attached** | Final output | Output header must match user role (lawyer vs non-lawyer) |

### Error Handling

| Failure Mode | Handling |
|-------------|----------|
| **Missing material facts** (e.g., processing activities unknown, main agreement not named) | Insert bracketed placeholders `[●]` or `[XX Service Agreement]`; note in reviewer note what needs completion |
| **User's facts contradict default scenario** (e.g., China-origin personal information export) | Flag the contradiction; adjust applicable frameworks; mark affected clauses `[review]` |
| **Unclear applicable law** (user doesn't specify which jurisdictions' data is involved) | Default to GDPR + UK GDPR + CCPA/CPRA + PIPL; ask user to confirm or narrow |
| **User requests a legal opinion** (e.g., "is this DPA compliant?") | Decline to opine; offer to provide a compliance-gap note for attorney review |
| **Word generation fails** (Documents plugin unavailable) | Fall back: produce clean markdown with formatting instructions; suggest manual `.docx` creation path |
| **Regulatory change suspected** (e.g., new SCCs adopted, PIPL implementation rules updated) | Flag with `[model knowledge — verify]`; advise user to check current version before finalizing |

---

## Guardrails

### Source Attribution

Apply these inline tags consistently during drafting:

- `[model knowledge — verify]` — legal references, regulatory thresholds, and procedural rules from training data. The reader should verify against a primary source before relying.
- `[review]` — a judgment call the attorney needs to make (e.g., whether to include a specific carveout, which transfer mechanism to use).
- `[user provided]` — information the user supplied in this session.
- `[settled — last confirmed YYYY-MM-DD]` — stable statutory references checked against a primary source on a known date. Use only when the check is confirmed; otherwise fall back to `[model knowledge — verify]`.

Do not promote a tag because the citation "seems right." The tag describes provenance, not confidence.

### No Silent Supplement — Three Values

When this skill needs information it doesn't have:

1. **Supplement with a flag.** Pull from model knowledge, tag `[model knowledge — verify]`, and proceed.
2. **Stop and ask.** Where the missing fact materially changes the draft, ask the user to provide it before continuing.
3. **Flag-but-don't-use.** If you are aware of information that would change whether a rule applies — pending regulatory changes, effective-date delays, new SCCs — surface it as a flagged caveat, even if you cannot use it to change the analysis.

Silence about known doubt is as misleading as confident assertion.

### Currency Trigger

Data protection law is in active flux — new SCCs, UK IDTA transitions, CCPA/CPRA rulemaking, PIPL implementation rules. When the question depends on a recent effective date, enforcement posture, or regulatory change, flag it with `[model knowledge — verify]` and advise the user to verify. The test: would a law firm client alert on this topic have a "recent developments" section? If yes, flag it.

### Jurisdiction Recognition

This skill covers four frameworks: GDPR, UK GDPR, CCPA/CPRA, and PIPL. When a user's facts involve a jurisdiction outside these four:

1. **Detect.** Check governing law, party locations, and data subject locations.
2. **Assess.** Does this skill have a framework for it?
3. **If not:** Clearly state: "This skill covers GDPR / UK GDPR / CCPA-CPRA / PIPL. Your scenario involves [jurisdiction], where the law differs. Applying these frameworks directly may give you a wrong answer that looks right."
4. **Offer:** Search for the applicable standard / route to a local specialist / flag the gap and continue with caveats.
5. **Never produce a confident answer using the wrong jurisdiction's law.**

### Scaffolding, Not Blinders

This skill's drafting rules and framework are a floor, not a ceiling. When the user asks for something this skill's normal checklist doesn't cover — a standalone SCCs drafting, a PIPL data export analysis, a China Personal Information Protection Impact Assessment — answer the question anyway and note: "This isn't in the normal DPA drafting checklist, but it's relevant: [analysis]." Apply the guardrails (source tags, disclaimer, reviewer note) without the full DPA structure.

### Destination Check

Before producing any output, consider where it's going. If the user names a destination (client-facing, counterparty, public channel), flag privilege implications. A DPA draft sent to the counterparty should not carry internal legal analysis notes. Offer to produce a clean version and an internal memo separately.

### Decision Posture on Subjective Legal Calls

When a drafting judgment is uncertain — is this clause position too aggressive? Does this carveout expose Party B? — prefer the recoverable error: draft the clause and tag the specific line with `[review]`. Do not silently omit the issue. Under-flagging is a one-way door; over-flagging is a two-way door the attorney closes in 30 seconds.

---

## Outputs

### Work-Product Header

Prepend to every DPA draft, memo, or review this skill produces:

- **Lawyer / legal professional user:** `内部法律分析 — 不构成正式法律意见 — 须经执业律师审核后方可使用`
- **Non-lawyer user:** `仅供参考 — 不构成法律建议 — 重大决策前请咨询执业律师`

### ⚠️ Reviewer Note

Place one reviewer note above the deliverable. This is the single place for everything the reviewing attorney needs to know before relying on the output:

> **⚠️ 审阅提示**
> - **来源：** [模型知识 — 需核实 | 用户提供]
> - **缺失事实：** [N 项使用了占位符 `[●]`，需补充 | 无]
> - **需您判断：** [N 项标记 `[review]` | 无]
> - **时效性：** [法规引用基于模型知识，签署前请核实当前版本]
> - **建议：** [1-2 项审阅者应重点关注的事项，或 "可直接审阅"]

If all clear (no placeholders, no flags, all facts confirmed), collapse to:
> ⚠️ 审阅提示：无缺失 · 无标记 · 可直接审阅

The deliverable below the reviewer note is clean — no banners, no inline meta-commentary, no workflow narration. Inline tags (`[review]`, `[model knowledge — verify]`) are the only annotations within the body.

### Decision Tree

After delivering the DPA draft or review, close with a decision tree — options, not decisions:

> **下一步，请选一个：**
>
> 【本 skill 可继续协助】
> 1. **生成 Word 版本** — 将当前草稿格式化为 `.docx`，含中英双语对照排版。
> 2. **制作 Redline** — 与客户/对方律师提供的 DPA 进行比对，生成修订痕迹版。
> 3. **补充缺失信息** — 填入占位符 `[●]` 对应的实际内容，完善草稿。
> 4. **调整条款立场** — 针对特定条款修改谈判姿态（如收紧/放宽审计权、修改违约通知时限）。
>
> 【需另行委托执业律师】
> 5. **SCCs / UK IDTA 机制确认** — 确定适用的标准合同条款版本及传输影响评估，须由执业律师处理。
> 6. **PIPL 数据出境分析** — 如涉及中国境内个人信息向境外提供，须单独评估安全评估/标准合同备案/认证路径。
>
> 【通用选项】
> 7. **起草内部备忘录** — 将本次 DPA 的核心条款立场和风险点整理为内部审阅备忘录。
> 8. **其他** — 告诉我你想怎么做。

---

## What This Skill Does NOT Do

- Does **not** provide legal opinions on whether a particular DPA is "compliant" with any specific law.
- Does **not** determine which SCCs version (2021/06/04 modules) or UK transfer mechanism (IDTA vs Addendum) applies — it drafts placeholders and flags the choice for attorney review.
- Does **not** conduct a PIPL data export security assessment or determine whether one is required.
- Does **not** replace a qualified attorney's review of the final DPA before execution.
- Does **not** guarantee that regulatory references are current — always verify effective dates and versions before relying on the output.

---

*本 skill 的输出为法律文件初稿，不构成正式法律意见。使用方应在签署前由具备相应法域执业资格的律师审阅。*
