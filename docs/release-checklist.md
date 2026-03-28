# OctoAcme Release Checklist

**Owner:** Release Manager  
**Purpose:** Ensure every release is executed safely, consistently, and with clear communication to all stakeholders.

---

## Pre-Release Checklist

### 48 Hours Before Release
- [ ] Notify stakeholders and Customer Success Manager of upcoming release and expected impact
- [ ] Confirm release window with PM and Dev lead
- [ ] Validate that all planned PRs are merged or explicitly deferred
- [ ] Confirm release notes are drafted and reviewed by PdM and CSM
- [ ] Verify rollback plan is documented and rehearsed if needed

### 24 Hours Before Release
- [ ] Confirm CI/CD pipeline is green on the release branch
- [ ] Confirm all automated tests (unit, integration, e2e) are passing
- [ ] Confirm security scans have passed; no outstanding critical or high findings
- [ ] QA sign-off received on smoke tests in staging environment
- [ ] Confirm support runbooks and incident playbooks are up to date
- [ ] Notify support team of release timing and any known impacts

### 1 Hour Before Release (Code Freeze)
- [ ] Code freeze in effect — no new PRs merged to release branch
- [ ] Final smoke test run in staging completed successfully
- [ ] On-call and incident response contacts confirmed and available
- [ ] Release readiness confirmed by RM, PM, Dev lead, and QA lead (go/no-go)

---

## Release Execution Checklist

- [ ] Deploy to production environment per deployment runbook
- [ ] Monitor error rates, latency, and key metrics immediately post-deploy
- [ ] Confirm feature flags and configuration changes are applied correctly
- [ ] Verify post-deploy smoke tests pass in production
- [ ] Send release notification to stakeholders and CSM
- [ ] Publish release notes (internal and/or customer-facing as applicable)

---

## Post-Release Checklist

### Within 2 Hours of Release
- [ ] Confirm key metrics are within expected range (error rates, latency, adoption signals)
- [ ] Confirm no critical incidents have been triggered
- [ ] Confirm rollback plan is still available if needed
- [ ] Update stakeholders with initial post-release status

### Within 24 Hours of Release
- [ ] Confirm no regressions found in production
- [ ] Close or hand off any outstanding release incidents
- [ ] Archive release checklist with go/no-go sign-offs for audit trail
- [ ] Schedule post-release review meeting (PM, PdM, Dev lead, QA, RM, CSM)

---

## Rollback Criteria

Trigger rollback if any of the following occur within 2 hours of release:
- Critical error rate increase above baseline threshold
- Data integrity or security issue identified
- Core user workflow is broken and cannot be hotfixed quickly
- On-call lead and RM jointly agree rollback is necessary

---

## Release Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Release Manager | Owns checklist execution, go/no-go decision, stakeholder notifications |
| PM | Confirms release is in scope and scheduled; escalates blockers |
| Dev lead | Confirms PRs merged, CI green, deployment steps ready |
| QA lead | Signs off smoke tests in staging and production |
| Security Lead | Confirms security scans passed and no outstanding critical findings |
| CSM | Reviews release notes for customer impact; distributes customer-facing comms |
| PdM | Reviews release notes for product accuracy |
| Support | Notified ahead of release; prepared with runbooks |

---

## Example Release Timeline

| Timing | Activity |
|---|---|
| T-48h | Stakeholder notification sent; release notes drafted |
| T-24h | CI green confirmed; security scans passed; QA sign-off on staging |
| T-1h | Code freeze; final smoke test; go/no-go confirmed |
| T-0 | Deploy to production |
| T+1h | Post-deploy metrics reviewed; status sent to stakeholders |
| T+24h | Post-release review scheduled; checklist archived |
