# KB Article Formatter — Claude Desktop Skill

A Claude Desktop skill that transforms raw text, notes, or documentation into properly formatted SoundPro knowledgebase articles.

## What It Does

Give Claude any raw content — rough notes, copy-pasted emails, meeting notes, existing docs — and it produces a publication-ready markdown article with:

- Correct YAML frontmatter (`title`, `created`, `updated`, `tags`, `version`)
- Proper heading hierarchy (H1 title, H2 sections, H3 subsections)
- VitePress callout blocks (`::: info`, `::: warning`, `::: danger`)
- Numbered step-by-step procedures with field annotations
- Screenshot placeholders with descriptive alt text
- Internal links using clean URL paths
- Attachment references
- Suggested filename and destination path

## Setup — Claude Desktop

1. Open Claude Desktop and create a new **Project**.
2. Go to the project's **Instructions** (the system prompt area).
3. Copy the entire contents of [`SKILL.md`](SKILL.md) and paste it into the project instructions.
4. Start a conversation in that project and provide your raw content.

## Setup — Claude Code

To use this as a Claude Code skill, copy the `SKILL.md` file into your project's `.agents/skills/kb-article-formatter/` directory:

```bash
mkdir -p .agents/skills/kb-article-formatter
cp SKILL.md .agents/skills/kb-article-formatter/
```

## Usage

Once configured, just paste or describe the content you want turned into a KB article:

> Here are my notes from the training on how to process returns. Customer calls in, we check the order number, verify the item is within 30 days, then create an RMA in Acumatica under Returns > New RMA...

Claude will output a complete, formatted markdown article ready to save into the `docs/` directory.

## Template

A standalone article template is also available at [`template.md`](template.md) for manual use or reference.

## KB Structure Reference

| Section | Path | Content |
|---------|------|---------|
| Acumatica | `docs/acumatica/<subsection>/` | ERP procedures |
| Team Resources | `docs/team-resources/<subsection>/` | IT guides, policies |
| Customer Portal | `docs/customer-portal/` | Shopify portal guides |
| IT | `docs/it/` | Infrastructure, access control |
| Accounting | `docs/accounting/` | Accounting articles |
