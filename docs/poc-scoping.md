# Open Research Workflow Agent — PoC Scoping Document

## Purpose

An open-source agent prompt and configuration, deployable across platforms, designed to help researchers and professional services staff navigate fragmented open research guidance and reflect on their own workflows.

The core problem it solves: making it easier for a researcher to identify relevant, actionable considerations without having to trawl through large volumes of guidance documentation themselves.

---

## Phase 1 — Core Question

> "How might I make my existing or planned research workflow more aligned with open research principles?"

---

## Phase 2 — Planned Extension *(out of scope for PoC)*

> "How might I articulate the open research principles I already embody — for example, in a funding application or impact statement?"

This would involve the agent reflecting the user's own responses back against relevant source material (e.g. funder guidance), using framing such as *"based on what you've said, you might consider including..."* The agent would not generate or recommend independently — it would surface connections between what the user has described and what a document already requires.

---

## Interaction Design

**Step 1 — Intent clarification**
The agent opens by asking the user what they are looking for help with:
- **(a) Existing workflow** — identify considerations and potential improvements with respect to open research practice
- **(b) Planned workflow** — explore open research principles relevant to a workflow they are designing

**Step 2 — Contextual questions**
A short, structured set of questions to establish context, covering:
- Nature of the workflow (existing or planned; what stage)
- Funder (with priority focus on **UKRI** and **Wellcome Trust**)
- Researcher digital skills / capability level *(framing for this still to be defined)*

**Step 3 — Output**
Surfaced questions and considerations relevant to their context, and suggested next steps — drawn from the approved source set, not independently generated.

---

## Agent Behaviour Principles

- **Signpost, don't recommend** — the agent does not make recommendations; it surfaces relevant considerations and questions for the user to pursue
- **Ask, don't advise** — in areas of ambiguity, institutional variance, or security risk, offer questions the researcher should explore, not answers
- **Reflect, don't generate** — outputs are grounded in the approved source set and the user's own responses; the agent does not independently compose guidance
- **Configurable source set** — the default source set can be extended or substituted; publicly available institutional policy documents are explicitly supported as additions

---

## Source Strategy

*(Action required — to be completed before build)*

### Principles
- Public domain only
- Where institutional policy is included, it must be publicly available online
- Hosted in a public GitHub repository for transparency and reuse
- The source set is configurable: deployers can add or substitute their own preferred source material

### Priority sources to identify
- UKRI open research policy and guidance
- Wellcome Trust open research requirements
- Discipline-agnostic open research frameworks (e.g. UNESCO, UKRN, TOP Guidelines)
- Any curated resource list to be maintained in the repo

---

## Implementation at the Event

- **Platform:** Microsoft Copilot (custom chat agent)
- **Knowledge base:** specified sources only (e.g. public GitHub repo)
- **Prompt, instructions, and knowledge** to be fully open and platform-agnostic
- **Goal:** proof of concept — validate the interaction design and usefulness of outputs, not production readiness

---

## Open Questions to Resolve

1. How do you define or proxy "researcher digital skills competency" in a short interaction? (A scale? Self-reported comfort level? Task-based?)
2. How dynamic is the source list — fixed at deployment, or updatable via the repo without changing the agent config?
3. What's the governance model for the source set over time?