# AI Agent Risk Copilot (Auto LOB)

## Live Demo
Landing page: https://agent-analyzer-3.emergent.host/

## Design Preview
This repository includes UI prototype screenshots and product docs demonstrating the intended experience and decision workflow.

## Overview
AI Agent Risk Copilot is a product simulation of an internal decision-support tool designed to help underwriting and product teams understand **why** an insurance agent appears risky and **what actions to take next**.

Rather than optimizing for predictive accuracy, this product prioritizes **clarity, explainability, and business alignment**. The focus is on translating behavioral signals into insights that support coaching, monitoring, and decision review.

---

## Problem
Agent risk evaluation historically relied on loss ratio–based predictive models that were:

- Highly volatile at the agent level
- Difficult to interpret and explain
- Often misaligned with stakeholder intuition

As a result, teams spent significant time debating model outputs rather than acting on insights.

The core problem was not model performance, but **lack of clarity and shared understanding**.

---

## Product Solution
The AI Agent Risk Copilot provides a concise, explainable view of agent performance:

- **Composite Risk Score (1–10)**
- **Top Behavioral Drivers** with impact levels
- **AI-generated narrative summary**
- **Prioritized recommended actions**

The product is designed to accelerate understanding, not replace human judgment.

---

## Key Metrics (Auto Line of Business)
The Copilot focuses on behavioral and process-driven signals:

- % “No Need”
- Excluded Accident Rate
- Excluded Violation Rate
- MPD Recycle Rate
- MVR Order Rate
- CBR NA / Inconclusive Modify Rate
- **PD Frequency** (claims / earned days × 365)

Synthetic data is used for safe prototyping and demonstration.

---

## Modeling Journey & Key Insight

### Iteration 1 – Predictive Modeling
A LightGBM model was initially built using **Loss Ratio** as the target.  
While technically sound, results were unstable and often failed to match operational reality.

### Cross-Functional Insight
Discussions with actuarial, pricing, and data science stakeholders revealed that:

- Loss ratios are noisy and unreliable at low volumes
- Stakeholders were not seeking prediction
- The real goal was understanding *how* agents were performing

### Iteration 2 – Business-Aligned Scoring
The approach pivoted to policy-level linear modeling using **PD Frequency** as the target.  
Directional coefficients were converted into transparent scoring weights.

This shift significantly improved interpretability and alignment with business expectations.

---

## Use of AI
AI is used as an **explanation and communication layer**, not a prediction engine.

## AI Tools Used
- **Emergent** – rapid landing-page/prototype build for the product concept.
- **Galileo AI** – UI concept generation and layout inspiration
- **OpenAI (ChatGPT)** – drafting product copy, refining narrative, and creating constrained prompt templates.
- **GitHub Copilot** – accelerating scaffolding, formatting, and iteration (when writing supporting snippets/docs).

Website uses Copilot to:
- Converts scoring outputs into natural-language summaries
- Highlights top contributing behaviors
- Suggests operational next steps

All outputs are constrained to known metrics to ensure transparency and avoid hallucination.

---

## Product Guardrails
- Credibility thresholds to avoid penalizing low-volume agents
- Emphasis on association, not causation
- Human-in-the-loop decision review
- Transparent scoring logic for auditability

---

## Roadmap
- **v1:** Explainable agent risk scoring
- **v2:** Coaching feedback loops and trend monitoring
- **v3:** Dashboard and workflow integration

---

## Why This Project Matters
The most impactful outcome of this project was not improved model accuracy, but improved **clarity through communication and stakeholder alignment**.

This work reflects a shift from model-centric optimization to product-centric problem solving, demonstrating how AI can be used responsibly to enhance understanding and decision-making.
