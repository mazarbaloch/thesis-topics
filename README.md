# AI-Powered Adaptive Pilot Decision-Making and Competency Training

An exploratory research and development project investigating how **generative AI, retrieval-augmented generation (RAG), simulation, and competency-based assessment** can be combined to create adaptive aviation training scenarios.

## Overview

Traditional pilot-training applications largely focus on knowledge testing, procedures, examination preparation, or predefined scenarios. Modern aviation training increasingly emphasizes **competency-based training (CBT), evidence-based training (EBT), scenario-based training, aeronautical decision-making, and threat and error management**.

At the same time, emerging AI technologies make it possible to build training environments that can understand natural-language responses, generate scenario variations, and adapt to user decisions.

This repository explores a potential next-generation platform:

> **An AI-powered adaptive training environment in which pilots enter an evolving operational situation, explain their decisions, receive competency-oriented feedback, and experience new scenario developments based on their actions.**

The project is currently a **research and concept-development initiative**. It is not an operational flight-decision system, certified flight simulator, or EASA-approved training product.

---

## The Core Idea

Instead of asking only:

> *"What is the correct answer?"*

the system asks:

> *"Given the current operational situation, what would you do, why would you do it, and what information would make you change your decision?"*

The scenario then evolves according to the pilot's response.

A simplified training loop is:

```text
Operational Situation
        ↓
Pilot Assessment
        ↓
Decision + Reasoning
        ↓
AI Interpretation
        ↓
Competency Analysis
        ↓
Scenario Evolution
        ↓
New Information / Event
        ↓
Pilot Reassessment
        ↓
Personalised Debrief
```

The goal is to train **judgement, situation awareness, decision-making, problem solving, workload management, communication, and threat management**, rather than simply memorising answers.

---

## Example Scenario

A pilot is operating an Airbus A320 approaching Frankfurt.

The system provides:

* current weather;
* TAF/METAR information;
* runway conditions;
* wind and visibility;
* fuel remaining;
* alternate airport information;
* NOTAM-related information;
* aircraft technical status;
* ATC constraints;
* traffic conditions.

The system might state:

> Frankfurt weather is deteriorating. Visibility is decreasing, crosswind is increasing, thunderstorms are approaching the arrival area, and traffic congestion is increasing.

The pilot responds in natural language:

> "I would continue toward the destination for now, but establish a clear diversion point based on fuel and weather conditions."

The platform analyses the response and identifies:

* threats recognised;
* threats omitted;
* decision quality;
* assumptions;
* contingency planning;
* communication;
* competency indicators.

The scenario then changes.

For example:

> Frankfurt reports further deterioration and the active runway becomes unavailable.

The pilot must reassess and make another decision.

This produces a **dynamic decision-making exercise rather than a static question**.

---

## Project Objectives

The project investigates how to build a system capable of:

1. Generating realistic aviation training scenarios.
2. Maintaining a structured and consistent scenario state.
3. Understanding pilot responses expressed in natural language.
4. Evaluating pilot reasoning rather than only the final answer.
5. Mapping behaviour to competency dimensions.
6. Dynamically adapting scenarios to pilot decisions.
7. Providing explainable and evidence-based feedback.
8. Personalising future training based on identified weaknesses.
9. Allowing instructors to create and control scenarios.
10. Maintaining traceability and validation for AI-generated training content.

---

## Research Focus

The project focuses particularly on the intersection of:

* Generative AI
* Large Language Models (LLMs)
* Retrieval-Augmented Generation (RAG)
* Agentic workflows
* Simulation and state management
* Human-AI interaction
* Aviation human factors
* Pilot decision-making
* Competency-Based Training
* Evidence-Based Training
* Threat and Error Management
* Explainable AI
* AI safety and validation

---

## Proposed Architecture

The envisioned platform uses a hybrid architecture rather than relying entirely on a generative AI model.

```text
┌───────────────────────────────────────┐
│            Pilot Interface            │
│     Web / Tablet / Desktop UI         │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│        Scenario State Engine           │
│ Aircraft • Weather • Fuel • Airport   │
│ ATC • Traffic • Crew • Technical      │
│ Operational Conditions                │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│       Decision / Rules Engine          │
│  Deterministic operational logic      │
│  Scenario transitions and constraints  │
└───────────────────┬───────────────────┘
                    │
                    ▼
┌───────────────────────────────────────┐
│          AI Orchestration              │
│     LLM + RAG + Tools + Agents        │
└───────────────┬───────────┬───────────┘
                │           │
                ▼           ▼
       ┌─────────────┐ ┌──────────────┐
       │ Knowledge   │ │ Competency   │
       │ Base / RAG  │ │ Model        │
       └─────────────┘ └──────────────┘
                │           │
                └─────┬─────┘
                      ▼
          ┌───────────────────────┐
          │ Assessment & Debrief  │
          │ Feedback • Analytics   │
          └───────────────────────┘
```

A central design principle is:

> **Generative AI should handle language, reasoning support and interaction, while deterministic components control critical scenario state and validation.**

This separation improves reproducibility, auditability, testing, and safety.

---

## Competency-Oriented Assessment

The system is intended to move beyond a simple right/wrong score.

Potential competency dimensions include:

| Competency                | Example indicators                                    |
| ------------------------- | ----------------------------------------------------- |
| Situation Awareness       | Identifies relevant threats and changing conditions   |
| Decision Making           | Selects and justifies an appropriate course of action |
| Problem Solving           | Considers alternatives and consequences               |
| Workload Management       | Prioritises tasks and manages competing demands       |
| Communication             | Clearly communicates intentions and priorities        |
| Application of Procedures | Correctly incorporates relevant procedures            |
| Leadership & Teamwork     | Uses crew and available resources effectively         |
| Threat & Error Management | Identifies, mitigates and reassesses threats          |

The system should provide **evidence-based observations** rather than treating an AI-generated numerical score as an authoritative assessment.

---

## Existing Work and Related Systems

This project does not assume that adaptive AI aviation scenarios are a completely unexplored area.

Several existing projects and products demonstrate important parts of the concept, including:

* **RINA – AI-powered Aviation Scenarios**
* **Resilient Pilot**
* **Boeing Virtual Airplane**
* **Scenario 737**
* **True Course**
* **PilotWorkshops Mastery**
* Other CBT/EBT and scenario-based aviation training systems

These demonstrate the feasibility of adaptive scenarios, digital pilot training, AI-supported training, and competency-oriented learning.

The research direction explored in this repository is the **integration and extension** of these ideas through a unified system combining:

> **adaptive scenarios + conversational AI + aviation RAG + structured scenario state + competency analysis + personalised learning + instructor authoring**

---

## Regulatory Considerations

The project is designed with EASA-oriented training concepts in mind, including:

* Competency-Based Training (CBT)
* Evidence-Based Training (EBT)
* Scenario-Based Training
* Aeronautical Decision Making (ADM)
* Threat and Error Management (TEM)
* Crew Resource Management (CRM)

However:

> **This repository does not represent an EASA-approved training system.**

The initial objective is to develop and evaluate a research/training prototype.

Any future use within an Approved Training Organisation (ATO), airline training programme, or regulated training device would require a separate assessment of the appropriate regulatory and approval pathway.

The platform should also maintain a strict distinction between:

**training simulation**

and

**real-world operational flight guidance**.

---

## Safety Principles

Because aviation is a safety-critical domain, the project follows several design principles.

### 1. No uncontrolled operational advice

The system is intended for training and research, not for making real-world flight decisions.

### 2. Grounded knowledge

Where factual aviation information is required, the system should rely on controlled and versioned sources rather than unrestricted model knowledge.

### 3. Deterministic scenario control

Critical scenario transitions should be governed by structured logic and validation rather than being generated entirely by an LLM.

### 4. Human oversight

Professional scenarios should be reviewable and controllable by qualified instructors or subject-matter experts.

### 5. Traceability

Training content should provide provenance and version information wherever practical.

### 6. Explainability

AI-generated assessments should explain the evidence behind observations rather than producing unexplained scores.

---

## Repository Purpose

This repository currently contains the **conceptual, research and design foundation** for the proposed platform.

The documentation is intended to support:

* research discussions;
* architecture development;
* university projects;
* industry collaboration;
* grant or project proposals;
* prototype development;
* aviation training research;
* future software implementation.

The repository may evolve from documentation into a working research prototype.

---

## Planned Development

### Phase 1 — Concept and Research

* Define requirements
* Study existing systems
* Map aviation competencies
* Design system architecture
* Identify regulatory considerations

### Phase 2 — Prototype

* Web-based pilot interface
* Scenario engine
* LLM integration
* RAG knowledge base
* Natural-language responses
* Initial competency model

### Phase 3 — Adaptive Scenarios

* Branching scenarios
* Dynamic state changes
* Decision-dependent consequences
* Scenario validation
* Difficulty adaptation

### Phase 4 — Assessment and Analytics

* Competency evidence extraction
* Structured debriefing
* Performance history
* Learner profiles
* Instructor dashboard

### Phase 5 — Instructor Platform

* Scenario authoring
* Scenario templates
* AI-assisted scenario generation
* Human review and approval
* Custom learning objectives

### Phase 6 — Evaluation

* Pilot user studies
* Expert review
* Training effectiveness studies
* AI reliability evaluation
* Scenario consistency testing
* Human-factors research

---

## Potential Research Questions

The project may investigate questions such as:

1. Can generative AI reliably interpret pilot decision-making expressed in natural language?
2. Can AI-generated scenario variations remain operationally and pedagogically consistent?
3. Can a hybrid LLM + RAG + deterministic-rules architecture improve reliability in aviation training?
4. Can AI provide useful competency-oriented feedback to pilots?
5. Can adaptive scenarios improve learning outcomes compared with static scenarios?
6. How should generative AI be constrained and validated in safety-critical training environments?
7. Can repeated scenario training improve threat recognition, situation awareness and decision-making?

---

## Project Status

**Status:** Concept / Research Development

The project is currently focused on:

* requirements;
* literature and market analysis;
* existing-system comparison;
* architecture;
* scenario design;
* AI safety;
* regulatory considerations;
* prototype planning.

The project should be considered exploratory until validated through aviation-domain expert testing.

---

## Repository Structure

A possible documentation structure is:

```text
.
├── README.md
├── proposal/
│   ├── project-proposal.md
│   ├── research-questions.md
│   └── regulatory-considerations.md
│
├── research/
│   ├── existing-solutions.md
│   ├── aviation-training.md
│   ├── cbta-ebt.md
│   ├── ai-in-aviation-training.md
│   └── literature-review.md
│
├── architecture/
│   ├── system-architecture.md
│   ├── scenario-engine.md
│   ├── ai-architecture.md
│   ├── rag-architecture.md
│   └── competency-model.md
│
├── scenarios/
│   ├── scenario-design.md
│   ├── scenario-examples.md
│   └── validation.md
│
└── future/
    ├── roadmap.md
    ├── research-agenda.md
    └── business-model.md
```

The actual repository structure may evolve as the prototype develops.

---

## Vision

The long-term vision is to create a training environment where pilots can repeatedly practise professional judgement without requiring a full-flight simulator for every training interaction.

The system should behave less like a question bank and more like an **interactive operational world**:

```text
The system presents a situation.

        ↓

The pilot interprets the situation.

        ↓

The pilot explains a decision.

        ↓

AI analyses the reasoning.

        ↓

The operational situation changes.

        ↓

The pilot reassesses.

        ↓

The system provides a competency-oriented debrief.

        ↓

Future scenarios adapt to the pilot's needs.
```

The central research challenge is therefore:

> **How can generative AI be safely and reliably used to create adaptive, explainable and competency-oriented aviation training experiences that develop pilot judgement rather than merely test pilot knowledge?**

---

## Disclaimer

This repository contains research and development material.

The software, concepts, scenarios and AI-generated content described here are **not intended to provide operational flight guidance** and must not be used as a substitute for:

* aircraft flight manuals;
* operator manuals;
* approved procedures;
* NOTAMs and official operational information;
* ATC instructions;
* applicable aviation regulations;
* certified training devices;
* qualified flight instructors;
* professional pilot judgement.

Any future deployment in regulated aviation training would require appropriate validation, expert oversight, and assessment of the applicable regulatory requirements.

---

## License

*License to be determined.*

This repository may contain references to third-party technologies, standards, research projects and aviation materials that remain subject to their respective licenses and terms of use.
