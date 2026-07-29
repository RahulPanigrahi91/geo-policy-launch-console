# Geo Policy Launch Console

Geo Policy Launch Console is a single-page web app that turns a proposed Maps-like feature into a structured launch decision: policy risk score, stakeholder escalation path, enforcement plan (policy / tooling / human review), vendor readiness, and a 14-day post-launch monitoring plan.

## Repo name

**geo-policy-launch-console**

Description:

> Internal policy operations prototype for Geo/Maps-style feature launches with risk scoring, escalation routing, vendor readiness, and post-launch monitoring.

---

## What this project is

This project simulates how a Program Manager / Policy Specialist in Google Geo would operationalize policy for a new feature on Maps, such as AI-generated place summaries, user-submitted road edits, or vendor-created data imports.

Instead of a static policy document, the app asks structured questions about the feature — region, impact, abuse potential, privacy, government sensitivity, and ML/vendor dependence — then produces:

- A deterministic policy risk score from 0 to 100, with Low / Moderate / High / Critical bands.
- A stakeholder escalation path covering Policy, Product, Legal, Trust & Safety, Government Affairs, Tools/ML, and Vendor Ops.
- An enforcement plan split across policy rules, ML/tooling controls, and human/vendor workflows.
- A vendor readiness view with guidance completeness, SLA confidence, ambiguity flags, and status.
- A post-launch watchlist and a first 14-day monitoring plan.

The design mirrors how a real Geo policy operations workflow works: clear policy rules, automated assessment, human review, escalation handling, and ongoing monitoring.

---

## Why it is relevant to Google Geo

The Program Manager, Policy Specialist – Geo role focuses on developing geo data policies, partnering with Product, Operations, Trust & Safety, Legal, and Government Affairs, integrating policy into tools and models, handling sensitive escalations, and managing vendor relationships for ongoing policy execution.

This prototype demonstrates that operating model in a simple, reviewable way. It shows how policy requirements can be turned into a repeatable workflow that connects risk, escalation, enforcement, and vendor operations.

---

## Core workflow

The app follows a five-step policy operations workflow:

1. **Feature intake**  
   Capture feature name, category, region, launch type, content sources, impact, abuse potential, privacy sensitivity, public/government sensitivity, vendor dependence, model/tool dependence, and known failure scenarios.

2. **Risk scoring**  
   Compute a visible risk score from 0 to 100 using fixed weights and map it to Low / Moderate / High / Critical.

3. **Escalation routing**  
   Recommend stakeholders such as Legal, Government Affairs, Trust & Safety, Tools/ML, Vendor Ops, plus Product and Policy.

4. **Enforcement planning**  
   Split controls into:
   - Policy rule / launch requirements.
   - ML / tooling enforcement.
   - Human review / vendor operations.

5. **Vendor readiness and monitoring**  
   Estimate completeness, SLA confidence, and ambiguity flags, then derive vendor status and a 14-day monitoring plan.

---

## Included scenarios

Three sample scenarios are preloaded:

- AI-generated place summary suggestions.
- Bulk vendor-created business category update.
- User-submitted road closure edits.

Each scenario pre-fills the form and shows a different risk, escalation, and readiness profile.

---

## Tech details

- Single-file static web app (`geo-policy-launch-console.html`)
- HTML, CSS, vanilla JavaScript
- Client-side state only
- No backend
- No login
- Deterministic logic
- Printable one-page launch brief

---

## How to run

1. Clone the repo or download it as a ZIP.
2. Open `geo-policy-launch-console.html` in a browser.
3. Choose a sample scenario or fill in your own feature.
4. Click **Run policy assessment**.
5. Use **Compare scenarios** or **Download brief** if needed.

No installation or backend setup is required.

---

## What a reviewer should notice

- This is a policy operations prototype, not just a UI demo.
- It maps directly to the responsibilities of the Geo Policy Specialist role.
- The logic is transparent and easy to inspect.
- It demonstrates product thinking, risk classification, stakeholder coordination, and operational execution.

---

## Disclaimer

This is a simulation prototype built only with public information and does not use internal Google data or proprietary systems.
