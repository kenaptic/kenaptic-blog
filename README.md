# Kenaptic blog

The articles published at [kenaptic.com/resources](https://www.kenaptic.com/resources), one
markdown file per article in [`posts/`](posts/).

They live in their own public repository for a reason that is the whole point of the product:
**Kenaptic adds cross-links by opening pull requests against source files.** For it to link an
article to the documentation, the article has to be a file it can edit — and for anyone to
believe that, the pull request has to be visible. Both are true here.

## Writing

Add a `.md` file to `posts/`. The filename is the URL slug: `posts/loop.md` publishes at
`/post-loop`. Frontmatter carries everything the page and the index card need:

```yaml
---
title: "Crawl, digest, detect, publish"
category: "Guide"                 # shown as the eyebrow, and colours the index card
meta: "AUG 2026 · 7 MIN READ"
description: "One sentence for search results and social cards."
standfirst: >-
  The opening paragraph, set larger than the body. Two sentences at most.
---

Body starts here. `##` for section headings — the title is already the h1.

A closing note goes in a blockquote:

> Kenaptic proposes; a person decides.
```

Nothing else to update. The article page, the entry on Resources and the sitemap all follow from
the file.

## Publishing

The site rebuilds from the `main` branch of this repository. Merging here publishes.

## Related

- [`kenaptic-docs`](https://github.com/kenaptic/kenaptic-docs) — the documentation, also public,
  also markdown. Cross-links between the two are the demonstration.
