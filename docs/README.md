README.md

# Medicare Agent Audition Tools

An automated hiring assessment system for evaluating Medicare Advantage sales candidates on both sales skill and regulatory compliance — without using real protected health information (PHI).

## Overview

This repo contains the **Mock Agent Desktop**, the browser-based tool candidates use during their live audition call. It's one piece of a three-layer assessment system:

1. **Claude Project (evaluation engine)** — Runs the interactive roleplay and produces a Hire / Do Not Hire / Manager Review scorecard. Covers AI-consent disclosure, scenario-based roleplay (e.g. Tricia/Part B Giveback Hook, Richard/Food Allowance Hook), and compliance gate tracking (TPMO disclosure, SOA consent, cross-sell boundaries).
2. **Retell AI voice agent** — Voice interface for the live audition call, powered by Claude Sonnet, with post-call data extraction.
3. **Mock Agent Desktop (this repo)** — A standalone HTML tool simulating the systems a real Medicare sales agent would use mid-call.

Live site: `unifiedgrowthpartners.github.io/agent_audition-tools`

## What's in this repo

- `index.html` — The Agent Desktop Portal, with three tabs:
  - **Provider Search** — fictional NPI/network lookup
  - **Formulary / Rx Lookup** — fictional 2026 formulary and copay data
  - **Eligibility / LIS Status** — fictional dual-eligibility and subsidy lookup
  - Embedded "Start Audition Call" buttons linking to the Retell voice agent
- `Candidate_Compliance_Cheat_Sheet.pdf` — Reference guide given to candidates, covering mandatory call sequencing, verbatim TPMO disclosure language, SOA consent script, and cross-sell/compliance guardrails

## Key design principles

- **No real PHI, ever.** All names, plans, providers, and medical data in this tool are fictional. Candidates are explicitly instructed not to enter their own real health information.
- **Retell and Claude Artifacts are separate environments** and can't be combined directly — hence the standalone HTML page architecture, hosted independently and linked from both the Retell agent and the Claude Project.
- **Compliance-first grading.** No "Hire" recommendation is issued if any regulatory compliance gate (TPMO disclosure, SOA consent, cross-sell boundary) fails, regardless of conversational quality.

## Status / Roadmap

- [x] Claude Project text evaluation engine deployed
- [x] Retell voice agent configured and linked
- [x] Mock Agent Desktop deployed to GitHub Pages
- [ ] Candidate email draft
- [ ] Legal review of AI-in-hiring consent language (IL, NY, MD)
- [ ] Live GitHub Pages confirmation
- [ ] Next test run and feedback pass

## Note

Known non-issue: Chrome/WebGL rendering quirks appear on internal Mosyle-managed test devices but do not affect candidates using personal devices.
