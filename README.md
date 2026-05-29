# CI/CD Pipeline Automation — AutoSys JIL Deployment
## M.Tech Dissertation | BITS Pilani | 2022–2026
**Author:** Indira Tiruveedhula (2021WA86285)
**Supervisor:** Bodapati Srikanth Chowdary
**Evaluation Score:** 4–5/5 across all dimensions

---

## Project Overview
Designed and implemented a complete end-to-end CI/CD 
pipeline for automating AutoSys JIL (Job Information 
Language) file deployments across DEV, UAT, and PROD 
environments in an enterprise Finance domain.

This project eliminates manual, error-prone deployment 
processes by creating a fully automated, auditable pipeline 
from code commit to live AutoSys job execution.

---

## The Problem Solved

### Before (Manual Process):
Engineer writes JIL file manually
→ Manually validates syntax
→ Emails file to ops team
→ Ops manually deploys to AutoSys
→ No audit trail, high error risk
→ Manual promotion to UAT, PROD

### After (Automated Pipeline):
Engineer writes JIL file locally
→ git push to Bitbucket
→ Pull Request raised + peer review
→ Jenkins Build ID generated
→ JILIN auto-validates JIL syntax
→ RLM deploys to DEV automatically
→ Promotes to UAT → PROD
→ Jobs live in AutoSys WCC

---


## Tools & Technologies

| Tool | Role | Category |
|---|---|---|
| **Git** | Version control — track all JIL changes | Source Control |
| **Bitbucket** | Central repo + Pull Request workflow + Webhooks | Source Control |
| **JILIN** | Web-based JIL syntax validator | Validation |
| **Jenkins** | CI/CD automation — Build ID generation | CI/CD |
| **RLM** | Release Lifecycle Manager — controlled deployments | Release Mgmt |
| **AutoSys WCC** | Enterprise job scheduler — executes deployed JILs | Job Scheduling |

---

## JIL File Naming Convention

| Environment | File Name | AutoSys Instance |
|---|---|---|
| DEV | `File_DA.jil` | DA5 |
| UAT | `File_QA.jil` | QA5 |
| PROD | `File_PA.jil` | PA5 |

---

## ALM Process (Application Lifecycle Management)

Step 1: Create folder with DEV/UAT/PROD JIL files

Step 2: Clone Bitbucket repo locally
git clone <bitbucket-url>
Step 3: Checkout working branch
git checkout bugfix/feeds
Step 4: Copy validated JILs to Deploy/NAM folder
Step 5: Push to Bitbucket
git status
git add --all
git commit -m "Updation_JILs"
git push
Step 6: Create Pull Request in Bitbucket
bugfix/feeds → master
Step 7: Reviewer approves and merges PR
Step 8: Generate Jenkins Build ID

---

## RLM Process (Release Lifecycle Management)

Step 1: Login to RLM portal
Step 2: Create Request → Choose RLM Template
Step 3: Set environment = DEV
Set promotion environment = UAT
Step 4: Run RLM for DEV → Status: Complete
Step 5: UAT RLM auto-created (Planned)
Step 6: Run RLM for UAT → Status: Complete
Step 7: PROD RLM auto-created (Planned)
Step 8: Raise SAAS Change Ticket for PROD
Step 9: Run RLM for PROD → Status: Complete
Step 10: Verify jobs in AutoSys WCC Console

---

## Test Cases

### TC01 — Syntax Error JIL (Failure Scenario)

| Field | Detail |
|---|---|
| Test File | Error_QA.txt |
| Error Type | `update_job` on non-existent job |
| JILIN Result | VALIDATION FAILURE |
| Email Alert | Failure notification with fix suggestion |
| Fix Required | Change `update_job` to `insert_job` |

**Key Learning:** Pipeline stops immediately on JIL syntax errors — prevents bad jobs from reaching production.

---

### TC02 — Successful JIL Validation (Success Scenario)

| File | Environment | Result |
|---|---|---|
| DEV_DA.txt | DA5 | ✅ SUCCESSFUL Validation |
| UAT_QA.txt | QA5 | ✅ SUCCESSFUL Validation |
| PROD_PA.txt | PA5 | ✅ SUCCESSFUL Validation |

All three environments validated and deployed successfully through full DEV → UAT → PROD pipeline.

---

## Key Achievements

- Reduced deployment time from hours to minutes
- Full audit trail — every JIL change tracked in Git history
- Zero manual intervention from commit to production
- Automated syntax validation catches errors before deployment
- Consistent deployments across DEV, UAT, and PROD
- RLM handles approvals, rollbacks, and SAAS change tickets

---

## What I Learned

- **JIL scripting** — CMD jobs, BOX jobs, job dependencies, conditions
- **Git branching** — feature branches, bugfix branches, pull requests
- **CI/CD design** — four-stage pipeline: Commit → Build → Validate → Deploy
- **Release management** — environment promotion, change tickets, rollback
- **AutoSys operations** — job lifecycle, JILIN validation, WCC monitoring
- **Enterprise DevOps** — how large Finance organizations manage deployments

---

## Academic Details

| Field | Detail |
|---|---|
| Program | M.Tech Software Systems |
| Institution | BITS Pilani (Wipro WILP Program) |
| Student ID | 2021WA86285 |
| Supervisor | Bodapati Srikanth Chowdary |
| Duration | 16 weeks (Phase 1–4) |
| Evaluation | Mid-semester: 4–5/5 across all dimensions |
| Domain | Finance — Enterprise Batch Operations |

---

> ⚠️ **Confidentiality Note:** JIL files in this repository are 
> samples created to demonstrate concepts. Actual production 
> JIL files, server names, and client-specific configurations 
> are confidential and not included.

---

## Author
**Indira Tiruveedhula**
- 4.9 years experience in AutoSys & Production Operations
- AWS Certified Cloud Practitioner (March 2026)
- LinkedIn: linkedin.com/in/indira-tiruveedhula-b01000379
- GitHub: github.com/IndiraT02
