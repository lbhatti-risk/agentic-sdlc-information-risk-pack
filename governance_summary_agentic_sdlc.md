# Agentic SDLC Information Risk Governance Summary

> **Disclaimer:** This is a synthetic case study inspired by publicly available 
> industry discussion on AI-agent-led software delivery. It does not reference, 
> reproduce or derive from any client engagement, proprietary methodology or 
> internal organisational material. All data, scenarios and examples are fictional.

---

## Scenario overview

The process is triggered when a user raises a Jira ticket requesting a software 
change. A development AI agent interprets the ticket, generates the change, and 
performs internal AI-led review loops across areas such as security, compliance 
and architecture before creating a pull request in GitHub. A separate review AI 
agent then assesses the Jira ticket and code change against defined prompts and 
criteria to determine whether the change is low risk or requires manual review. 
Where the change is classified as low risk, the change proceeds to production 
without human review; where it is not low risk, it is routed to a manual review 
queue. As a result, human involvement is only reintroduced where the AI review 
agent determines the change is not low risk — meaning the threshold for human 
oversight is itself AI-determined.

---

## Risk appetite position

Residual risk should be treated as outside appetite for production-impacting or 
business-critical changes until the low-risk classification criteria, Jira ticket 
quality gate, segregation of duties checks, prompt/model governance and rollback 
monitoring are formally owned and operating. Residual risk is within appetite only 
for genuinely low-risk changes where the classification is supported by approved 
criteria, the change does not affect sensitive systems or data, and exceptions are 
visible through governance. The key position is that automation itself is not 
outside appetite; AI-determined deployment without proportionate independent 
challenge is outside appetite where business impact could be material.

---

## Top three information security risks

### 1. Low-risk misclassification

The AI review agent may classify a production-impacting, security-sensitive or 
business-critical change as low risk, allowing it to proceed to production without 
human review. This could result in unauthorised, insecure or incorrectly designed 
code being deployed into a live environment, affecting system integrity, service 
availability, financial reporting, customer outcomes or regulatory compliance.

### 2. Segregation of duties bypass

A user may raise a Jira ticket, have the development AI agent generate the change, 
and then approve the related GitHub change if access rules do not prevent 
requester/approver overlap. This creates an end-to-end path for unauthorised or 
malicious change without independent human challenge, increasing insider threat 
and change governance risk.

### 3. Prompt and model governance failure

Development or review agent prompts, guardrails, low-risk classification criteria 
or model versions may be changed without formal approval, testing, monitoring or 
rollback planning. This could cause the AI agents to behave differently from their 
approved design, meaning governance bodies can no longer rely on AI classification 
as a control and the approval mechanism itself becomes unreliable.

---

## Required actions

1. Define and approve low-risk classification criteria covering production impact, 
data sensitivity, security impact, financial reporting relevance, privileged access, 
customer impact, rollback availability and service criticality.

2. Implement a mandatory Jira ticket quality gate before the development AI agent 
is triggered, requiring clear business requirements, affected systems, change 
rationale, test expectations, data classification, security impact assessment and 
rollback plan.

3. Enforce segregation of duties between Jira requester and GitHub approver so 
that the same individual cannot request, approve or deploy the same change, 
including where the change is classified as low risk by the AI review agent.

4. Treat prompts, guardrails, model versions and classification logic as controlled 
SDLC artefacts subject to formal approval, version control, testing, rollback 
planning and post-implementation monitoring.

5. Require human review for defined high-impact change categories, including 
production-impacting changes, security-sensitive changes, privileged access changes, 
payment or financial reporting changes, and changes affecting critical business 
services.

6. Monitor rollback events and AI-approved production changes through corrective 
action tracking, with root cause review required where an AI-generated or 
AI-approved change causes rollback, incident, vulnerability finding or 
post-deployment failure.

---

## Escalation triggers

The following events should automatically route to the relevant technology risk 
or CISO governance forum:

1. **AI-approved production rollback** — Any production change that was generated, 
reviewed or approved by AI and subsequently triggers a rollback, incident, service 
degradation or material defect.

2. **Low-risk classification override event** — Any change classified as low risk 
by the AI review agent where the change affects production, payment flows, financial 
reporting, authentication, authorisation, privileged access, confidential data or 
critical business services.

3. **Segregation of duties conflict** — Any instance where the Jira requester, 
GitHub approver, deployment approver or exception approver is the same individual, 
or where independent approval cannot be evidenced.

4. **Prompt, guardrail or model version change without approval** — Any change to 
development agent prompts, review agent prompts, classification criteria, guardrails 
or model versions that has not been formally approved, tested and version-controlled.

5. **Security testing bypass or failed scan exception** — Any AI-generated or 
AI-approved change where vulnerability scanning, dependency scanning, SAST, test 
gates or required security checks are bypassed, failed or overridden without 
approved exception.

6. **Overdue corrective action on high-risk issue** — Any corrective action linked 
to a high-risk agentic SDLC issue that remains open beyond its agreed target date 
or shows repeated slippage without documented risk acceptance.

---

## References

Yin, H. et al. (2025). *Marco-o1 v2: Towards Widening The Distillation Bottleneck 
for Reasoning Models*. arXiv:2503.01461. The structured classification rationale 
approach in this project draws on this paper's findings on tree-based reasoning 
nodes and the limitations of extended chain-of-thought as reliable evidence.
