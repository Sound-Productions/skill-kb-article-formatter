# KB Article Formatter — Claude Skill

A Claude skill that transforms raw text, notes, or documentation into properly formatted SoundPro knowledgebase articles.

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

## Repo Structure

```
kb-article-formatter/
├── SKILL.md            # Skill definition (required)
├── assets/
│   └── template.md     # Standalone article template
├── references/         # Reference docs (reserved)
└── README.md
```

## Setup — Claude Desktop (Native Skill)

Claude Desktop supports skills natively. To install:

1. Download or build the ZIP:
   ```bash
   zip -r kb-article-formatter.zip SKILL.md assets/ references/
   ```
2. Open **Claude Desktop**.
3. Go to **Customize > Skills**.
4. Click **+** then **Create skill**.
5. Upload `kb-article-formatter.zip`.

Claude will automatically invoke this skill when you paste raw content and ask it to create a KB article. You can also invoke it explicitly by typing `/kb-article-formatter`.

## Setup — Claude Code

Copy the skill directory into your project:

```bash
mkdir -p .agents/skills/kb-article-formatter
cp -r SKILL.md assets/ references/ .agents/skills/kb-article-formatter/
```

## Usage

Once installed, just paste or describe the content you want turned into a KB article:

> Here are my notes from the training on how to process returns. Customer calls in, we check the order number, verify the item is within 30 days, then create an RMA in Acumatica under Returns > New RMA...

Claude will output a complete, formatted markdown article ready to save into the `docs/` directory.

## Template

A standalone article template is available at [`assets/template.md`](assets/template.md) for manual use or reference.

## KB Structure Reference

| Section | Path | Content |
|---------|------|---------|
| Acumatica | `docs/acumatica/<subsection>/` | ERP procedures |
| Team Resources | `docs/team-resources/<subsection>/` | IT guides, policies |
| Customer Portal | `docs/customer-portal/` | Shopify portal guides |
| IT | `docs/it/` | Infrastructure, access control |
| Accounting | `docs/accounting/` | Accounting articles |
