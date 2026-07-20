# slopaudit.org, site prose (editable source)

Edit the prose here; tell me when you're done and I'll sync it back into `public/index.html`. Section headings below match the page sections. Links are shown as `[text](url)`. Bold shows the emphasis used on the page.

---

## Meta

- **Page title:** Slop Audit: an open standard for measuring software quality
- **Meta description:** Code coverage cannot prove every permutation was tested. The Slop Audit is an open standard that measures whether a codebase is structurally capable of exhaustive behavioural verification, essential for any organization that must attest to software correctness: banks, insurers, pharma, regulated industries. Stewarded by the Open Honest Foundation.
- **Nav labels:** Coverage · Four layers · Dimensions · Frameworks · Research

---

## Hero

**H1:** The Slop Audit

**Tagline:** Code coverage cannot prove every case was tested.

**Lead:**
If your organization has to **attest to the correctness of its software**, regulated industries, banks, insurers, pharmaceutical and medical-device manufacturers, public infrastructure, you are almost certainly leaning on a number that does not mean what you were told it means: test coverage. The Slop Audit is an open standard that measures what coverage cannot, whether a codebase is even structurally capable of having every behaviour verified. It is stewarded by the [Open Honest Foundation](https://openhonest.org), released under Apache-2.0, and is the common name for the standard formally designated the **Honest Audit**.

---

## Coverage is not proof of correctness

The conventional standard for software testing is line coverage, or coverage for short. Coverage tells you how many lines of your code was executed by tests. 

Importantly, it does not tell you how much of your software’s actual behavior was properly verified. You can hit 95% coverage and still leave the vast majority of real-world scenarios—the ones regulators and auditors care about—completely untested.

Whether true verification is even possible depends on the structure of the code itself. The way most code is written leaves the door open for many different combinations of steps and logic, each one of these is a “state permutation”. When code has lots of state permutation, the number of possible behaviors explodes far beyond what any test suite can cover. More tests don’t solve this.

Our analysis of 200 public codebases found that roughly 99% of typical enterprise systems (outside of React front-ends) **are structurally incapable of being fully verified through testing** because of this state explosion. The Slop Audit measures this risk directly through objective mathematical calculations which gives you real evidence of correctness instead of misleading coverage percentages.

---

## You cannot eyeball quality

We all know what AI Slop is. The word gets used to describe a general impression: code that looks AI-generated, rushed, or low-quality. However, a polished codebase can hide serious defects, and rough-looking code can be as solid as can be. The Slop Audit replaces a general impression with a measurement, an evidence-based, reproducible score against named indicators and compliance thresholds, created from hard data. Only the actual structure decides.

The audit scores any codebase against the published thresholds of named compliance frameworks across 18 dimensions covering security architecture, data architecture, compliance engineering, operational security, performance engineering, operations, DevOps, infrastructure, software architecture, governance, process engineering, lifecycle management, and software development.

It applies to any codebase, in any language, regardless of architectural style. Each indicator is calibrated against the compliance-framework thresholds it maps to.

---

## The four-layer model

The Slop Audit is not a single methodology. It is four nested methodologies that compose, each operating at a different cognitive level and each producing a different kind of evidence. The boundary between Layer 3 and Layer 4 is the load-bearing decision of the entire standard: Phase 0 runs Layers 1, 2, and 3, which trained assessors can reproduce; Phase 1 adds Layer 4, the elite architectural judgment that transfers only by apprenticeship.

| Layer | Name | Judgment | Phase |
|---|---|---|---|
| 1 | Quantitative git-history assessment | Mechanical, no judgment | Phase 0 |
| 2 | Quantitative artifact assessment | Mechanical, no judgment | Phase 0 |
| 3 | Qualitative specified judgment | Trainable, specified markers | Phase 0 |
| 4 | Architectural synthesis | Elite, by apprenticeship | Phase 1 |

**Layer 1: git-history assessment.**
A *mechanical* analysis of the codebase git history and static artifacts that produces 20 numerical indicators: mutable-state ratio, decision-space coverage, test determinism, delete/add ratio, secrets scan, type-escape density, fuzzy duplication, “god-file” concentration, and 12 others. Inputs are a git repository and a date range. The same indicators applied to the same repository by two different assessors produce identical numbers. Numbers that come from running git commands are harder to dispute than numbers that come from architectural judgment.

**Layer 2: artifact assessment.**
A mechanical inspection of structural artifacts (configuration, dependency declarations, file structures, the presence or absence of specific kinds of files) for each of the 18 dimensions, scored Present, Partial, Absent, or Not Applicable, with file paths and line numbers cited as evidence. Every finding can be reproduced by any other trained assessor in minutes. The audit software is not asked to trust judgment; it looks at the codebase's own files and confirms what is or is not there.

**Layer 3: specified judgment.**
A structured exercise of qualitative judgment applied through specified markers, on aspects of each dimension that cannot be reduced to artifact inspection. Each dimension defines between three and five markers, each scored against defined criteria, with a stated inter-rater-reliability target. The judgment is real, but the criteria are explicit enough that trained assessors produce consistent scores. This is what lets Phase 0 answer the meaningful question on dimensions like pattern sophistication and architectural philosophy without requiring elite experience.

**Layer 4: architectural synthesis.**
The judgment that cannot be reduced to specified markers: whether an architecture is the right one for the domain, whether hidden couplings will surface under operational stress, whether patterns are used correctly in the deepest sense. This requires years of building, shipping, and maintaining systems at scale, and it does not transfer through documentation. During a Phase 0 audit, Layer 4 issues are recorded as flagged for Phase 1 follow-up; they are not scored and do not influence the Layer 2 and Layer 3 dimension scores.

A Phase 0 audit of a mid-size codebase (50,000 to 250,000 lines) runs in about five days and produces a Slop Report: the Layer 1 panel, the combined Layer 2 and Layer 3 scorecard for all 18 dimensions, and the Layer 4 flagged-findings section. It also yields a **SOC 2 deliverable**: a compliance-evidence package a CIO can hand to their SOC 2 auditor as a byproduct of the Phase 0 audit.

---

## The 18 dimensions

Each dimension is inspected mechanically at Layer 2 and, where applicable, assessed against specified markers at Layer 3. Each maps to the published thresholds of the compliance frameworks below.

| # | Dimension | Category |
|---|---|---|
| 4.1 | Entitlement system | Security architecture |
| 4.2 | Authentication | Security architecture |
| 4.3 | Inter-service security | Security architecture |
| 4.4 | Multi-tenancy | Data architecture |
| 4.5 | Audit infrastructure | Compliance engineering |
| 4.6 | Rate limiting | Operational security |
| 4.7 | Configuration and secrets | Operational security |
| 4.8 | Caching | Performance engineering |
| 4.9 | Notifications | Operations |
| 4.10 | CI/CD | DevOps |
| 4.11 | Containerization | Infrastructure |
| 4.12 | Dependency injection | Software architecture |
| 4.13 | Pattern sophistication | Software architecture |
| 4.14 | Architectural philosophy | Software architecture |
| 4.15 | Live documentation | Governance |
| 4.16 | SDLC with AI safeguards | Process engineering |
| 4.17 | Tech debt management | Lifecycle management |
| 4.18 | UX from code | Software development |

---

## Mapped to named compliance frameworks

The audit does not invent its own thresholds. Each indicator and dimension is calibrated against the published thresholds of established compliance and quality frameworks, so a score is auditable against standards a compliance officer already recognizes:

- SOC 2 Trust Services Criteria
- NIST SP 800-53
- OSFI B-13
- OWASP ASVS
- ISO/IEC 25010
- WCAG 2.2, Section 508, EN 301 549, and AODA (accessibility)
- Quebec Law 25

---

## Research and status

The Slop Audit methodology and its underlying measurements are published under the Open Honest research program, pre-registered on the Open Science Framework and independently validated.

- OSF DBSYG block (construct and predictive validity studies): [osf.io/dbsyg](https://osf.io/dbsyg/), DOI [10.17605/OSF.IO/DBSYG](https://doi.org/10.17605/OSF.IO/DBSYG)
- Independent validation: institutional collaboration of record at UQAM/LATECE; assessor protocols and inter-rater-reliability calibration in preparation
- Methodology: complete, approximately 45,000 words of documented procedures across 18 dimensions, four layers, and the SOC 2 deliverable extraction
- Released under Apache-2.0; reference implementation and full specification coming soon under the Open Honest organization on GitHub

---

## Use it

The Slop Audit is an open standard. You can adopt it, run it against your own codebases, and cite it, without asking permission and without buying anything. The specification, the 18-dimension catalog, and the Layer 1 indicator definitions are published under Apache-2.0.

- [The standard in context](https://openhonest.org/frameworks.html) at the Open Honest Foundation
- [Open Honest on GitHub](https://github.com/openhonest) (specification and reference implementation)
- [contact@openhonest.org](mailto:contact@openhonest.org)

---

## Footer

Links: [Open Honest Foundation](https://openhonest.org) · [GitHub](https://github.com/openhonest) · [Researcher](https://adamzacharywasserman.com) · [Contact](mailto:contact@openhonest.org)

Notice: Slop Audit is a trademark of the Open Honest Foundation. Code Apache-2.0 · Content CC-BY-NC-4.0
