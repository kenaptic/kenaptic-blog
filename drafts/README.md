# Drafts — written, not published

`gen.py` builds the blog from `posts/*.md` only (`blog.load()` globs that one directory), so
anything here is invisible to the site: no page, no Resources card, no link.

These four were written for launch. They are held back because the site is currently pre-launch
and `launch.md` in particular announces something that has not happened — publishing it beside
the "Kenaptic is coming" teaser would contradict it on the same page.

To publish one: `git mv drafts/<name>.md posts/` and push. The Cloudflare build hook does the
rest.
