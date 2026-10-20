# 🚀 VibeCraft — Vibe Coding Club Assignment

> **Complete submission for the Vibe Coding Club task:**
> Building one complete working project using the 8-Markdown Spec-Driven Vibe Coding methodology.

![Vibe Coding Status](https://img.shields.io/badge/Deliverables-8%20of%208%20Markdown%20Files-emerald)
![Test Status](https://img.shields.io/badge/Tests-8%2F8%20Passing-emerald)
![Methodology](https://img.shields.io/badge/Method-Spec--Driven%20Vibe%20Coding-blue)
![Built for](https://img.shields.io/badge/Club-Vibe%20Coding%20Club-amber)

---

## 📌 Deliverables Overview

This repository fulfills all requirements announced in the Vibe Coding Club session:

1. ✅ **All 8 Markdown (.md) files** authored following the workflow discussed in the session:
   - [`docs/01_OVERVIEW.md`](docs/01_OVERVIEW.md): Executive summary, vision, problem statement, KPIs, and scope boundaries.
   - [`docs/02_FEATURES.md`](docs/02_FEATURES.md): Personas (1st/2nd sem member, mentor, lead), P0/P1/P2 priority matrix, Gherkin acceptance criteria.
   - [`docs/03_ARCHITECTURE.md`](docs/03_ARCHITECTURE.md): Tech stack, ASCII system diagram, component hierarchy, and data contracts.
   - [`docs/04_DESIGN.md`](docs/04_DESIGN.md): UI/UX Design System, color tokens, typography scale, zero-pill discipline, WCAG AA compliance.
   - [`docs/05_USER_FLOW.md`](docs/05_USER_FLOW.md): End-to-end user journeys, Finite State Machine transitions, and error recovery trees.
   - [`docs/06_ROADMAP.md`](docs/06_ROADMAP.md): Sprints 1 through 4 milestones, technical debt strategy, and Definition of Done.
   - [`docs/07_BUSINESS_MODEL.md`](docs/07_BUSINESS_MODEL.md): Unit economics, token cost reduction analysis (75%+ savings), sustainability.
   - [`docs/08_TESTING_PLAN.md`](docs/08_TESTING_PLAN.md): Testing matrix, 8 automated test suites, quality gates, and regression protocols.

2. ✅ **A working project built using that method**:
   - **VibeCraft**: An interactive, production-grade Vibe Coding Workbench with:
     - 📁 **8-Markdown Documentation Hub**: Live syntax viewer, search, raw/formatted toggle, and one-click ZIP exporter.
     - 🧪 **Interactive Architecture Topology**: Live canvas verifying components, dependencies, and health pings.
     - 🔄 **User Flow State Machine Simulator**: Step-through simulation of the vibe coding lifecycle with branching decisions.
     - 🎨 **Design System Inspector**: Live WCAG AA contrast analysis, typography scales, and zero-pill validator.
     - 📊 **Unit Economics & Token Calculator**: Real-time prompt overhead & cost-to-serve estimator.
     - 🚦 **Automated Test Runner**: Executes all 8 verification suites in-browser with pass/fail telemetry.
     - 🛠️ **GitHub Submission Suite**: Dynamic Git shell commands, checklist validator, and repo tester.

3. ✅ **GitHub Repository Link with Project Uploaded**:
   - Ready for pushing directly with the provided CLI scripts in `src/components/GitHubHandOff/`.

---

## 🛠️ Quick Start

```bash
# Clone the repository
git clone https://github.com/shaheer51-1/vibe-coding-club-project.git

# Navigate to project
cd vibe-coding-club-project

# Install dependencies
npm install

# Start the dev server
npm run dev

# Build for production
npm run build
```

---

## 📂 Project Structure

```
├── docs/                       # The 8 canonical Markdown deliverables
│   ├── 01_OVERVIEW.md
│   ├── 02_FEATURES.md
│   ├── 03_ARCHITECTURE.md
│   ├── 04_DESIGN.md
│   ├── 05_USER_FLOW.md
│   ├── 06_ROADMAP.md
│   ├── 07_BUSINESS_MODEL.md
│   └── 08_TESTING_PLAN.md
├── src/
│   ├── components/             # Modular React 19 components
│   │   ├── Header.tsx          # Clean typography-first app header
│   │   ├── SpecHub/            # 8-doc reader, search & zip exporter
│   │   ├── Workbench/          # Live interactive engineering modules
│   │   ├── GitHubHandOff/      # Git CLI generator & deliverable check
│   │   └── ClubGuide/          # Vibe Coding method explanation
│   ├── data/
│   │   └── defaultSpecs.ts     # Embedded source for the 8 markdown docs
│   ├── utils/
│   │   ├── zipExport.ts        # JSZip bundle exporter
│   │   └── testEngine.ts       # In-browser test runner
│   ├── App.tsx                 # Core application controller
│   └── main.tsx                # Entry point
├── package.json
└── README.md
```

---

## 💡 What is the Vibe Coding 8-Markdown Methodology?

As Andrej Karpathy articulated, "vibe coding" allows developers to guide AI models through natural language. However, without persistent context, models suffer from hallucination and cascade fatigue.

The 8-Markdown methodology introduces a **lightweight specification harness**:
1. You define the 8 documents sequentially to anchor the AI's memory.
2. The AI uses these files as continuous context prompts.
3. Code is produced with rigorous quality gates and zero architectural drift.
