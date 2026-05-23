# Agentic SDLC Information Risk Pack

A synthetic second-line information security risk pack for AI-agent-led 
software delivery processes.

---

## Purpose

This project demonstrates how a second-line information security risk function 
could assess, govern and report on an AI-agent-led software development lifecycle 
(SDLC). It is not an audit project. The focus is on risk ownership, business 
impact, risk appetite, corrective action tracking and governance visibility — not 
control testing or audit evidence.

The scenario is synthetic. It does not reference, reproduce or derive from any 
client engagement, proprietary methodology or internal organisational material. 
All data, scenarios and examples are fictional and inspired by publicly available 
industry discussion on agentic AI in software delivery.

---

## Scenario

In a traditional SDLC, a human engineer interprets a change request, writes 
code, and submits it for peer review and approval before deployment. In an 
agentic SDLC, that flow changes materially: a Jira ticket triggers a development 
AI agent, which generates the change and performs internal review loops. A 
separate review AI agent then classifies the change as low risk or not low risk. 
Low-risk changes proceed to production without human review. Human involvement 
is only reintroduced where the AI agent determines it is required.

This shift changes the control boundary. The key risks are no longer only about 
developer access to production. They are about who controls the inputs, 
classification criteria, prompts, model versions and approval routes that govern 
how AI agents behave.

---

## Contents

| File | Description |
|------|-------------|
| `governance_summary_agentic_sdlc.md` | One-page second-line risk governance summary covering scenario, risk appetite, top risks, required actions and escalation triggers |

### Planned additions

| File | Description |
|------|-------------|
| `risk_register_agentic_sdlc.xlsx` | Risk register with likelihood/impact ratings, appetite position, treatment decisions and corrective action owners |
| `control_ownership_matrix.xlsx` | Control library mapped to owners, operators, frequency and current status |
| `corrective_action_tracker.xlsx` | Tracker for open issues with target dates, owners and escalation triggers |
| `risk_classifier.py` | Lightweight Python script that reads synthetic Jira ticket data and outputs risk rating, appetite position, triggered criteria and treatment decision |

---

## How a BIRA would use this

A Business Information Risk Analyst approaching an agentic SDLC environment 
would not start with the technology. They would start with the process — mapping 
where AI receives inputs, makes decisions and triggers actions — then ask whether 
those decisions are owned, governed, monitored and within risk appetite.

This pack is structured around that approach:

- **Governance summary** — frames the risk position for senior stakeholders
- **Risk register** — identifies, rates and assigns ownership to key risks
- **Control ownership matrix** — confirms who operates each control and its status
- **Corrective action tracker** — tracks what needs to change and by when
- **Risk classifier** — demonstrates how classification logic could be automated 
and made auditable

---

## Key risk positions

**Automation is not outside appetite by default.** The risk position is not that 
AI should not approve changes. It is that AI-determined deployment for 
production-impacting or business-critical changes is outside appetite without 
proportionate independent challenge, formally owned classification criteria, SoD 
enforcement and rollback monitoring.

**The threshold for human oversight is itself AI-determined.** In this process, 
whether a human reviews a change depends on whether the AI review agent classifies 
it as low risk. That makes the classification criteria, prompt governance and model 
version control first-order risk management issues, not just technical configuration.

**SoD changes shape, not relevance.** Traditional SoD separates developer from 
deployer. In an agentic SDLC, the separation must cover Jira requester, GitHub 
approver, deployment approver, prompt/model owner and exception approver. AI does 
not remove the need for SoD — it changes where the boundaries must sit.

---

## Approach to AI reasoning

Where AI classification rationale is included in this project, it is treated as 
decision-support — not audit evidence. Classification outputs are structured using 
defined criteria, source data and validation checks rather than free-form model 
reasoning.

This approach is informed by research into structured AI reasoning, including 
findings on tree-based chain-of-thought construction and the limitations of 
extended reasoning chains as reliable decision evidence:

> Yin, H. et al. (2025). *Marco-o1 v2: Towards Widening The Distillation 
> Bottleneck for Reasoning Models*. arXiv:2503.01461.

---

## Limitations

- All data is synthetic. No real organisations, clients or systems are referenced.
- The risk classifier uses rules-based logic, not a live AI model.
- This pack reflects one scenario. Risk appetite thresholds, control designs and 
escalation routes would vary by organisation, sector and regulatory context.
- Framework mappings (ISO 27001, NIST AI RMF, EU AI Act) are indicative only.

---

## Author

**Layla Bhatti** — github.com/lbhatti-risk

Background in IT audit, ITGCs, AI governance and information security risk. 
Building toward second-line risk roles in technology risk, GRC and AI governance.
