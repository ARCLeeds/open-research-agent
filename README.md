# Open Research Workflow Agent

Building blocks for an open, platform-agnostic open research methodology agent.

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

## What this is

This repository contains the building blocks for a simple AI agent designed to help researchers and research support staff navigate open research guidance in a more usable and proportionate way.

Across disciplines, researchers are asked to engage with increasing amounts of guidance around open research, data, software, ethics, and good practice. While this guidance is important, it is often extensive, fragmented, and time-consuming to navigate — particularly for early-career researchers, those working across disciplines, or anyone encountering unfamiliar expectations. One consequence of this is rarely discussed: people may choose not to engage with guidance at all, not because they don't care about research quality, but because the cognitive and time burden feels too high.

This agent is a modest attempt to address that problem. It acts as a navigation aid — helping users surface relevant considerations, prioritise what matters in their context, and identify where further advice or referral may be useful. It does not provide definitive answers, compliance judgements, or advice on specific methods or tooling. It draws only on publicly available sources.

## Current status

This is an early-stage proof of concept. It was developed as a demonstration tool for a workshop exploring whether AI-based tools could support researchers in navigating open research guidance — not by simplifying research practice or removing judgement, but by making guidance more accessible and proportionate to context.

At this stage, the agent supports one lifecycle stage only: **planning and developing research**. Support for further lifecycle stages is planned.

## How it was developed

This proof of concept was developed with support from Claude Sonnet 4.6 (Anthropic), used as a thinking partner and drafting aid throughout the design and documentation process. This includes the scoping document, the knowledge source list, source annotations, and this README.

We are being transparent about this because the project is about responsible and open use of AI in research contexts, and it would be inconsistent not to acknowledge it here.

The use of an AI assistant in development does not mean the outputs are unreviewed. All content has been checked and edited by a human. However, as with any AI-assisted work, readers should apply their own judgement, particularly to source annotations and any statements about funder policy, which should be verified against primary sources.

## Source strategy

The agent is instructed to prefer sources from a curated list of reputable, publicly available guidance maintained in this repository. However, it is not restricted to those sources alone.

This is a deliberate decision. Restricting the agent to a fixed source list risks it sounding authoritative while actually having an artificially narrow view of a fast-moving and genuinely multidisciplinary space. Open research guidance spans multiple disciplines, funders, institutions, and regulatory contexts — a fixed list will always have gaps, and over-constraining the agent risks producing responses that refuse to engage with legitimate questions simply because a relevant source wasn't anticipated when the list was compiled.

The trade-off is that not all sources the agent draws on will have been reviewed or curated. **Users should always verify links and check claims against primary sources**, particularly for anything touching funder policy, data protection, or institutional requirements. The agent is a starting point for exploration, not an authoritative reference.

## Known limitations

### Limitations of the agent itself

- **Coverage of the curated source list is incomplete.** The agent draws on a curated list of reputable sources as a preference, but is not restricted to it. See *Source strategy* above.
- **Source citation is inconsistent.** The agent does not always attribute statements to named sources, even when instructed to do so. Where citations are provided, they should be verified.
- **Coverage is limited to the planning stage.** The agent is not yet configured to support other lifecycle stages and will decline to help with them.
- **It is not a substitute for specialist advice.** For questions involving data protection, intellectual property, ethics, or funder compliance, users should consult their institution's specialist support teams.

### Limitations encountered when deploying in Microsoft Copilot

These limitations are specific to the Microsoft Copilot Studio platform and may not apply to other deployment contexts:

- **URL depth restriction.** Copilot only allows knowledge source URLs up to two levels deep (e.g. `domain.com/path`). This excludes most pages in documentation sites, funder guidance, and GitHub repositories, which are typically three or more levels deep.
- **Maximum of four knowledge source URLs.** The platform limits the number of specified knowledge sources to four URLs. This makes it impractical to point the agent directly at a comprehensive source list.
- **GitHub repositories are not reliably indexed.** Pointing the agent at a GitHub repository does not reliably give it access to the file contents within that repository.
- **Workaround adopted.** To address these constraints, the curated source list is published as a GitHub Pages site at `https://arcleeds.github.io/open-research-agent`, which falls within the URL depth limit and can be used as one of the four knowledge source slots. The agent is instructed to refer to this page when making further reading recommendations.

These constraints significantly affect how much the agent can draw on specified sources in practice. They are worth understanding before investing time in curating a knowledge base for deployment on this platform.

## What's in this repository

- **`knowledge/index.md`** — the curated list of publicly available sources the agent draws on, organised by category. This is the primary knowledge base for the agent. It is designed to be configurable: deployers are encouraged to add or substitute sources appropriate to their institutional context.
- **`knowledge/illustrative-examples.md`** — illustrative examples of open research principles in practice, across different research contexts and output types. These are intended to help ground abstract considerations in realistic scenarios and are drawn on by the agent when relevant.
- **`docs/scoping-document.md`** — the scoping document describing the design intent, interaction design, and open questions behind the agent.
- **`implementations/copilot-chat.md`** — the configurations for an implementation in M365 as a copilot chat agent.

The agent prompt and description are not yet saved as files in this repository. This is planned.

## How it works

The agent asks a researcher a short series of questions about their project — their funder, expected outputs, whether their research involves external partners or sensitive data, and their confidence with technical aspects of their workflow. It uses those responses to surface relevant open research considerations and signpost appropriate resources, drawn from the curated source list.

It is designed around a small number of principles:

- **Signpost, don't recommend** — the agent surfaces considerations and questions, not instructions
- **Ask, don't advise** — in areas of ambiguity or risk, it raises questions for the researcher to explore with appropriate support
- **Entry points over exhaustiveness** — it helps researchers identify where to start, not everything they should eventually do
- **Configurable source set** — the knowledge base can be extended or substituted to fit different institutional contexts

## How to deploy it

The agent prompt and knowledge base are designed to be platform-agnostic. The proof of concept was implemented using Microsoft Copilot Studio, but the instructions and source list can be adapted for other platforms. See the known limitations section above before deploying on Copilot.

To deploy your own version:

1. Use the agent prompt (to be published in this repository) as your system instructions
2. Point the agent at `https://arcleeds.github.io/open-research-agent` as a knowledge source, or host your own adapted version of the source list
3. Substitute or extend the institutional guidance section of `pages/index.md` with sources appropriate to your context

## How to contribute

Contributions are welcome and the project will benefit from them. The most useful things people can add are:

- **Sources** — additional reputable, publicly available guidance relevant to open research planning. If you know of funder policies, institutional frameworks, or discipline-specific guidance that isn't currently represented, please suggest it or submit a pull request to `pages/index.md`.
- **Annotations** — richer or more accurate descriptions of existing sources, particularly where the current annotation doesn't reflect a source's full relevance or scope.
- **Illustrative examples** — new scenarios in `examples.md` that show open research principles in practice across different research contexts, disciplines, or output types.

If you're not comfortable with GitHub, you're welcome to raise suggestions as an issue or get in touch directly.

## Licence

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

This project is released under [CC0 1.0 Universal (Public Domain Dedication)](http://creativecommons.org/publicdomain/zero/1.0/). You are free to copy, adapt, and reuse any part of it without attribution.

The content of this repository — sources, annotations, and illustrative examples — draws substantially on community-produced knowledge and publicly available guidance. Claiming ownership over a curation of others' work would be inconsistent with the collaborative and open spirit the project is trying to embody, and would sit awkwardly alongside an invitation to others to contribute to it.

This does not affect any intellectual property that may arise from use of the tool within an experimental process — including findings, analysis, and conclusions about the design and effectiveness of this kind of tool.