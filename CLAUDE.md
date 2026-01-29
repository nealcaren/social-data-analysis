# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This repository provides a Claude Code plugin marketplace with skills (agents) for rigorous social science research analysis. Each skill guides users through a structured, phased workflow with pauses for user input at each stage.

## Installation

Users can install this plugin marketplace and individual plugins with:

```bash
# Add the marketplace
/plugin marketplace add nealcaren/social-data-analysis

# Install only the plugins you need
/plugin install r-analyst@social-data-analysis
/plugin install stata-analyst@social-data-analysis
/plugin install interview-analyst@social-data-analysis
/plugin install interview-writeup@social-data-analysis
/plugin install dag-development@social-data-analysis
/plugin install abductive-analyst@social-data-analysis
/plugin install text-analyst@social-data-analysis
/plugin install lecture-designer@social-data-analysis
/plugin install lit-search@social-data-analysis
/plugin install lit-synthesis@social-data-analysis
/plugin install lit-writeup@social-data-analysis
/plugin install interview-bookends@social-data-analysis
/plugin install genre-skill-builder@social-data-analysis
/plugin install methods-writer@social-data-analysis
/plugin install case-justification@social-data-analysis
/plugin install revision-coordinator@social-data-analysis
```

## Available Skills

After installation, invoke skills with:

| Skill | Purpose | Invocation |
|-------|---------|------------|
| **R Analyst** | Statistical analysis in R for publication | `/r-analyst` |
| **Stata Analyst** | Statistical analysis in Stata for publication | `/stata-analyst` |
| **Interview Analyst** | Qualitative analysis of interview data | `/interview-analyst` |
| **Interview Write-Up** | Write-up support for interview methods and findings | `/interview-writeup` |
| **DAG Development** | Develop causal diagrams and render publication-ready figures | `/dag-development` |
| **Abductive Analyst** | Abductive analysis (Timmermans & Tavory) | `/abductive-analyst` |
| **Text Analyst** | Computational text analysis (R/Python) | `/text-analyst` |
| **Lecture Designer** | Transform chapters into engaging lectures | `/lecture-designer` |
| **Lit Search** | Build literature databases via OpenAlex | `/lit-search` |
| **Lit Synthesis** | Deep reading, theoretical mapping, debate identification | `/lit-synthesis` |
| **Lit Write-Up** | Draft publication-ready Theory sections | `/lit-writeup` |
| **Interview Bookends** | Draft introductions and conclusions from theory/findings | `/interview-bookends` |
| **Genre Skill Builder** | Create genre-analysis-based writing skills from a corpus | `/genre-skill-builder` |
| **Methods Writer** | Draft Methods sections for interview articles (3 pathways) | `/methods-writer` |
| **Case Justification** | Draft case justification sections (5 clusters) | `/case-justification` |
| **Revision Coordinator** | Orchestrate manuscript revision by routing feedback to skills | `/revision-coordinator` |

## Unified Phased Architecture

All skills follow the same phased structure with pauses between phases:

### Statistical Analysis (R & Stata)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Research Design** | Establish identification strategy | User confirms design |
| **1: Data Familiarization** | Understand data before modeling | User reviews descriptives |
| **2: Model Specification** | Fully specify before estimation | User approves specification |
| **3: Main Analysis** | Run primary models | User reviews results |
| **4: Robustness** | Stress-test findings | User assesses robustness |
| **5: Output** | Publication-ready outputs | Analysis complete |

### Interview Analysis

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Theory Synthesis** | Build theoretical sensitivity (Track A only) | User confirms framework |
| **1: Immersion** | Deep familiarity with data | User reviews observations |
| **2: Coding** | Systematic categorization | User reviews coding structure |
| **3: Interpretation** | Move from "what" to "why" | User reviews explanations |
| **4: Quality Check** | Evaluate against quality indicators | User addresses gaps |
| **5: Synthesis** | Integrate into coherent argument | Analysis complete |

### Abductive Analysis (Timmermans & Tavory)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Theoretical Preparation** | Build theoretical sensitivity | User confirms theoretical map |
| **1: Familiarization** | Open coding, flag surprises | User reviews initial codes |
| **2: Theoretical Casing** | Apply multiple lenses to excerpts | User reviews casings |
| **3: Anomaly Analysis** | Identify contradictions and puzzles | User confirms focus |
| **4: Memo Writing** | Develop tentative theory | User tests interpretations |
| **5: Integration** | Test against full dataset | User reviews synthesis |
| **6: Writing Up** | Rhetorical abduction for publication | Analysis complete |

### Text Analysis (R/Python)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Research Design** | Method selection, language choice | User confirms design |
| **1: Corpus Preparation** | Load, clean, explore text | User reviews preprocessing |
| **2: Specification** | Document preprocessing, parameters | User approves specification |
| **3: Analysis** | Run topic models, classifiers, etc. | User reviews results |
| **4: Validation** | Human validation, diagnostics | User assesses validity |
| **5: Output** | Publication-ready outputs | Analysis complete |

### Lecture Design

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Context & Outcomes** | Define measurable learning outcomes | Instructor confirms outcomes |
| **1: Content Audit & Narrative** | ABT arc, hook, chunk map | Instructor reviews narrative |
| **2: Active Learning** | Polls, ConcepTests, peer instruction | Instructor reviews activities |
| **3: Slide Development** | Google Slides via MCP with speaker notes | Instructor reviews slides |
| **4: Review & Refinement** | Timing audit, backup plans | Lecture package complete |

> **Note**: Lecture Designer requires the [Google Docs MCP](https://github.com/nealcaren/google-docs-mcp) to create slides directly in Google Slides.

### The Lit Trilogy

Three skills form a complete literature review workflow:

| Skill | Role | Key Output |
|-------|------|------------|
| **lit-search** | Find papers via OpenAlex | `database.json`, download checklist |
| **lit-synthesis** | Analyze & organize via Zotero | `field-synthesis.md`, `theoretical-map.md` |
| **lit-writeup** | Draft prose | Publication-ready Theory section |

> **Note**: lit-synthesis requires the [Zotero MCP](https://github.com/54yyyu/zotero-mcp) for full-text access.

### Literature Search (OpenAlex)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Scope Definition** | Define topic, search terms, criteria | User confirms search strategy |
| **1: Initial Search** | Query OpenAlex, build corpus | User reviews corpus composition |
| **2: Screening** | Filter with LLM assistance | User reviews borderline cases |
| **3: Snowballing** | Expand via citation networks | User approves additions |
| **4: Full Text** | Identify OA sources, download checklist | User obtains missing PDFs |
| **5: Annotation** | Extract structured information | User reviews extractions |
| **6: Synthesis** | Generate database, identify gaps | Database complete |

### Literature Synthesis (Zotero)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Corpus Audit** | Assess coverage, set reading priorities | User confirms priorities |
| **1: Deep Reading** | Close read priority papers | User reviews reading notes |
| **2: Theoretical Mapping** | Identify traditions and lineages | User reviews theoretical landscape |
| **3: Thematic Clustering** | Organize papers by focus and method | User reviews clustering |
| **4: Debate Mapping** | Identify tensions and competing positions | User selects focus areas |
| **5: Field Synthesis** | Integrate understanding, recommend approach | Handoff to lit-writeup |

### Literature Write-Up

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Assessment** | Identify contribution type, select cluster | User confirms cluster |
| **1: Architecture** | Design structure, subsections, arc | User approves architecture |
| **2: Planning** | Map paragraph functions and sequence | User reviews paragraph map |
| **3: Drafting** | Write paragraphs with sentence-level craft | User reviews each subsection |
| **4: Turn** | Craft the gap/contribution pivot | User evaluates turn |
| **5: Revision** | Calibrate against norms, polish | User approves final |

### Interview Bookends

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Intake** | Review inputs, identify cluster, confirm scope | User confirms cluster |
| **1: Introduction** | Draft introduction matching cluster style | User reviews introduction |
| **2: Conclusion** | Draft conclusion with all standard elements | User reviews conclusion |
| **3: Coherence** | Verify promise-delivery alignment, callbacks | User approves coherence |

### Genre Skill Builder (Meta-Skill)

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Scope Definition** | Define target section, select model skill | User confirms scope |
| **1: Corpus Immersion** | Quantitative profiling of corpus | User reviews statistics |
| **2: Genre Coding** | Systematic coding of genre features | User reviews codebook |
| **3: Interpretation** | Pattern analysis, cluster discovery | User confirms clusters |
| **4: Generation** | Build skill files from templates | User reviews generated skill |
| **5: Validation** | Quality check, optional testing | Skill ready for use |

### Methods Writer

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Assessment** | Gather study info, select pathway | User confirms pathway |
| **1: Drafting** | Write section following pathway template | User reviews draft |
| **2: Revision** | Calibrate against benchmarks, polish | Section complete |

### Case Justification

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Assessment** | Gather case info, select cluster | User confirms cluster |
| **1: Drafting** | Write section following cluster template | User reviews draft |
| **2: Revision** | Calibrate against benchmarks, polish | Section complete |

### Revision Coordinator (Meta-Skill)

Orchestrates manuscript revision by routing feedback to specialized skills:

| Phase | Goal | Pause Point |
|-------|------|-------------|
| **0: Intake** | Parse feedback into items, map to sections | User confirms routing |
| **1: Diagnostic** | Assess clusters/pathways, determine entry points | User confirms strategy |
| **2: Dispatch** | Route sections to skills for revision | User reviews each section |
| **3: Integration** | Cross-section coherence checks | User approves coherence |
| **4: Verification** | Audit all items, generate response memo | Revision complete |

**Skill Routing**:

| Section | Primary Skill |
|---------|---------------|
| Introduction | `interview-bookends` |
| Conclusion | `interview-bookends` |
| Theory/Literature | `lit-writeup` |
| Methods | `methods-writer` |
| Case Justification | `case-justification` |
| Findings | Direct guidance |
| Discussion | Direct guidance |

## Repository Structure

```
.claude-plugin/
└── marketplace.json          # Plugin marketplace definition (17 plugins)

plugins/
├── r-analyst/
│   └── skills/r-analyst/
│       ├── SKILL.md          # Main R analyst skill
│       ├── phases/           # Phase agent files
│       └── techniques/       # R method reference guides
│
├── stata-analyst/
│   └── skills/stata-analyst/
│       ├── SKILL.md          # Main Stata analyst skill
│       ├── phases/           # Phase agent files
│       └── techniques/       # Stata method reference guides
│
├── interview-analyst/
│   └── skills/interview-analyst/
│       ├── SKILL.md          # Main interview analyst skill
│       └── phases/           # Phase agent files
│
├── interview-writeup/
│   └── skills/interview-writeup/
│       ├── SKILL.md          # Main interview write-up skill
│       └── phases/           # Phase agent files
│
├── dag-development/
│   └── skills/dag-development/
│       ├── SKILL.md          # Main DAG development skill
│       └── phases/           # Phase agent files
│
├── abductive-analyst/
│   └── skills/abductive-analyst/
│       ├── SKILL.md          # Main abductive analyst skill
│       └── phases/           # Phase agent files (7 phases)
│
├── text-analyst/
│   └── skills/text-analyst/
│       ├── SKILL.md          # Main text analyst skill
│       ├── phases/           # Phase agent files
│       ├── concepts/         # Method concepts (language-agnostic)
│       ├── r-techniques/     # R implementation guides
│       └── python-techniques/ # Python implementation guides
│
├── lecture-designer/
│   └── skills/lecture-designer/
│       ├── SKILL.md          # Main lecture designer skill
│       ├── phases/           # Phase agent files
│       ├── pedagogy/         # Teaching methodology guides
│       ├── mcp/              # Google Docs MCP setup guides
│       └── quarto/           # Quarto reveal.js (alternative)
│
├── lit-search/
│   └── skills/lit-search/
│       ├── SKILL.md          # Main literature search skill
│       ├── phases/           # Phase agent files (7 phases)
│       └── api/              # OpenAlex API reference
│
├── lit-synthesis/
│   └── skills/lit-synthesis/
│       ├── SKILL.md          # Main literature synthesis skill
│       ├── phases/           # Phase agent files (6 phases)
│       └── mcp/              # Zotero MCP setup guide
│
├── lit-writeup/
│   └── skills/lit-writeup/
│       ├── SKILL.md          # Main literature write-up skill
│       ├── phases/           # Phase agent files (6 phases)
│       ├── clusters/         # Cluster profile guides (5 styles)
│       └── techniques/       # Writing technique guides
│
├── interview-bookends/
│   └── skills/interview-bookends/
│       ├── SKILL.md          # Main interview-bookends skill
│       ├── phases/           # Phase agent files (4 phases)
│       ├── clusters/         # Cluster profile guides (5 styles)
│       └── techniques/       # Writing technique guides
│
├── genre-skill-builder/
│   └── skills/genre-skill-builder/
│       ├── SKILL.md          # Main genre-skill-builder skill
│       ├── phases/           # Phase agent files (6 phases)
│       └── templates/        # Skill generation templates
│
├── methods-writer/
│   └── skills/methods-writer/
│       ├── SKILL.md          # Main methods-writer skill
│       ├── phases/           # Phase agent files (3 phases)
│       ├── pathways/         # Pathway profiles (Efficient/Standard/Detailed)
│       └── techniques/       # Writing technique guides
│
├── case-justification/
│   └── skills/case-justification/
│       ├── SKILL.md          # Main case-justification skill
│       ├── phases/           # Phase agent files (3 phases)
│       ├── clusters/         # Cluster profiles (5 styles)
│       └── techniques/       # Writing technique guides
│
└── revision-coordinator/
    └── skills/revision-coordinator/
        ├── SKILL.md          # Main revision-coordinator skill
        └── phases/           # Phase agent files (5 phases)
```

## Key Commands

### Running R Analysis

```bash
Rscript filename.R
which R || which Rscript
Rscript -e "sessionInfo()"
```

### Running Stata Analysis

```bash
stata -e do filename.do
# macOS: /Applications/Stata/StataMP.app/Contents/MacOS/StataMP -e do filename.do
which stata || which StataMP || which StataSE
```

### Running Python for Text Analysis

```bash
python script.py
python -c "import sklearn; print(sklearn.__version__)"
pip install gensim sentence-transformers bertopic
```

## Invoking Phase Agents

Each phase is executed by a sub-agent using the Task tool:

```
Task: Phase 1 Data Familiarization
subagent_type: general-purpose
model: sonnet  # or opus for interpretation phases
prompt: Read phases/phase1-data.md and execute for [user's project]
```

### Model Recommendations

| Phase Type | Model | Examples |
|------------|-------|----------|
| Data processing, coding | **Sonnet** | Phases 0-1 (data), Phase 2-3 (coding) |
| Design, interpretation, writing | **Opus** | Phase 0 (design), Phases 3-5 (interpretation, synthesis) |

## Development Conventions

### Adding New Plugins

1. Create `plugins/[plugin-name]/skills/[skill-name]/SKILL.md` with YAML frontmatter
2. Create `phases/` directory with phase agent files
3. Optionally create `techniques/` for reference guides
4. Add plugin entry to `.claude-plugin/marketplace.json`
5. Follow the pause-between-phases pattern

### SKILL.md Format

```yaml
---
name: skill-name
description: Brief description shown in skill listings
---

# Skill Title

[Skill content...]
```

### Phase Agent Structure

Each phase agent should include:
- **Why This Phase Matters**: Conceptual justification
- **Your Tasks**: Numbered steps with code examples
- **Output Files to Create**: Specific deliverables
- **Guiding Principles**: Key reminders
- **When You're Done**: Summary for orchestrator

### Core Principles Across All Skills

1. **Pauses are mandatory**: Never auto-proceed between phases
2. **User expertise**: The user knows their domain; we provide methodological support
3. **Show, don't tell**: Ground claims in concrete evidence
4. **Variation is data**: Differences and negative cases are analytically valuable
5. **Reproducibility**: Document decisions, use seeds, save intermediate outputs
