# Tools and guides content foundation

This branch reconciles the uploaded blog schemas with the existing standalone Studio.

It retains existing document types, including `freeResources`, and adds the `guide` type.

SEO articles, blog posts, and guides can select related executable tools and reference related educational content.

Guide articles use `/guides/[slug]`. SEO articles keep their existing `/ai-seo/[slug]` URLs.

Tool URLs use `/tools/[slug]`. Content references do not create executable tools inside Sanity.

## Registry synchronization

`schemaTypes/tool-registry.json` is an editor-choice snapshot of the frontend's central registry.

Update it from `features/tool-catalog/registry.json` in `sufi0900/doitwithai.tools` whenever available tool slugs change.

Do not manage a competing executable catalogue inside the CMS.

## Validation and release

```bash
npm ci
npm run build
npm run schema:validate
```

The Studio build passes. Schema validation reports zero errors and four existing rich-text option warnings.

The project-wide TypeScript check still reports legacy strict-typing errors. New guide and relationship schemas introduce no reported errors.

The existing remote theme import now uses the repository's local theme file.

No Studio deployment, schema deployment, document edit, or publication occurred.

Before releasing content, deploy reviewed schemas and check the website's webhook filter for new document types.

Review existing drafts before editing published articles. Editorial status and actual Sanity publication remain separate states.
