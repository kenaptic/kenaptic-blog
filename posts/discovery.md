---
title: "Cross-link discovery: finding the answer that already exists"
category: "Engineering"
meta: "AUG 2026 · 8 MIN READ"
description: "Why typed relationships beat similarity scores, and how cross-link discovery targets the most common self-service failure."
standfirst: >-
  When self-service fails, the most common reason is not that the answer was missing. It is that the reader could not find it. That is a link problem, and links are fixable.
---
Start with the failure, because it is more precise than it first looks. Gartner's 2024 survey
found that customers could not find content relevant to their issue in **43% of cases** — the
single most common reason self-service fails ([Gartner, August
2024](https://www.gartner.com/en/newsroom/press-releases/2024-08-19-gartner-survey-finds-only-14-percent-of-customer-service-issues-are-fully-resolved-in-self-service)).
The content existed. The path to it did not.

Nielsen Norman Group separates that failure into two useful halves. Findability is when "users
can easily find content or functionality that they assume is present"; discoverability is when
"users encounter new content or functionality that they were not aware of previously" ([NN/g,
*Low Findability and Discoverability*](https://www.nngroup.com/articles/navigation-ia-tests/)).
Search, at best, serves the first. A cross-link serves the second — and across a split estate
the second is the harder problem, because the reader cannot search for a resource they do not
know exists.

Across a fragmented estate this gets worse, for a structural reason: the reader is not searching
one site. They are searching whichever silo they happened to land in. A docs search will not
surface the forum thread. A help-centre search will not surface the blog post. The content is
there; the path is not.

## Why "related" is not good enough

The obvious approach is embedding similarity: encode every page, find the near neighbours, link
them. It produces plausible-looking output and it is not very useful, for two reasons.

The first is that similarity is symmetric and reading is not. A tutorial and its API reference
are similar to each other, but the useful link runs one way at one moment and the other way at
another. The second is that "related content" tells the reader nothing about *why* to click. A
link that says *this thread troubleshoots the error on this page* earns a click. A link that
says *related* earns a shrug.

So Kenaptic types its edges from a deliberately small vocabulary — `explains`, `troubleshoots`,
`is-design-reference-for`, `discusses-real-world-issue-with`, `is-prerequisite-for`. A small
controlled set beats an open one here: it keeps the types comparable across an estate, and it
forces the model to commit to a claim we can show the reviewer and defend.

## Three signals, blended — and a number that is not a probability

A candidate is scored on topic overlap between the two pages, embedding similarity between the
relevant passages, and a directional judgement about whether the proposed relationship actually
holds. Topic overlap acts as a soft pre-filter and a booster rather than a hard gate, because a
hard gate on topics throws away exactly the cross-silo pairs the product exists to find — a
forum thread and a reference page often share very little surface vocabulary while being
precisely about the same failure.

The score we show a reviewer is **decision support, not a calibrated probability**. We say so in
the product and we will keep saying it. A number that looks like a confidence invites people to
threshold on it and stop reading the evidence, and the evidence is the point.

## Evidence, then a human

Every proposal arrives with the passages from both pages that justify it, the relationship type,
and the exact change that would be written. The reviewer approves, edits the type, or rejects.
Nothing publishes without that step.

This is also how the product gets measured. We keep two numbers apart on purpose: **recall**,
whether the engine rediscovers links we already know should exist, and **precision**, the share
of proposals a human actually approves. Collapsing them into one score would let a system look
excellent by proposing very little, or by proposing everything.

## Where the link goes matters as much as whether it is right

A correct link in the wrong place is close to worthless. A reference block at the foot of a long
troubleshooting page is read by almost nobody who needed it. So an approved link can land as a
foot-of-page reference, as an additive sentence in the prose at the relevant point, or both —
and the sentence is written to sit in the flow of the paragraph rather than announce itself as
machine output.

It is additive by design: Kenaptic adds a sentence, it does not rewrite yours. The words on your
page stay your words.

> Kenaptic proposes; a person decides. Every link is reviewed before it publishes and retractable in one click — see [Security](security.html).
