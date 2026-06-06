# Word Output

Use this reference when the user asks for a Word draft, formatted document, comments, or tracked changes.

---

## Document Creation

- Prefer `.docx` output for formal DPA drafts.
- Use the Documents skill/plugin if available.
- Create polished formatting: title page or compact heading block, automatic-looking heading hierarchy, bilingual clause pairing, readable tables for annexes, page numbers, and footer placeholders.
- Keep formatting professional and conservative for legal use.

---

## Bilingual Layout

Acceptable layouts:

| Layout | Use When | Notes |
|--------|----------|-------|
| **Clause-by-clause bilingual** (default) | Standard DPA drafting and negotiation | Chinese paragraph followed by English paragraph within each clause; easiest to negotiate and redline |
| **Two-column bilingual table** | Annexes, definitions, or processing details | Chinese in left column, English in right; clean for reference but harder to track-change |
| **Chinese-only working draft + English translation** | When user explicitly requests separate versions | Less common; produces two documents |

Default to clause-by-clause bilingual text because it is easier to negotiate and redline.

### Clause-by-Clause Formatting Rules

- Heading: bilingual on one line, e.g., `第1条 定义 / Article 1 Definitions`
- Body: Chinese paragraph first, then English paragraph. Separate with a blank line.
- For numbered sub-clauses: pair at the sub-clause level, not the parent clause level.
- Use consistent indentation and spacing.

---

## Tracked Changes and Comments

When revising an existing Word DPA:

- Preserve the original file where possible.
- Use tracked changes for textual edits when the document workflow supports it.
- Use comments for legal rationale, fallback positions, missing facts, or negotiation notes.
- Keep comments concise and actionable. Each comment should explain *why* the change is proposed, not just *what* changed.
- Render the document to images or PDF for visual QA when using the Documents skill/plugin.

When creating a new draft from scratch:

- Do not artificially mark all text as tracked changes unless the user requests a redline.
- Include drafting notes in bracketed comments or a separate note section only if useful.
- Placeholder text (e.g., `[●]`, `[待补充]`) should be visually distinct — consider using a highlight or comment to flag.

### Redline Production Workflow

1. Read the original document.
2. Identify changes: substitutions, deletions, insertions, and new sections.
3. Apply tracked changes in the document (using Documents skill/plugin or `python-docx`).
4. Visual QA: render to images or PDF; confirm changes appear correctly.
5. Produce: tracked-changes `.docx` (for counterparty) + optional clean version + optional change summary.

---

## Comments Style Guide

| Comment Type | Format | Example |
|-------------|--------|---------|
| **Legal rationale** | `[Legal note]: [reason]` | `[Legal note]: Article 28(3)(e) GDPR requires this provision.` |
| **Fallback position** | `[Fallback]: [position]` | `[Fallback]: If Party A rejects, accept "without undue delay" without the 48-hour specification.` |
| **Missing fact** | `[To confirm]: [question]` | `[To confirm]: Please confirm whether processing involves special category data.` |
| **Negotiation note** | `[Negotiation]: [guidance]` | `[Negotiation]: Party A may push for 24-hour breach notice. 48 hours is market standard for SaaS.` |

---

## File Naming

Use descriptive Chinese-English filenames, for example:

- `DPA_CN_Outbound_Bilingual_Draft.docx`
- `数据处理协议_DPA_中英双语初稿.docx`
- `DPA_Redline_YYYYMMDD.docx`
- `DPA_Annex_1_Processing_Details.docx`

Include a date stamp when producing redlines or versioned drafts.

---

## Formatting Checklist

Before delivering a Word DPA:

- [ ] Headings use consistent hierarchy (Title → Heading 1 → Heading 2).
- [ ] Bilingual clause pairing is consistent throughout.
- [ ] Page numbers present.
- [ ] Footer includes document name and date placeholder.
- [ ] Placeholder text `[●]` is visually distinct.
- [ ] Annex tables are properly formatted with borders and alignment.
- [ ] No orphan headings at page breaks.
- [ ] Comments are in the correct language (Chinese for Chinese text, English for English text, or consistent with the primary audience).
