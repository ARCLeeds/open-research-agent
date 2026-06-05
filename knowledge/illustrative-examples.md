# Illustrative Examples of Open Research in Practice

This file contains constructed scenarios illustrating how open research principles can apply at the planning stage of different research projects. These examples are intended to help ground abstract considerations in realistic contexts. They are not based on real individuals or projects.

---

## Where software or code outputs are envisaged

### Example 1: Making software citable and traceable from publications

A researcher is developing a computational tool as part of a funded project. They plan to publish findings in a journal article and want to ensure that other researchers can locate and cite the exact version of the software used in the analysis.

**What open research looks like here:**

- The researcher hosts their code on GitHub and uses the [Zenodo–GitHub integration](https://zenodo.org) to automatically archive each release and generate a persistent Digital Object Identifier (DOI). This means the software can be cited independently of any paper, and each version has its own unique, stable reference.
- A `CITATION.cff` file is added to the root of the repository. This plain-text file specifies how the software should be cited — including author names, version, and DOI — and is automatically recognised by GitHub, which displays a "Cite this repository" option on the repository page.
- When the journal article is published, the software DOI is included in the references or data availability statement, creating a traceable link from the publication to the exact code used.

**Why this matters:**

Software used in research is often invisible in the scholarly record — referenced vaguely or not at all — which makes it difficult to reproduce results or give credit to developers. Citing software with a DOI makes it a first-class research output, supports reproducibility, and allows software contributions to be recognised in research evaluation.

**Further reading:**

- [How to make your research software citable](https://arc.leeds.ac.uk/knowledge-centre/how-to-make-your-research-software-citable/) — ARC Leeds
- [Software Citation with CITATION.cff](https://book.the-turing-way.org/communication/citable/citable-cff/) — The Turing Way
- [Making code citable with Zenodo and GitHub](https://www.software.ac.uk/blog/making-code-citable-zenodo-and-github) — Software Sustainability Institute

---

### Example 2: Open development practices from the start

A research team is building a data processing pipeline that will underpin several publications over a multi-year project. They are deciding at the planning stage how to manage and share the codebase.

**What open research looks like here:**

- The team uses a public version-controlled repository (e.g. GitHub or GitLab) from the beginning, rather than sharing code only at the point of publication. This makes the development process itself transparent, and allows others to follow or contribute as the work evolves.
- They choose an open source licence early in the project — for example, MIT or Apache 2.0 — to make clear that others can reuse and adapt the code. Leaving this decision until later can create complications, particularly where multiple institutions or funders are involved.
- The repository includes a `README` that explains what the software does, what dependencies it requires, and how to run it. This is treated as a living document, not an afterthought.
- Issues and planned features are tracked openly in the repository's issue tracker, giving external collaborators visibility into the project's direction.

**Why this matters:**

Starting with open development practices is significantly easier than retrofitting them before publication. Decisions about licensing, documentation, and version control are much harder to make under deadline pressure. Building these in from the start also means the codebase is more likely to be genuinely reusable, not just technically public.

**Further reading:**

- [The Turing Way: Version Control](https://book.the-turing-way.org/reproducible-research/vcs) — guidance on using version control in research contexts
- [Choose an open source licence](https://choosealicense.com) — a plain-language guide to common software licences
- UKRI expectations for software outputs: [UKRI open research hub](https://www.ukri.org/manage-your-award/good-research-resource-hub/open-research/)

---

## Where tools, learning resources, or public-facing outputs are envisaged

### Example 3: Stakeholder engagement and user-centred design in a health equity e-learning project

A research team studying racial and gender inequalities in healthcare has committed in their grant application to producing e-learning modules for use in clinical education. The goal is to help future practitioners recognise and address bias in their practice.

**What open research looks like here:**

- Before any content is developed, the team maps the stakeholders with a meaningful interest in the resource: not only educators and curriculum leads who might embed it, but — crucially — people from the communities whose experiences of healthcare inequity the resource is about. These groups are identified and engaged early, not consulted after decisions have already been made.
- The design process is documented as it unfolds. When the team makes decisions about framing, language, or content — for example, how to present clinical case studies, or whose voices are foregrounded — they record what informed those decisions: who they spoke with, what was said, and what changed as a result. This creates a traceable record of how the resource came to be.
- Where possible, community representatives are involved not just as consultees but as contributors to the design itself — shaping what questions the modules ask and how practitioners are invited to reflect.

**Why this matters:**

A resource designed to address racial inequity in healthcare carries a particular responsibility. If the decisions about how to frame that inequity — what to name, what to emphasise, whose experience to centre — are made exclusively by researchers who are not from the affected communities, the resource risks reproducing the same dynamic it is trying to correct: well-intentioned people making decisions about others, without those others in the room.

Transparency here is not just procedurally good practice. It is part of what makes the research credible and the resource trustworthy. Documenting who shaped the design, and how, makes it possible for communities, educators, and funders to scrutinise those decisions — and for future researchers to build on them honestly.

**Further reading:**

- [UKRI guidance on co-production in research](https://www.ukri.org/what-we-do/public-engagement/co-producing-research/) — including principles for meaningful community involvement
- [UK Standards for Public Involvement](https://sites.google.com/nihr.ac.uk/pi-standards/home) — NIHR framework for involving the public in research
- [The Turing Way: Participatory Research](https://book.the-turing-way.org/ethical-research/participatory-research) — practical guidance on participatory approaches

---

### Example 4: User research and the decision to build two artefacts in a heritage digitisation project

A research team is digitising and analysing a collection of historical artefacts — letters, photographs, and records — with the intention of making them more widely accessible. Their grant application commits to producing an interactive portal as an output. As they begin planning, they identify two distinct groups who might use it: other researchers working in the same field, and members of the public, some of whom may have a personal or community connection to the collection.

**What open research looks like here:**

- The team conducts structured user research with both groups before any design decisions are made — not to validate a solution they have already settled on, but to understand what each group actually needs from the collection and what barriers they might face in accessing it.
- What they find is that the needs diverge significantly. Researchers need to be able to download data in interoperable formats, understand the provenance and completeness of the digitised records, filter and query across the collection, and cite specific items or versions in publications. Members of the public — particularly those with family or community connections to the material — need contextual interpretation, accessible language, and some agency over how they engage with what may be personally significant content. They are not simply consumers of data; they may have knowledge that enriches it.
- On the basis of this user research, the team decides that a single portal cannot serve both groups well without compromising for both. They document this decision explicitly — recording what they learned from each group, what trade-offs a unified artefact would involve, and why two distinct outputs better serve the stated aims of the project. This documentation becomes part of the project record.
- The researcher-facing output prioritises interoperability and citability: data is available in standard formats, items have persistent identifiers, and provenance is clearly described. The public-facing output prioritises accessibility and interpretation: it is designed with, not just for, community members, and includes mechanisms for people to contribute contextual knowledge about the collection.

**Why this matters:**

"Open" means different things depending on who something is for and what it is trying to enable. A portal that is technically open — publicly accessible, freely available — can still be effectively closed to most of its intended users if it assumes expertise they do not have, or if it offers no meaningful role to people whose knowledge could enrich the collection.

The open research behaviour here is not simply making the artefacts available. It is treating the design process itself as a research activity: using evidence from user research to drive decisions, documenting the reasoning transparently, and recognising that different purposes require different solutions. The decision to build two artefacts, grounded in documented user research, is itself a traceable and accountable research output.

**Further reading:**

- [The Turing Way: Participatory Research](https://book.the-turing-way.org/ethical-research/participatory-research) — practical guidance on involving users in research design
- [UK Standards for Public Involvement](https://sites.google.com/nihr.ac.uk/pi-standards/home) — NIHR framework applicable beyond health research
- [FAIR Principles](https://www.go-fair.org/fair-principles/) — for the researcher-facing output, these provide a useful framework for thinking about findability, accessibility, interoperability, and reuse

---

*Further examples will be added in due course. Consider becoming a contributor to help us expand the list of examples and improve the Open Research Agent.*