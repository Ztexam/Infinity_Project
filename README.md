# Infinity Project — Job Shortlist

Infinity Job Shortlist connects live US job matching with explainable employer financial evidence. A candidate searches keywords and locations; two deployed IBM watsonx Orchestrate agents collaborate to return up to ten eligible openings with scores, explanations, and direct job/report links.

## Download and run the working source

1. Download **[Infinity_Project_Submission_Source.zip](Infinity_Project_Submission_Source.zip)** using GitHub's download button on that file's page.
2. Extract that source ZIP to a writable folder. It contains the complete Python service, frontend, tests, data metadata, agent instructions, setup documentation, and dated QA records in their required directory structure.
3. Install **Python 3.11+**. On Windows, double-click **Start Shortlist.cmd** in the extracted source folder. On macOS/Linux, run `sh start.sh`.
4. Open **http://localhost:8080/live**. The first launch installs pinned dependencies. Keep the launcher running.

If you download this entire repository as a ZIP, extract it first, then extract the nested **Infinity_Project_Submission_Source.zip** before launching.

**IBM connection:** the two deployed agents belong to a private lab instance. This public source archive intentionally contains no signing keys, tokens, encrypted personal connection backup, or transfer password. A new installation needs an authorized encrypted connection transfer from the instance owner, or its own IBM instance/signing configuration. Follow **PORTABLE_SETUP.md** inside the source archive. Once connected, embedded chat uses short-lived signed tokens, so no IBM API key is entered in the browser. Instance access, usage allowances, and service availability still apply.

## Two-agent mechanism

- **Infinity Job Shortlist** receives relevant listings and sends complete company financial evidence to its collaborator.
- **Infinity Company Assessment** explains the supplied cash flow, revenue growth, R&D, reporting period, score, and eligibility.
- The shortlist agent explains up to ten distinct eligible job URLs. Multiple jobs at one employer remain separate opportunities.

Python calculates the provisional score: **50% cash flow, 30% revenue growth, 20% R&D**. Eligibility requires **strictly above 5/10** and positive operating cash flow for the reported period. Comparable six-month reports are accepted. Missing evidence means unassessed. Scores support research; they do not guarantee company stability or employment.

## IBM Bob evidence

IBM Bob implemented the initial live frontend and `GET /live` route. The original task was reopened in **ibm-skillsbuild-ell** on November 20 without starting another AI task; its visible usage was **1.07 Bobcoins**. See **[bob_sessions](bob_sessions)** for the completed-task and expanded task-header screenshots. Later enhancements and IBM deployment were performed separately.

## Coverage and validation

The POC checks **72 employer boards**, supports locations across **all 50 states**, and uses free public job feeds and financial sources. Concurrent collection, throttling, and caches reduce repeated work. The UI identifies refreshed, cached, and failed sources.

The dated November 19 HRIS/Python test checked 72/72 boards and found 856 matching openings across 96 employers. The corrected live agent test returned ten application links and ten report links in the expected order and accepted six-month evidence. All 36 local tests and the scoring check also pass on the public source copy. Detailed evidence is under **docs/** inside the source archive; fixture-based unit tests are distinct from recorded real IBM executions.

The frontend/Python service runs locally; the two runtime agents are hosted on IBM. Windows relocation was tested. Native macOS/Linux and Docker execution remain unverified. A new operator cannot access the private IBM instance simply by downloading the code.

## Submission materials

- [Problem and solution](problem_solution.txt)
- [Technology statement](technology_statement.txt)
- [Data-source inventory](DATA_SOURCES.txt)
- Full setup, code, tests, agent change record, and QA: **Infinity_Project_Submission_Source.zip**

The narrated submission screen demonstration is being prepared. The existing Ava animation is an explainer and does not by itself satisfy the portal's on-screen-demo requirement. No official AI advisor precheck has run yet.

This public package omits historical job-description excerpts and all private connection material. Free public access is not an unrestricted content license; provider/employer terms need review before redistribution or commercial operation. No employee reviews are fabricated and no applications are submitted.
