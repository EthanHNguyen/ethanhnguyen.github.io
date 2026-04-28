---
title: "ATO Copilot"
excerpt: "ATO Copilot by Ethan Nguyen is a source-backed AI prototype for government authorization workflows, evidence mapping, reviewer questions, provenance, and operational trust."
description: "ATO Copilot by Ethan Nguyen is a source-backed AI prototype for government authorization workflows, evidence mapping, reviewer questions, provenance, and operational trust."
collection: portfolio
permalink: /portfolio/ato-copilot/
---

ATO Copilot is a prototype for source-backed authorization support.

It started as a four-hour hackathon build at c0mpiled-10/DC: AI for Government, where it won 1st place. The project explored a narrow question:

> Can AI help government teams move through authorization and compliance workflows by grounding every recommendation in source evidence?

## What it does

ATO Copilot ingests synthetic evidence artifacts and produces structured control analysis.

The demo focuses on a few concrete tasks:

- mapping evidence to relevant control families
- surfacing likely reviewer questions
- identifying gaps or weak claims
- recommending next actions
- keeping outputs traceable to source material

![ATO Copilot demo showing source-backed control analysis over synthetic evidence](/images/ato-copilot-package-scan-complete.png)

*ATO Copilot demo interface using synthetic evidence. The screenshot shows source-backed control analysis, reviewer questions, recommended actions, and provenance traces.*

## Design principle

The important design choice is that the system is not a generic chatbot.

A blank chat interface asks the user to know what to ask. A compliance workflow needs the opposite: it should shape messy evidence into reviewer-ready work products. The interaction should start with artifacts and produce structured analysis, not start with a prompt box and hope the user interrogates the system correctly.

That is the difference between AI as an answer machine and AI as workflow infrastructure.

## What it proves

High-trust AI systems should be:

- source-backed
- auditable
- constrained
- artifact-driven
- embedded in real approval paths
- designed around trust, not just speed

This is a prototype, not a production authorization system. All demo evidence is synthetic. It does not contain CUI, customer data, or official assessment output.

## Links

- [Writeup: ATO Copilot and the Compliance Gap in Agentic Software](/posts/2026/04/ato-copilot-source-backed-ai/)
- [Source: github.com/EthanHNguyen/ato-copilot](https://github.com/EthanHNguyen/ato-copilot)
