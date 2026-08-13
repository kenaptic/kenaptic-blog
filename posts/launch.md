---
title: "Kenaptic is here"
category: "Announcement"
meta: "AUG 2026 · 6 MIN READ"
description: "Your estate already contains the answer. We built the layer that connects it, with a human approving every change."
standfirst: >-
  Your content estate already contains the answer your customer is looking for. It is just in the wrong silo, with nothing pointing at it. Today we are launching the layer that fixes that — and asks a human before it changes a single page.
---
Every company that has been shipping for more than a couple of years ends up with the same
shape. Product documentation on one platform. A knowledge base on another. A blog on a third. A
community forum, and increasingly a Discord, holding the troubleshooting knowledge that never
made it back into any of them. Four teams, four tools, and — this is the part that costs money —
almost no links between them.

The reader pays for that. A customer hits a problem, opens the docs, finds the page that
describes the feature but not the failure, and stops. The fix exists. It is in a forum thread
from eighteen months ago, or a knowledge-base article written by a support engineer who has
since moved teams. Nothing in the estate points from where the reader is to where the answer
lives.

## Why this is worth building a product around

Gartner's 2024 customer service survey put a number on it that we have not been able to stop
thinking about. **73% of customers use self-service at some point** in their journey — and they
fully resolve only **14%** of their service and support issues there. Even for issues the
customers themselves described as very simple, only 36% resolved fully ([Gartner, August
2024](https://www.gartner.com/en/newsroom/press-releases/2024-08-19-gartner-survey-finds-only-14-percent-of-customer-service-issues-are-fully-resolved-in-self-service)).

The reason given is the part that turned this into a product. In **43% of cases, customers could
not find content relevant to their issue.** Not that the content was wrong, or missing, or badly
written — that they could not find it. That is a navigation failure sitting on top of a content
estate which, more often than not, already holds the answer.

What it costs to leave there is well established: Gartner benchmarks the median self-service
contact at roughly **$1.84** against about **$13.50** for an assisted one ([*Benchmarks to
Assess Your Customer Service Costs*](https://www.gartner.com/en/documents/5164231), February
2024) — close to a sevenfold difference. Every reader who cannot find the page walks out of the
cheap channel and into the expensive one.

Closing that gap is not a search-ranking problem. It is a problem of the estate having no
connective tissue — and connective tissue is the thing no single-silo tool can build, because
each one only sees its own content.

## What Kenaptic actually does

It reads every silo you connect — docs, knowledge base, blog, forum, GitHub discussions,
repositories with no rendered site at all — and builds one model of how the pages relate. Not
"these two documents are similar", which is nearly useless to a reader, but **typed**
relationships: this page *explains* that one, this thread *troubleshoots* that feature, this
reference *is a prerequisite for* that guide. The type is what makes a link worth following, and
it is what lets us write a sentence a human would have written.

Then it proposes the links that should exist, with the passages from both pages that justify
them, and puts them in front of a person. Approved links are written into the actual page source
— a pull request for docs-as-code, the platform's own API elsewhere — so they are real
hyperlinks that readers follow, search engines index and AI assistants can traverse. Not a
JavaScript widget that only humans with the right browser ever see.

## Two rules we will not be talked out of

**A person approves every change.** Review is the default everywhere, and it is not a setting we
bury. A tool that edits your published pages unattended is a tool you will eventually regret,
and the first time it gets something wrong in front of a customer you will turn it off for good.
So Kenaptic is the analyst; your team is the editor. (Automatic publishing does exist, per
source and above a threshold you set — off until an administrator deliberately turns it on, and
carrying a warning we make no attempt to soften.)

**Everything is reversible in one click.** Each link we add is wrapped in explicit markers, so
what we contributed is always distinguishable from what was already there — which means removal
is exact, not approximate. Retract a link and the page returns to precisely its previous state.
We think the fastest way to earn trust with something that writes into your content is to be
genuinely, boringly easy to undo.

## There is a second audience now

Documentation is no longer read only by people. Coding agents and answer engines traverse it
constantly, and they navigate by following links — an unlinked page is, to them, very nearly an
unreachable one. An estate that is well connected at the source is legible to both audiences at
once. That is a happy accident of doing the right thing for readers, but it is not a small one.

Start with three silos on the free plan and see what your own estate is hiding. Most first runs
surface something the team already suspected and nobody had the evidence for.

> Kenaptic proposes; a person decides. Every link is reviewed before it publishes and retractable in one click — see [Security](security.html).
