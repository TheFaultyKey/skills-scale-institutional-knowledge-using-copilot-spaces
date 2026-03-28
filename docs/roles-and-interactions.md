# OctoAcme Roles and Interactions

This document describes how roles collaborate across common activities, provides a RACI-like mapping, and outlines recommended communication touchpoints. Use this alongside `octoacme-roles-and-personas.md` for a full picture of responsibilities.

---

## Role Abbreviations

| Abbreviation | Role |
|---|---|
| PM | Project Manager |
| PdM | Product Manager |
| Dev | Developers |
| QA | QA/Testing |
| UX | UX Designer |
| RM | Release Manager |
| SL | Security Lead |
| CSM | Customer Success Manager |
| SH | Stakeholders |

---

## RACI Matrix

**Key:** R = Responsible, A = Accountable, C = Consulted, I = Informed

| Activity | PM | PdM | Dev | QA | UX | RM | SL | CSM | SH |
|---|---|---|---|---|---|---|---|---|---|
| Feature definition | C | A/R | C | C | C | I | C | C | C |
| Design | C | C | C | C | A/R | I | C | I | I |
| Implementation | C | I | A/R | C | C | I | C | I | I |
| QA/Testing | C | I | R | A/R | C | C | C | I | I |
| Security review | C | C | R | C | I | I | A/R | I | I |
| Release | R | I | R | R | I | A/R | C | C | I |
| Post-release support | C | C | C | I | I | C | C | A/R | I |

---

## Common Handoff Examples

### Feature design → Implementation → Release → Post-release support

1. **Feature definition:** PdM defines problem statement, success metrics, and acceptance criteria. PM sets timeline and dependencies. UX contributes user research and constraints. SL advises on security requirements.

2. **Design:** UX produces wireframes and specs. Developers and QA review for feasibility and testability. PdM validates against product goals. Design handoff documented in PR or shared design tool.

3. **Implementation:** Developers implement against specs and acceptance criteria. UX available for design review questions. SL reviews PRs for security issues. QA prepares test cases in parallel.

4. **QA/Testing:** QA validates implementation against acceptance criteria. UX may assist with usability acceptance tests. SL validates security test coverage. Findings logged and resolved before release sign-off.

5. **Security review:** SL runs or reviews security scans, threat models, and vulnerability assessments. Findings triaged with PdM and PM for remediation before release.

6. **Release:** RM confirms release readiness (all PRs merged, CI green, smoke tests passed). RM sends pre-release notification to CSM and stakeholders. PM confirms scheduling alignment. RM coordinates deployment and monitors for issues.

7. **Post-release support:** CSM monitors adoption metrics and customer feedback. Support flags recurring issues to CSM. CSM and PdM triage against backlog. PM schedules follow-up fixes if needed.

---

## Recommended Communication Touchpoints

### Project Kickoff
- **Attend:** PM, PdM, Dev lead, QA lead, UX, SL, RM, SH
- **Owner:** PM facilitates
- **Outcome:** Agreed scope, timeline, key risks, and RACI alignment

### Sprint/Iteration Planning
- **Attend:** PM, PdM, Developers, QA, UX
- **Owner:** PM or PdM facilitates
- **Outcome:** Committed backlog with clear acceptance criteria and design assets ready

### Design Review
- **Attend:** UX, Developers, QA, PdM
- **Owner:** UX facilitates
- **Outcome:** Implementation-ready specs, open questions resolved

### Release Readiness Review
- **Attend:** RM, PM, Dev lead, QA lead, SL
- **Owner:** RM facilitates
- **Outcome:** Go/no-go decision, rollback plan confirmed, notifications prepared

### Release Notes
- **Owner:** RM drafts; PdM reviews; CSM reviews for customer-facing impact
- **Distribution:** CSM, SH, Support

### Blocker Escalation
- **Notify:** PM (primary), PdM (if scope/priority impacted), SL (if security-related), SH (if milestone at risk)
- **Owner:** Whoever identifies the blocker raises to PM immediately

### Post-Release Review
- **Attend:** PM, PdM, Dev lead, QA lead, RM, CSM
- **Owner:** PM facilitates
- **Outcome:** Adoption metrics reviewed, incidents captured, retrospective actions logged
