# Agentic Tools for the Tableau Workflow

A collection of Claude skills built around Tableau MCP to help practitioners design dashboards, author calculations, generate synthetic data, evaluate visualizations, document analytics assets, improve governance, and build judgment through practice.

I've spent over a decade building Tableau content and helping teams get better at it. These tools represent what I kept wishing existed: structured, repeatable approaches to the parts of the workflow that eat up time or fall through the cracks.

Each skill runs inside Claude Desktop with Tableau MCP connected. You describe what you need in natural language, and the skill handles the methodology, API calls, and output formatting. **[Blog](https://medium.com/design-bootcamp/from-dashboards-to-agents-ffe773fd8267)** on Bootcamp via Medium (no paywall).

---

## The Workflow
```
DATA ──→ DESIGN ──→ BUILD ──→ REVIEW ──→ DOCUMENT ──→ GOVERN
                          ↑
                        LEARN (judgment across all stages)
```
| Stage | Tool | What it does |
|-------|------|-------------|
| **Data** | [Hyper Synthetic Forge](https://github.com/adammico-lab/hyper-synthetic-forge) | Generate realistic synthetic datasets from schemas, profiles, or plain-language descriptions |
| **Data** | [Data Quality Sentinel](https://github.com/adammico-lab/Tableau-Data-Quality-Sentinel-BETA) | Profile datasources for naming violations, type mismatches, metadata gaps, and schema hygiene |
| **Design** | [Tableau Dashboard Blueprint](https://github.com/adammico-lab/Tableau-Dashboard-Blueprint-BETA) | Recommend chart types, layout, filters, colors, and interaction design before you build |
| **Design** | [Pulse Blueprint](https://github.com/adammico-lab/Pulse-Blueprint-BETA) | Design, audit, and optimize Tableau Pulse metric definitions |
| **Build** | [Calc Engine](https://github.com/adammico-lab/Tableau-Calc-Engine-BETA) | Write, debug, translate, and optimize calculated fields (LODs, table calcs, sets, parameters) |
| **Review** | [VizCritique Pro](https://github.com/adammico-lab/vizcritique-pro) | Score dashboards across seven domains with prioritized, actionable recommendations |
| **Document** | [Tableau Scribe](https://github.com/adammico-lab/Tableau-Scribe-BETA) | Auto-generate dashboard documentation and metric dictionaries from live content |
| **Govern** | [Governance Scanner](https://github.com/adammico-lab/Tableau-Governance-Scanner-BETA) | Audit a Tableau site for stale content, naming violations, uncertified sources, and hygiene gaps |
| **Learn** | [TableauQuest](https://github.com/adammico-lab/Tableau-Quest) | Interactive choose-your-own-adventure that teaches Tableau judgment through realistic consequences |

---

## Quick Start

### Prerequisites

- Claude Desktop with agent mode enabled
- Tableau MCP installed and authenticated
- Access to a Tableau Cloud or Tableau Server site

### Install any skill
1. Clone or download the repository for the skill you want.
2. Copy the skill folder into your Claude skills directory.
3. Restart Claude Desktop.
4. Confirm Tableau MCP is connected (you should see your site's content).
5. Try one of the example prompts in that skill's README.

---

## Where to Start

| Situation | Start here |
|-----------|-----------|
| Building something new | Dashboard Blueprint. Give it your datasource and business questions, and it will recommend what to build before you open a worksheet. |
| Have existing dashboards | VizCritique Pro. Point it at a published view and get a structured evaluation with specific fixes. |
| Need test data | Hyper Synthetic Forge. Describe what you need or point it at an existing datasource to clone. |
| Inheriting someone else's work | Tableau Scribe. It will document what's there so you don't have to reverse-engineer it. |
| Want to sharpen your decision-making | TableauQuest. It drops you into realistic Tableau scenarios and lets you learn judgment through consequences, not instruction. |

---

## Maturity
| Tool | Status | Version |
|------|--------|---------|
| VizCritique Pro | Public Beta | v1.1 |
| Hyper Synthetic Forge | Public Beta | v3.0 |
| Calc Engine | Public Beta | v1.1 |
| Dashboard Blueprint | Public Beta | v1.1 |
| Governance Scanner | Public Beta | v2.0 |
| Tableau Scribe | Public Beta | v1.0 |
| Data Quality Sentinel | Public Beta | v3.1 |
| Pulse Blueprint | Public Beta | v2.1 |
| TableauQuest | Public | v3.1 |

All tools are functional and actively used, but APIs, scoring methodologies, and output formats may evolve based on feedback.

---

## How These Work Together

These aren't isolated utilities. They're designed to hand off to each other across the workflow:
- **Data Quality Sentinel** flags field issues before you build, so **Dashboard Blueprint** starts with clean inputs.
- **Dashboard Blueprint** produces a design spec that **Calc Engine** can reference when authoring calculations.
- **VizCritique Pro** identifies what to fix after you build, giving you a prioritized punch list.
- **Tableau Scribe** documents what you shipped, so future maintainers (or future you) don't start from scratch.
- **Governance Scanner** monitors the broader site, catching what falls through the cracks over time.
- **TableauQuest** reinforces judgment across the entire workflow. After a scenario involving calculations, it can hand off to **Calc Engine** for real practice. Governance scenarios bridge to **Governance Scanner**. Design scenarios connect to **Dashboard Blueprint**.

---

## Data Access and Permissions

These tools interact with your Tableau environment through MCP. Here's what each one reads:
| Tool | Metadata | Rendered Images | Aggregate Values | Row-Level Data | Writes to Tableau |
|------|----------|-----------------|------------------|----------------|-------------------|
| Dashboard Blueprint | Yes | No | No | No | No |
| VizCritique Pro | Yes | Yes | No | No | No |
| Hyper Synthetic Forge | Yes | No | Yes (for profiling) | No | No |
| Calc Engine | Yes | No | No | No | No |
| Tableau Scribe | Yes | Yes | No | No | No |
| Governance Scanner | Yes | No | Limited | No | No |
| Data Quality Sentinel | Yes | No | No | No | No |
| Pulse Blueprint | Yes | No | No | No | No |
| TableauQuest | Yes (Field Quest mode) | No | No | No | No |

No tool writes back to your Tableau environment. All processing happens locally through Claude Desktop.

---

## About

I'm Adam Mico. I'm a Director of Product Management at Salesforce working in the Data Cloud organization for the CCO. I've been part of the Tableau community since 2019, was a Tableau Visionary and Ambassador, and I co-led and co-found the AI and Tableau User Group until March 2026. I build these tools because I use them myself and because I think agentic workflows are the next step for analytics practitioners. Questions, feedback, or ideas: open an issue in any repository or connect with me on [LinkedIn](https://www.linkedin.com/in/adammico/).

---

## License

Each repository includes its own license file. See the individual repos for details.

---

*This is an independent community project. It is not affiliated with, endorsed by, or officially connected to Salesforce or Tableau. Tableau is a trademark of Salesforce, Inc.*
