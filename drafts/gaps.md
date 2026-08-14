---
title: "Gaps and contradictions: the two failures your docs cannot see"
category: "Engineering"
meta: "AUG 2026 · 7 MIN READ"
description: "A gap is demand with no page. A contradiction is two pages disagreeing. Neither is visible inside a single silo."
standfirst: >-
  A content gap is demand with no page behind it. A contradiction is two pages that disagree. Neither is visible to a tool that only looks inside one silo — and both are expensive.
---
Once you have a model of the whole estate rather than one silo, two things fall out of it that
no single-silo tool can compute. They are worth naming separately, because they have different
causes and different fixes.

## A gap is demand with no supply

Your community is a demand signal that nobody reads as one. When forty threads discuss proxy
timeouts and the documentation has no page on the subject, that is not an anomaly — it is a
measurement. The readers told you what was missing, at length, in public, and the information
stayed trapped in a channel the docs team does not treat as an input.

Kenaptic computes this across buckets: topics with real demand in one part of the estate and no
coverage in a part you could publish to. On one mid-sized estate we analysed recently, the
community carried **more than 5,000 topics with no counterpart anywhere else** — every one of
them a question somebody asked that the documentation never answered.

This matters commercially because of what happens next. Gartner finds customers fully resolve
only **14%** of their service and support issues in self-service ([August
2024](https://www.gartner.com/en/newsroom/press-releases/2024-08-19-gartner-survey-finds-only-14-percent-of-customer-service-issues-are-fully-resolved-in-self-service)),
while the same firm benchmarks the median self-service contact at roughly **$1.84** against
about **$13.50** assisted. A gap is a guaranteed escalation from the cheap channel to the
expensive one — the reader cannot self-serve, because the page does not exist.

## A contradiction is two pages that cannot both be right

Fast-shipping teams produce these constantly and almost never catch them. The changelog says a
default changed; the tutorial still teaches the old one. The knowledge base says tokens last 24
hours; the reference says 90 days. Both pages were correct when written. Neither is wrong in a
way that any linter, test or reviewer of a single page could detect, because the error only
exists in the relationship *between* two documents that nobody reads together.

Detecting these well turns out to be mostly a matter of restraint. Our first instinct was to
flag numeric and version differences between similar passages — it produced a 66% flag rate at
approximately zero precision, because most numeric differences between two pages are not
disagreements at all. What works is far narrower: sample passages that carry explicit change
language — *deprecated*, *no longer*, *replaced by*, *breaking change* — pair each with its
nearest cross-bucket neighbour, and judge that pair. Fewer candidates, dramatically better
findings.

We would rather report five contradictions that are all real than fifty that a reader has to
triage. A detector people stop trusting is worse than no detector, because it consumes the
attention that the real findings needed.

## Both are reported honestly, including when we cannot answer

If your estate has no writable destination configured, Kenaptic cannot tell you what is missing
from it — and it says exactly that, rather than reporting zero gaps. This sounds like a small
distinction. It is not. "We found nothing wrong" and "we were unable to look" are completely
different statements to put in front of a team, and a product that conflates them will
eventually be trusted at precisely the wrong moment.

The same principle runs through the dead-link detector: it reports only on links inside the
estate we actually crawl, and states what it excluded. Calling a working link broken costs more
trust than saying nothing.

## What you do with them

A gap becomes a drafted page you can accept, edit or discard. A contradiction becomes a proposed
correction at the source, routed through the same review gate and the same one-click retraction
as every cross-link. Nothing about a finding gives it a shortcut past a human.

> Kenaptic proposes; a person decides. Every link is reviewed before it publishes and retractable in one click — see [Security](security.html).
