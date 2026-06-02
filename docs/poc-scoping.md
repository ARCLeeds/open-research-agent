# Open Research Workflow Agent — PoC Scoping Document

## Purpose

An open-source agent prompt and configuration, deployable across platforms, designed to help researchers and professional services staff navigate fragmented open research guidance and reflect on their own workflows.

The core problem it solves: open research guidance exists, but it is organised in ways that don't match how researchers think about their own situation. This agent meets researchers where they are — helping them identify relevant first steps and signposting where to go next, based on their context. It is not designed to be exhaustive; it is designed to make guidance navigable.

---

## Phase 1 — Core Question

> "How might I make my existing or planned research workflow more aligned with open research principles?"

---

## Phase 2 — Planned Extension *(out of scope for PoC)*

> "How might I articulate the open research principles I already embody — for example, in a funding application or impact statement?"

This would involve the agent reflecting the user's own responses back against relevant source material (e.g. funder guidance), using framing such as *"based on what you've said, you might consider including..."* The agent would not generate or recommend independently — it would surface connections between what the user has described and what a document already requires.

---

## Interaction Design

**Step 1 — Lifecycle stage**
The agent asks the user which stage of the research lifecycle they are currently at or planning for, from a constrained list:

- Planning and developing research
- Conducting research and acquiring data
- Analysing and sharing data
- Disseminating and publishing research

For the PoC, users will be directed to select **Planning and developing research**. The agent will respond to any other selection with a prompt indicating it is not yet able to help with that stage.

**Step 2 — Contextual questions**
A short, structured set of sequential questions to establish context. Sequential questioning is preferred over open description to reduce cognitive load and avoid exposing sensitive project information.

Where an initial question is high level, a positive answer may unlock a brief follow-up to gather just enough detail to make the output useful. Constrained answer options (e.g. a list to choose from) are preferred over free text where possible.

For the planning stage, questions will cover:

- **Funder** — which funder are they applying to or in receipt of funding from, if any (priority: UKRI, Wellcome Trust)
- **Outputs** — what kinds of outputs will the research produce? *(constrained list: data, software, publications, tools, frameworks, documentation, other)*
- **Collaboration and engagement** — does the research involve societal actors, end-users or external partners? If yes: a brief follow-up on their role (e.g. participants, co-creators, intended beneficiaries)
- **Legal and security considerations** — does the research involve sensitive data, IP considerations, consent requirements, or collaboration across international boundaries?
- **Researcher capability** — how confident does the researcher feel discussing the technical aspects of their research workflow, e.g. data formats, software, computational methods? *(three-point scale: not very / somewhat / quite confident)*

**Step 3 — Output**
Surfaced considerations and suggested first steps relevant to their context — including links to relevant platforms, portals, and guidance documents from the approved source set. The agent identifies where to start and where to go next, not everything to do.

---

## Agent Behaviour Principles

- **Signpost, don't recommend** — the agent does not make recommendations; it surfaces relevant considerations and questions for the user to pursue
- **Ask, don't advise** — in areas of ambiguity, institutional variance, or security risk, offer questions the researcher should explore, not answers
- **Reflect, don't generate** — outputs are grounded in the approved source set and the user's own responses; the agent does not independently compose guidance
- **Configurable source set** — the default source set can be extended or substituted; publicly available institutional policy documents are explicitly supported as additions
- **Entry points over exhaustiveness** — the agent helps researchers identify where to start, not everything they should eventually do

---

## Source Strategy

*(Action required — next step before further interaction design)*

The usefulness of the agent's output depends entirely on the quality and coverage of the source set. Sources should be mapped to lifecycle stage and consideration type (outputs, collaboration, legal, funder requirements etc.) so the agent can surface relevant links and guidance rather than generic observations.

### Principles
- Public domain only
- Where institutional policy is included, it must be publicly available online and relevant to informing the considerations and priorities the agent surfaces
- Hosted in a public GitHub repository for transparency and reuse
- The source set is configurable: deployers can add or substitute their own preferred source material

### Priority sources to identify
- UKRI open research policy and guidance
- Wellcome Trust open research requirements
- Reputable, widely-used frameworks and guidance adopted across UK research institutions, including domain-specific resources where relevant
- Platforms and portals relevant to sharing research outputs (e.g. data repositories, software sharing platforms)
- Relevant institional policy
- Any curated resource list to be maintained in the repo

---

## Implementation at the Event

- **Platform:** Microsoft Copilot (custom chat agent)
- **Knowledge base:** specified sources only (e.g. public GitHub repo)
- **Prompt, instructions, and knowledge** to be fully open and platform-agnostic
- **Goal:** proof of concept — validate the interaction design and usefulness of outputs, not production readiness
- **Scope constraint:** users will be directed to use the Planning and developing research stage only

---

## Open Questions to Resolve

1. How dynamic is the source list — fixed at deployment, or updatable via the repo without changing the agent config?
2. What's the governance model for the source set over time?