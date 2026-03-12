# KI-EAIP — AI Enterprise Architecture & Integration Patterns

**A catalog of 10 empirically validated patterns for compliance-aware AI integration in business processes.**

---

## Overview / Überblick

This repository documents the **KI-EAIP** (AI Enterprise Architecture and Integration Patterns) catalog, developed and empirically validated by Syngenio AG. The catalog provides concrete, actionable patterns for organisations introducing AI into regulated business processes, where compliance, auditability, and controlled error propagation are critical requirements.

Each pattern is an AI-specific adaptation of established software, enterprise architecture, or business process management patterns — grounded in empirical validation across three real-world case studies.

---

## Case Studies / Anwendungsfälle

| ID | Name | Domain | Patterns Applied |
|---|---|---|---|
| **KIMONA** | Complaints processing | Insurance / document processing | 01, 02, 03, 06 |
| **IEdit** | Compliance-conform application flow generation | Banking / financial products | 05, 06, 10 |
| **ISA** | Internal support assistant with AI compliance monitoring | IT services / knowledge management | 04, 08, 09 |

---

## The 10 Patterns

### Purpose & Structure

| # | Pattern | Core Idea |
|---|---|---|
| 01 | [Separation of Level](patterns/01_separation-of-level.md) | Each AI step handles exactly one level transition in the data→knowledge hierarchy |
| 02 | [Separation of Concern](patterns/02_separation-of-concern.md) | One dedicated AI system per organisational/functional unit; controlled handoffs |
| 03 | [Split Chatbot](patterns/03_split-chatbot.md) | Frontend AI (external-facing) + Backend AI (internal/restricted data) — strictly separated |

### Data Quality & Access

| # | Pattern | Core Idea |
|---|---|---|
| 04 | [Semantic Access](patterns/04_semantic-access.md) | Route AI to semantically consistent data sources only; block terminologically ambiguous sources |
| 05 | [Fixed Interfaces](patterns/05_fixed-interfaces.md) | AI populates within a predefined template; non-AI validator enforces structural/compliance rules |

### Control & Oversight

| # | Pattern | Core Idea |
|---|---|---|
| 06 | [Human in the Loop](patterns/06_human-in-the-loop.md) | Human reviews and approves AI output before it proceeds — the four-eyes principle applied to AI |
| 07 | [AI in the Loop](patterns/07_ai-in-the-loop.md) | AI reviews and provides feedback on human output — leveraging AI's rule-processing capacity |
| 08 | [Validate / Detect](patterns/08_validate-detect.md) | Downstream system (classical or AI) checks AI output; errors flagged for correction |
| 09 | [Detect / Correct](patterns/09_detect-correct.md) | Extends 08: high-plausibility corrections applied automatically; low-plausibility escalated to human |

### Agentic AI

| # | Pattern | Core Idea |
|---|---|---|
| 10 | [Agentic Subworkflow Structures](patterns/10_agentic-subworkflow.md) | Bound agent scope as a sub-workflow; prefer Bottom-Up composition; linear structures are more practical than tree structures |

---

## Key Cross-Cutting Findings

1. **Full reliability without human oversight was not achieved** in any case study. Either compliance risks must be accepted, or human control remains necessary.
2. **AI as colleague, not tool**: The same risk management practices that apply to human actors in regulated BPs apply to AI actors. The four-eyes principle is the clearest example.
3. **Self-validation is unreliable**: An AI checking its own output tends to reproduce its original errors — even with different prompts and explicit instructions for critical re-assessment.
4. **Bottom-Up beats Top-Down** for agentic AI: Starting from the smallest reliable steps produces more reliable results than planning from the top down.
5. **Linear structures are more practical** than tree structures in most agentic AI cases, because specifications are typically available at the element level — not as abstract multi-level hierarchies.
6. **AI + human collaboration outperforms either alone**: All case studies confirmed that the combination produced better results — both quantitatively and qualitatively.

---

## Repository Structure

```
ki-eaip-katalog/
├── README.md
├── LICENSE
├── patterns/
│   ├── 01_separation-of-level.md
│   ├── 02_separation-of-concern.md
│   ├── 03_split-chatbot.md
│   ├── 04_semantic-access.md
│   ├── 05_fixed-interfaces.md
│   ├── 06_human-in-the-loop.md
│   ├── 07_ai-in-the-loop.md
│   ├── 08_validate-detect.md
│   ├── 09_detect-correct.md
│   └── 10_agentic-subworkflow.md
└── assets/
    └── diagrams/
        ├── 01_separation-of-level.svg  …  10_agentic-subworkflow.svg
```

---

## Background and Motivation

The KI-EAIP catalog results from a research and application project by Syngenio AG. Starting from an analysis of **97 existing software, enterprise architecture, and BPM patterns**, 10 AI-specific patterns were derived and validated across three real-world case studies. Only patterns whose effectiveness was empirically confirmed were included.

### Positioning: A gap in the existing pattern landscape

The catalog addresses a gap that currently exists in the published pattern literature. Two types of AI pattern collections are well established:

- **Technical AI patterns** (e.g. Andrew Ng's four agentic design patterns — Reflection, Tool Use, Planning, Multi-Agent Collaboration; or Anthropic's workflow patterns — Prompt Chaining, Routing, Parallelization, Orchestrator-Workers, Evaluator-Optimizer): These are formulated at the level of LLM calls and system architecture. They describe *how* an AI system works internally, but do not address the integration of AI into business processes, organisational accountability, or compliance requirements.

- **AI governance frameworks** (e.g. EU AI Act, NIST AI RMF, ISO/IEC 42001): These operate at the regulatory and organisational policy level. They define what is required, but do not provide concrete, actionable patterns at the level of individual process steps.

The KI-EAIP patterns occupy the space between these two: they are formulated at the **business process level**, addressing questions such as: At which process step should a human review AI output? How should data access be structured to meet compliance requirements? How should an agentic AI be scoped within a workflow to remain auditable? These are questions that cannot be answered by technical LLM patterns alone, nor by high-level governance frameworks alone.

To the best of our knowledge, no comparable empirically validated pattern catalog at this level of abstraction currently exists.

---

## License

MIT — see [LICENSE](LICENSE)

---
---

# KI-EAIP — KI Enterprise Architecture & Integration Pattern

**Ein Katalog von 10 empirisch validierten Pattern für compliance-konforme KI-Integration in Geschäftsprozesse.**

---

## Überblick

Dieses Repository dokumentiert den **KI-EAIP**-Katalog, entwickelt und empirisch validiert von der Syngenio AG. Der Katalog liefert konkrete, handlungsrelevante Pattern für Organisationen, die KI in regulierte Geschäftsprozesse einführen.

---

## Anwendungsfälle

| ID | Name | Domäne | Eingesetzte Pattern |
|---|---|---|---|
| **KIMONA** | Reklamationsbearbeitung | Versicherung | 01, 02, 03, 06 |
| **IEdit** | Compliance-konforme Antragsstrecken | Banking | 05, 06, 10 |
| **ISA** | Support-Assistent mit KI-Compliance-Überwachung | IT-Services | 04, 08, 09 |

---

## Die 10 Pattern

| # | Pattern | Kerngedanke |
|---|---|---|
| 01 | [Separation of Level](patterns/01_separation-of-level.md) | Jeder KI-Schritt bearbeitet genau eine Level-Transition |
| 02 | [Separation of Concern](patterns/02_separation-of-concern.md) | Ein dediziertes KI-System pro organisatorischer Einheit |
| 03 | [Split Chatbot](patterns/03_split-chatbot.md) | Frontend-KI (extern) + Backend-KI (intern) strikt getrennt |
| 04 | [Semantic Access](patterns/04_semantic-access.md) | Nur semantisch konsistente Datenquellen zulassen |
| 05 | [Fixed Interfaces](patterns/05_fixed-interfaces.md) | KI befüllt Template; Nicht-KI-Validator erzwingt Compliance-Regeln |
| 06 | [Human in the Loop](patterns/06_human-in-the-loop.md) | Mensch prüft KI-Output — Vier-Augen-Prinzip |
| 07 | [AI in the Loop](patterns/07_ai-in-the-loop.md) | KI prüft menschlichen Output |
| 08 | [Validate / Detect](patterns/08_validate-detect.md) | Nachgelagertes System erkennt Fehler im KI-Output |
| 09 | [Detect / Correct](patterns/09_detect-correct.md) | Erkennung + automatische oder menschlich eskalierte Korrektur |
| 10 | [Agentic Subworkflow Structures](patterns/10_agentic-subworkflow.md) | Agent-Scope abgrenzen; Bottom-Up; lineare Strukturen bevorzugen |

---

## Hintergrund und Motivation

Der KI-EAIP-Katalog entstammt einem Forschungs- und Anwendungsprojekt der Syngenio AG. Ausgehend von einer Analyse von **97 bestehenden Software-, Enterprise-Architecture- und BPM-Pattern** wurden 10 KI-spezifische Pattern abgeleitet und in drei realen Fallstudien validiert. In den Katalog wurden ausschließlich Pattern aufgenommen, deren Wirksamkeit empirisch bestätigt wurde.

### Einordnung: Eine Lücke in der bestehenden Pattern-Landschaft

Der Katalog adressiert eine Lücke, die in der publizierten Pattern-Literatur derzeit besteht. Zwei Typen von KI-Pattern-Sammlungen sind etabliert:

- **Technische KI-Pattern** (z. B. Andrew Ngs vier Agentic Design Patterns — Reflection, Tool Use, Planning, Multi-Agent Collaboration; oder Anthropics Workflow-Pattern — Prompt Chaining, Routing, Parallelization, Orchestrator-Workers, Evaluator-Optimizer): Diese sind auf der Ebene von LLM-Aufrufen und Systemarchitektur formuliert. Sie beschreiben, *wie* ein KI-System intern funktioniert, adressieren jedoch nicht die Einbettung von KI in Geschäftsprozesse, organisatorische Verantwortlichkeiten oder Compliance-Anforderungen.

- **KI-Governance-Frameworks** (z. B. EU AI Act, NIST AI RMF, ISO/IEC 42001): Diese operieren auf der Ebene von Regulierung und Organisationspolitik. Sie definieren, *was* gefordert ist, liefern aber keine konkreten, handlungsrelevanten Pattern auf der Ebene einzelner Prozessschritte.

Die KI-EAIP-Pattern besetzen den Raum zwischen diesen beiden Ebenen: Sie sind auf der **Geschäftsprozessebene** formuliert und beantworten Fragen wie: An welchem Prozessschritt soll ein Mensch den KI-Output prüfen? Wie ist der Datenzugriff zu strukturieren, um Compliance-Anforderungen zu erfüllen? Wie ist eine agentische KI innerhalb eines Workflows abzugrenzen, damit sie auditierbar bleibt? Diese Fragen lassen sich weder durch technische LLM-Pattern allein noch durch übergeordnete Governance-Frameworks allein beantworten.

Nach aktuellem Kenntnisstand existiert kein vergleichbarer empirisch validierter Pattern-Katalog auf dieser Abstraktionsebene.

---

## Lizenz

MIT — siehe [LICENSE](LICENSE)
