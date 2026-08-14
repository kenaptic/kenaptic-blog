---
title: "Crawl, digest, detect, publish: keeping a knowledge web fresh"
category: "Guide"
meta: "AUG 2026 · 7 MIN READ"
description: "The loop that keeps a knowledge web fresh as the estate changes, and why every step of it is reversible."
standfirst: >-
  A one-off cross-linking pass ages badly. Estates change weekly, and a connective layer that does not change with them becomes wrong in a way that is hard to notice.
---
The first run is the exciting one — a few hundred links appear where there were none, and the
estate is visibly better connected. The interesting engineering question is what happens in
month four, when forty new pages have shipped, three have moved, and one has been retired.

Kenaptic runs as a loop rather than a project, and it is worth being explicit about each step
because the failure modes are different at each one.

## Crawl — politely, and only what you are allowed to

KenapticBot identifies itself honestly and treats `robots.txt` as a complete opt-out, alongside
crawl-delay directives and machine-readable text-and-data-mining reservations. It never crawls
past a login. Re-crawling is additive: pages that have not changed are not refetched, so a
weekly pass over a large estate costs a fraction of the first one.

Personal data is removed at this step, before anything is stored — email addresses, phone
numbers, handles, usernames and bylines are stripped from the text on the way in, so everything
derived downstream is clean by construction rather than cleaned up later. That ordering is the
whole point: an embedding built from text containing personal data is itself a problem, and you
cannot un-derive it afterwards.

## Digest — a compact model of what each page is about

Each page gets a topic digest with weighted topics drawn from a canonical vocabulary, and its
passages are embedded. This is the step that makes the estate comparable to itself: two pages on
different platforms, written by different teams, in different house styles, become comparable
objects.

## Detect — and only re-examine what changed

New and changed pages produce new candidate relationships, new gaps and new contradiction
candidates. Scoring is additive, so a nightly pass does not re-judge an estate that has not
moved.

One caveat we will state plainly, because it caught us: adding a large new bucket to an existing
workspace does not, on its own, cause previously-scored pages to be re-examined against it. If
you connect a forum with several thousand threads to an estate that was scored last month, ask
for a full re-score rather than assuming the incremental pass will find everything. We would
rather tell you that than have you quietly under-count.

## Publish — through a human, and reversibly

Approved changes are written at the source: a pull request into the repository for docs-as-code
platforms, or the platform's own API where there is no repository. Re-running does not open a
second pull request for the same change; it updates the one already open. On community
platforms, Kenaptic adds a reply pointing at the related page — it never edits a member's post,
because those words belong to the person who wrote them.

Every change is marked, so what Kenaptic contributed is always distinguishable, and removal is
therefore exact rather than approximate. Retracting a link restores the page to its previous
state; on git-backed content that means closing or reverting the pull request.

## Monitor — because links decay quietly

A published link is not finished. Pages move, sections are retired, and an estate slowly
accumulates references to things that no longer exist. The loop watches click-through per link,
freshness, and in-estate links whose destination has disappeared — reported to your inbox or
messaging app rather than waiting to be discovered.

There is a second reason to keep the web current. Documentation now has an audience that
navigates almost entirely by following links: coding agents and answer engines traverse an
estate the way a reader would, and a page with nothing pointing at it is close to invisible to
them. Keeping the connective layer fresh keeps the estate legible to both audiences at once.

> Kenaptic proposes; a person decides. Every link is reviewed before it publishes and retractable in one click — see [Security](security.html).
