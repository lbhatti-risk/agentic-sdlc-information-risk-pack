# Agentic SDLC Information Risk Pack

A synthetic second-line information security risk pack for AI-agent-led software delivery processes.

This repository explores how a Business Information Risk Analyst, Technology Risk Manager, or CISO-aligned risk function could assess an SDLC process where AI agents generate, review, classify, and route software changes with reduced human involvement.

The project is intentionally framed from a **second-line information security risk perspective**, not as an audit workpaper. The focus is on business impact, risk appetite, control ownership, corrective actions, and governance visibility.

---

## Purpose

AI-enabled SDLC processes are moving from simple developer assistance toward agentic workflows where AI may:

- interpret Jira tickets;
- generate code changes;
- perform security, compliance, or architecture review loops;
- create or support pull requests in GitHub;
- classify changes as low, medium, or high risk;
- route low-risk changes toward deployment with limited human review.

This changes the risk profile of the SDLC. Traditional human control points may be reduced, moved, or replaced, and new risk points emerge around Jira ticket quality, AI classification criteria, segregation of duties, prompt governance, model version updates, rollback monitoring, and governance reporting.

This repository demonstrates how those risks could be captured in a practical information risk pack.

---

## Disclaimer

This is a synthetic case study inspired by publicly available industry discussion on AI-agent-led software delivery and emerging AI governance themes.

It does **not** reference, reproduce, or derive from any client engagement, proprietary methodology, confidential documentation, internal organisational material, or real control environment.

All scenarios, risks, owners, control descriptions, and examples are fictional.

---

## Repository contents

| Artefact | Purpose |
|---|---|
| `governance_summary_agentic_sdlc.md` | One-page governance summary for senior stakeholders |
| `risk_register_agentic_sdlc.xlsx` | Information security risk register for the agentic SDLC scenario |
| `control_ownership_matrix.xlsx` | Control ownership and status matrix |
| `corrective_action_tracker.xlsx` | Corrective action tracker with owners, due dates, and escalation triggers |
| `synthetic_jira_tickets.csv` | Fictional Jira-style tickets used to illustrate risk classification |
| `risk_classifier.py` | Optional lightweight script to classify synthetic changes against simple risk criteria |

Version 1 focuses on the governance summary. Further artefacts may be added iteratively.

---

## Scenario

The process is triggered when a user raises a Jira ticket requesting a software change. A development AI agent interprets the ticket, generates the change, and performs internal AI-led review loops across areas such as security, compliance, and architecture before creating a pull request in GitHub.

A separate review AI agent then assesses the Jira ticket and code change against defined prompts and criteria to determine whether the change is low risk or requires manual review. Where the change is classified as low risk, the change proceeds to production without human review; where it is not low risk, it is routed to a manual review queue.

As a result, human involvement is only reintroduced where the AI review agent determines the change is not low risk — meaning the threshold for human oversight is itself AI-determined.

---

## Core risk judgement

The central risk judgement is:

> Automation itself is not outside appetite. AI-determined deployment without proportionate independent challenge is outside appetite where business impact could be material.

This distinction matters. The purpose of this risk pack is not to block AI-enabled SDLC automation, but to define where risk ownership, human review, escalation, and corrective action are required.

---

## Top information security risks

### 1. Low-risk misclassification

The AI review agent may classify a production-impacting, security-sensitive, or business-critical change as low risk, allowing it to proceed to production without human review.

This could result in unauthorised, insecure, or incorrectly designed code being deployed into a live environment, affecting system integrity, service availability, financial reporting, customer outcomes, or regulatory compliance.

### 2. Segregation of duties bypass

A user may raise a Jira ticket, have the development AI agent generate the change, and then approve the related GitHub change if access rules do not prevent requester/approver overlap.

This creates an end-to-end path for unauthorised or malicious change without independent human challenge, increasing insider threat and change governance risk.

### 3. Prompt and model governance failure

Development or review agent prompts, guardrails, low-risk classification criteria, or model versions may be changed without formal approval, testing, monitoring, or rollback planning.

This could cause the AI agents to behave differently from their approved design, meaning governance bodies can no longer rely on AI classification as a control and the approval mechanism itself becomes unreliable.

---

## Key second-line questions

This project is built around the following risk questions:

- What business process is the AI influencing or executing?
- What inputs does the AI rely on?
- What decisions does the AI make?
- What actions can the AI trigger?
- Who owns the risk if the AI makes a poor decision?
- What is the business impact if the AI classification is wrong?
- Is the residual risk within appetite?
- Which controls are preventive, detective, or corrective?
- Which risks require governance escalation?
- How are corrective actions tracked to completion?

---

## Required control themes

The risk pack focuses on six control themes:

### 1. Low-risk classification criteria

Clear, approved criteria for determining whether a change is genuinely low risk.

### 2. Jira ticket quality gate

Mandatory minimum information before AI development can begin.

### 3. Segregation of duties

Separation between requester, approver, deployer, exception approver, and owners of classification logic.

### 4. Prompt and model governance

Formal change control over prompts, guardrails, model versions, and classification criteria.

### 5. Human review floor

Mandatory human review for defined high-impact change categories, regardless of AI classification.

### 6. Rollback and corrective action monitoring

Root cause review and corrective action tracking where AI-generated or AI-approved changes fail.

---

## Structured classification rationale

This project uses the concept of a **structured classification rationale** rather than free-form AI reasoning.

In practice, this means a risk classification should be supported by defined criteria, source fields, and decision outputs, for example:

```json
{
  "ticket_id": "JIRA-1042",
  "risk_rating": "High",
  "risk_appetite_position": "Outside appetite",
  "criteria_triggered": [
    "Production-impacting change",
    "Payments-related system",
    "Requester and approver are the same individual"
  ],
  "treatment_decision": "Reduce",
  "recommended_action": "Require independent human approval before deployment"
}
```

The purpose is to make the classification:

- evidence-backed;
- consistent;
- challengeable;
- governance-ready;
- easier to validate than a long narrative explanation.

AI-generated reasoning should not be treated as sufficient evidence on its own. It should be treated as a decision-support artefact that must be supported by approved criteria, source data, ownership, monitoring, and escalation.

---

## Research inspiration

The structured rationale approach is partly informed by:

**Yin, H. et al. (2025). _Marco-o1 v2: Towards Widening The Distillation Bottleneck for Reasoning Models_. arXiv:2503.01461.**  
https://arxiv.org/abs/2503.01461

The paper discusses tree-based chain-of-thought construction and the limitations of long reasoning chains, including risks of over-thinking and unreliable rationale.

This project applies that lesson in a governance context by avoiding reliance on long free-form AI explanations and instead using structured criteria, decision nodes, and validation checks.

This repository does not implement Marco-o1 v2 or reproduce the paper’s methodology. It only draws on the broader governance implication: reasoning outputs should be structured, bounded, and independently challengeable where they support risk decisions.

---

## How this maps to a BIRA-style role

A Business Information Risk Analyst is not only concerned with whether a control exists. The role requires understanding:

- what the risk is;
- who owns it;
- whether it is within appetite;
- what corrective action is required;
- whether senior stakeholders need visibility;
- whether the risk posture is improving or deteriorating.

This repository is designed to demonstrate that mindset using an emerging technology scenario.

The focus is therefore not on writing production-grade code. The focus is on translating a complex AI-enabled SDLC process into a clear risk management view that a CISO, Technology Risk Manager, or governance forum could act on.

---

## Current status

Version 1 includes:

- governance summary;
- top risks;
- risk appetite position;
- required actions;
- escalation triggers;
- structured rationale approach.

Planned future additions:

- risk register;
- control ownership matrix;
- corrective action tracker;
- synthetic Jira ticket examples;
- lightweight risk classification script.

---

## Limitations

This is a conceptual and educational project.

It does not connect to Jira, GitHub, GitHub Copilot, CI/CD tooling, LLM APIs, or production systems. It does not assess real code, real tickets, or real organisational controls.

The examples are simplified to demonstrate second-line risk thinking and should not be treated as a complete control framework for AI-led SDLC.

---

## Author

Layla Bhatti  
Digital Audit Associate | Technology Controls | Information Security Risk | AI Governance  
GitHub: https://github.com/lbhatti-risk
