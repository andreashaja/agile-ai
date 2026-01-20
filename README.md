<p align="center">
  <img src="https://img.shields.io/badge/Framework-Agile--AI-blue?style=for-the-badge" alt="Agile-AI"/>
  <img src="https://img.shields.io/badge/Agentic-3%20Agents-green?style=for-the-badge" alt="3 Agents"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="MIT License"/>
</p>

<h1 align="center">Agile-AI</h1>
<h3 align="center">An Agentic Framework for AI-Assisted Software Development Using Scrum Principles</h3>

<p align="center">
  <i>Bringing Scrum discipline to human-AI collaboration</i>
</p>

<p align="center">
  <a href="#research-context"><strong>📄 Research Paper</strong></a> <i>(available soon)</i> ·
  <a href="INSTALLATION.md"><strong>🚀 Get Started</strong></a> ·
  <a href="agile/docs/WORKFLOW.md"><strong>📖 Documentation</strong></a>
</p>

---

## What is Agile-AI?

Agile-AI is a research framework that brings structured project management to AI-assisted software development. Rather than relying on ad-hoc conversations with AI coding assistants—an approach sometimes called "vibe coding"—this framework applies established Agile principles to create a systematic, repeatable process for building software with AI collaboration.

The core insight is simple: the challenges of AI-assisted development (requirement drift, scope creep, inconsistent quality) mirror those that Scrum methodology was designed to address in traditional software teams. By adapting Scrum's emphasis on clear roles, defined artifacts, and structured iterations, Agile-AI provides a disciplined approach that produces more reliable results than unstructured interaction.

> **This repository contains the complete, working implementation** of the framework as described in the accompanying research paper (available soon).

---

## The Three Agents

Agile-AI employs three specialized LLM agents, each responsible for a distinct phase of the software development lifecycle. This separation ensures that each phase receives appropriate attention and that constraints cannot be bypassed.

<table>
<tr>
<td width="33%" valign="top">

### Phase 1: Vision
**The Visionary Agent**

Conducts structured requirements interviews. Asks clarifying questions. Documents user intent.

**Key Constraint:** Cannot invent features or make technical decisions—only documents what users explicitly confirm.

**Produces:**
- Project Vision
- Product Backlog

</td>
<td width="33%" valign="top">

### Phase 2: Structure  
**The Architect Agent**

Plans technical implementation. Makes technology decisions. Creates execution roadmap.

**Key Constraint:** Must preserve all original user stories. Technical additions are tagged as `[TECH-ENABLER]`.

**Produces:**
- Enhanced Vision & Backlog
- Definition of Done
- Sprint Plan

</td>
<td width="33%" valign="top">

### Phase 3: Work
**The Sprinter Agent**

Implements code through iterative sprints. Tests autonomously. Delivers working software.

**Key Constraint:** Scope Guard—refuses new features during active sprints. Suggests adding them to backlog instead.

**Iterative:** This phase repeats until all sprints from the backlog are complete.

**Produces:**
- Working Code
- Sprint Reports
- Helper Scripts

</td>
</tr>
</table>

---

## Quick Start

```bash
# 1. Clone this repository
git clone https://github.com/[username]/agile-ai.git
cd agile-ai

# 2. Open in VS Code
code .

# 3. Start the workflow
#    In the OpenCode chat panel, type:
/visionary-start
```

For detailed setup instructions including VS Code, OpenCode extension, and LLM configuration, see the **[Installation Guide](INSTALLATION.md)**.

---

## How It Works

The workflow progresses through three phases, each with a start and complete command:

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│                 │     │                 │     │    ┌────────┐   │
│   VISIONARY     │────▶│   ARCHITECT     │────▶│    │ SPRINT │   │
│                 │     │                 │     │    │  1..N  │   │
│  /visionary-    │     │  /architect-    │     │    └───┬────┘   │
│     start       │     │     start       │     │        │        │
│  /visionary-    │     │  /architect-    │     │   ┌────▼────┐   │
│    complete     │     │    complete     │     │   │  Done?  │   │
│                 │     │                 │     │   └────┬────┘   │
│                 │     │                 │     │   No   │  Yes   │
│                 │     │                 │     │   ┌────┘  │     │
│                 │     │                 │     │   │       ▼     │
│                 │     │                 │     │   │   Complete  │
│                 │     │                 │     │   └──────────   │
└─────────────────┘     └─────────────────┘     └─────────────────┘
        │                       │                       │
        ▼                       ▼                       ▼
   Requirements            Technical              Working
   Documents               Planning               Software
```

The Sprinter phase is **iterative**: each sprint cycle runs `/sprinter-start` → implement → test → `/sprinter-complete`, repeating until all planned sprints are delivered.

**Phase 1** begins with `/visionary-start`. The agent asks questions about your project—what problem you're solving, who will use it, what the first version should do. Your ideas become documented requirements.

**Phase 2** begins with `/architect-start`. The agent asks technical questions—preferred language, database needs, deployment targets. It creates a technical plan and sprint breakdown.

**Phase 3** begins with `/sprinter-start`. The agent proposes a sprint scope, you agree, and it begins coding. Test the results, provide feedback, and `/sprinter-complete` commits the working code. This cycle repeats—start the next sprint, implement, test, complete—until all sprints from the backlog are delivered and your software is complete.

Throughout this process, all decisions are documented in Markdown files that persist across sessions.

---

## Repository Structure

```
agile-ai/
│
├── .opencode/agents/           # Agent definitions
│   ├── visionary/              #   Phase 1 agent + commands
│   ├── architect/              #   Phase 2 agent + commands
│   └── sprinter/               #   Phase 3 agent + commands
│
├── agile/
│   ├── artifacts/              # Generated documents (starts empty)
│   │   ├── 01_vision/          #   Phase 1 outputs
│   │   ├── 02_structure/       #   Phase 2 outputs
│   │   └── 03_work/            #   Phase 3 outputs
│   │
│   ├── templates/              # Templates & examples for each phase
│   │   ├── 01_vision/
│   │   ├── 02_structure/
│   │   └── 03_work/
│   │
│   └── docs/                   # Framework documentation
│       ├── WORKFLOW.md
│       └── ROLES.md
│
├── results/                    # Generated code goes here
│
├── README.md                   # This file
├── INSTALLATION.md             # Setup guide
└── LICENSE                     # MIT License
```

---

## Requirements

| Requirement | Purpose |
|-------------|---------|
| **VS Code** | Development environment |
| **OpenCode Extension** | AI assistant integration |
| **LLM Access** | Claude, GPT-4, or Gemini recommended |
| **Node.js 18+** | Running generated applications |
| **Git** | Version control for sprints |

> **Academic Users:** GitHub Education provides free Copilot access with multiple LLM models. Apply at [education.github.com/pack](https://education.github.com/pack).

---

## Documentation

| Document | Description |
|----------|-------------|
| **[INSTALLATION.md](INSTALLATION.md)** | Step-by-step setup instructions |
| **[WORKFLOW.md](agile/docs/WORKFLOW.md)** | Detailed three-phase process explanation |
| **[ROLES.md](agile/docs/ROLES.md)** | Agent responsibilities and constraints |

---

## Research Context

This framework was developed at the **Laboratory for Innovations in Engineering** at the University of Applied Sciences Emden/Leer, Germany. It addresses a fundamental question: as AI systems assume increasing responsibility for technical implementation, how should engineers structure their interaction with these tools?

Agile-AI proposes that engineers transition from hands-on technical executors to **project leaders** who guide and supervise AI capabilities. The framework supports this evolution by providing structured processes where users define requirements and validate results, while AI agents handle implementation details.

The framework was evaluated in a pilot study with approximately 30 Master's students, who successfully developed substantial software applications using the three-agent workflow.

> **Research Paper:** The full academic paper describing the framework's design, implementation, and evaluation results will be available here soon.

---

## Citation

If you use this framework in your research or teaching, please cite:

```bibtex
@inproceedings{haja2026agileai,
  title     = {Agile-AI: An Agentic Framework for AI-Assisted 
               Software Development Using Scrum Principles},
  author    = {Haja, Andreas},
  booktitle = {Proceedings of [Conference]},
  year      = {2026},
  organization = {IEEE}
}
```

---

## License

This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

---

<p align="center">
  <b>Prof. Dr. Andreas Haja</b><br/>
  Laboratory for Innovations in Engineering<br/>
  University of Applied Sciences Emden/Leer, Germany<br/>
  <a href="mailto:andreas.haja@hs-emden-leer.de">andreas.haja@hs-emden-leer.de</a>
</p>
