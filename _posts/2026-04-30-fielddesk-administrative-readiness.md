---
title: "FieldDesk and Administrative Readiness"
date: 2026-04-30
permalink: /posts/2026/04/fielddesk-administrative-readiness/
excerpt: "FieldDesk is a source-backed AI prototype for military administrative readiness. It won the GenAI.mil track in Washington, D.C. at the SCSP 2026 National Security Technology Hackathon."
description: "FieldDesk is a source-backed AI prototype for military administrative readiness. It won the GenAI.mil track in Washington, D.C. at the SCSP 2026 National Security Technology Hackathon."
tags:
  - AI for Government
  - GovTech
  - Operational Trust
  - Agentic AI
  - Hackathon
---

At the SCSP 2026 National Security Technology Hackathon in Washington, D.C., I built FieldDesk, a prototype for military administrative readiness. FieldDesk won the local GenAI.mil track.

The win was meaningful, but the more interesting part was the question the prototype explored:

> What if AI for government work did not start as a chatbot, but as workflow infrastructure for turning fragmented evidence into route-ready action?

That question matters because a lot of operational friction is not dramatic. It is administrative.

The military does not just run on orders. It runs on the administrative work that makes orders executable: packets, rosters, checklists, approvals, policy references, emails, funding evidence, rate tables, and routing rules.

When that work breaks, the failure mode is familiar. A packet comes back. The preparer fixes one issue. Another issue appears. The reviewer sees a mismatch. The unit loses time.

The person doing the work usually does not need another search box. They need to know:

- Which sources matter?
- What evidence has been found?
- What is missing?
- What conflicts?
- What will likely get returned?
- What should happen next?

FieldDesk was built around that loop.

## The hackathon context

The event was SCSP's 2026 National Security Technology Hackathon, hosted as part of the AI+ Expo ecosystem. SCSP describes the hackathon as bringing together AI engineers from academia, research institutions, the private sector, and government to build applications for national competitiveness and national security.

The first phase took place across San Francisco, Boston, and Washington, D.C. Teams built prototypes in tracks including Cloud Laboratories, Electric Grid Optimization, Wargaming, and GenAI.mil. The GenAI.mil track focused on AI tools for military administrative work, logistics, and tactical knowledge retrieval for rank-and-file users.

That framing was important. It pushed the project away from abstract AI demos and toward a concrete user: a junior NCO trying to turn mission intent into a complete administrative packet.

## What FieldDesk does

FieldDesk is an agentic workflow platform for administrative readiness.

The demo starts with a TDY travel scenario because it is concrete, common, and painful. A user enters mission intent:

> Send 10 soldiers to Demo Training Site for training from June 10-14. Lodging and rental vehicles required.

From there, FieldDesk searches across mocked sources that represent the kinds of systems a real workflow would touch:

- Outlook-style coordination messages
- SharePoint-style documents and rosters
- GSA-style per diem data
- JTR-style policy excerpts
- local SOPs and unit checklists
- uploaded correction files
- DTS-style export fields

The point is not that TDY is the only workflow. TDY is the wedge.

The broader pattern is:

```text
mission intent
  -> fragmented evidence
  -> requirement mapping
  -> gap detection
  -> reviewer objections
  -> staged corrections
  -> route-ready package
```

In the demo, FieldDesk finds the training order, roster, approval email, rate data, policy references, and local checklist. It also catches issues that would likely cause the packet to come back:

- the mission says 10 travelers, but the roster only shows 8
- no funding memo is present
- the rental vehicle justification is too generic for review

After the user stages corrections, FieldDesk recomputes readiness and generates a review package: evidence map, reviewer objections, action list, packet summary, DTS-style export rows, and source-backed audit trail.

The core value moment is simple:

> FieldDesk catches avoidable administrative failure before review.

## Not a regulation chatbot

A regulation chatbot can answer questions about policy. That can be useful, but it is not enough for operational administrative work.

The hard part is not only finding the right paragraph. The hard part is connecting a user's intent to the evidence required to execute it.

A useful system should be able to say:

- Here is the mission intent I understood.
- Here are the sources I checked.
- Here is the evidence I found.
- Here is the policy or checklist requirement it maps to.
- Here is what is missing or weak.
- Here is what a reviewer will likely object to.
- Here is the next action needed before routing.

That is a different product shape from chat.

A blank chat box asks the user to know what to ask. FieldDesk starts from the workflow and turns scattered context into structured work products. The interface is not centered on conversation. It is centered on readiness.

## The agent boundary

The prototype separates model reasoning from system verification.

The model owns semantic work:

- interpreting mission intent
- selecting relevant sources
- extracting facts from evidence
- identifying gaps and conflicts
- drafting reviewer objections and next actions

The application owns deterministic controls:

- source availability
- correction state
- schema validation
- per diem arithmetic
- audit trace
- final API contract

That boundary matters.

In high-trust workflows, the model should not be the only place where correctness lives. It can reason over messy context, but the platform should constrain what data is available, what tools can run, what math is trusted, what outputs are valid, and what gets handed to a human.

For example, FieldDesk keeps per diem calculation in deterministic code rather than asking the model to invent arithmetic. It uses structured schemas for agent output. It runs golden-scenario evaluations and LLM-as-judge checks for semantic quality. It treats the agent as one component in a workflow, not as the whole system.

That is the design lesson I keep coming back to:

> A model is not an operational system.

FieldDesk is another exploration of the layer around the model: tools, evidence, interface, evaluation, deterministic verification, and human review.

## Why administrative readiness matters

Administrative work is easy to dismiss because it looks like paperwork.

But paperwork is often how organizations coordinate action. It decides whether people move, equipment arrives, travel happens, funding is available, permissions are granted, and plans become executable.

If that layer is slow, the organization is slow.

This is especially true in high-trust environments. The answer cannot be to let AI silently skip review or invent missing facts. The answer is to make the workflow more legible before it reaches the reviewer.

The right AI system should compress the evidence surface without hiding accountability. It should preserve sources, surface gaps, and help humans make better decisions faster.

That is why FieldDesk is not framed as "automating paperwork" in the simplistic sense. The goal is administrative readiness:

```text
less hunting
less rework
clearer gaps
better review packages
faster execution
```

## The broader product thesis

FieldDesk is about one TDY workflow, but the pattern extends beyond TDY.

Many military administrative workflows have the same shape:

- leave
- supply
- maintenance
- range requests
- training approvals
- personnel actions
- deployment paperwork
- housing
- awards
- evaluations

Each workflow has local rules, required artifacts, source systems, reviewer expectations, and common failure modes. A strong process usually lives in someone's head, inbox, folder structure, or unit checklist.

FieldDesk points toward a system where those workflows can become reusable templates.

A unit should be able to encode the sources, requirements, checklist items, reviewer objections, and routing risks that matter for a workflow. The agent can then help gather evidence, reason across it, and prepare the package, while the platform preserves the trace and keeps humans accountable.

That is the useful version of AI in this context: not generic automation, but workflow memory and evidence-native assistance.

## Scope and safety

FieldDesk is a hackathon prototype, not a production military system.

The public repository uses synthetic demo data only. It contains no real personnel information, credentials, operational records, or government output. The connectors are mocked to show the workflow pattern without requiring access to live enterprise systems.

That constraint is intentional. The goal of the demo is to make the product shape inspectable and public-safe:

- agent-led evidence gathering
- gap detection
- correction staging
- deterministic verification
- reviewer-ready output

The real work would be integrating those patterns into approved environments, approved data sources, and accountable review processes.

## What I learned

The strongest AI products for government will probably not look like generic assistants.

They will look like workflow systems with models inside them.

The model will reason, but the product will define the task boundary. The product will decide what sources exist, what evidence counts, what output schema is valid, where uncertainty is shown, what a reviewer can inspect, and which actions require human approval.

That is the thread connecting FieldDesk, ATO Copilot, and the systems I keep building:

> high-trust work needs source-backed AI, not just fluent AI.

The bottleneck is shifting from access to model capability toward the ability to wrap that capability in systems that preserve evidence, judgment, and accountability.

FieldDesk is a small prototype pointed at that shift.

The prototype is public here: [https://github.com/EthanHNguyen/FieldDesk](https://github.com/EthanHNguyen/FieldDesk)

Sources: [SCSP Hackathon](https://www.scsp.ai/hackathon/), [AI+ Expo Hackathon](https://expo.scsp.ai/hackathon/), [FieldDesk repository](https://github.com/EthanHNguyen/FieldDesk).
