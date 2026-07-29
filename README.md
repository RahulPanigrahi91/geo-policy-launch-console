# Geo Policy Launch Console

Geo Policy Launch Console is a single-page web app that turns a proposed Maps‑like feature into a structured launch decision: policy risk score, stakeholder escalation path, enforcement plan (policy / tooling / human review), vendor readiness, and a 14‑day post‑launch monitoring plan.[web:27][web:77]

## 1. What this project is

This project simulates how a Program Manager / Policy Specialist in Google Geo would operationalize policy for a new feature on Maps (e.g., AI-generated place summaries, user-submitted road edits, vendor-created data imports).[web:14][web:15]  

Instead of a static policy document, the app asks structured questions about the feature (region, impact, abuse potential, privacy, government sensitivity, ML/vendor dependence), then produces:

- A deterministic policy **risk score** (0–100, Low/Moderate/High/Critical).[web:27][web:77]
- A **stakeholder escalation path** (Policy, Product, Legal, Trust & Safety, Government Affairs, Tools/ML, Vendor Ops) based on selected risk factors.[web:14][web:15]
- An **enforcement plan** split across policy rules, ML/tooling controls, and human/vendor workflows.[web:27][web:61]
- A **vendor readiness** view: guidance completeness, SLA confidence, ambiguity flags, and status (Ready / Needs clarification / Blocked).[web:14][web:15]
- A simple **post-launch watchlist** and first 14‑day monitoring plan.[web:27][web:80]

The design mirrors Google Maps’ published approach to content trust and safety: clear policies, automated systems that assess content at scale, trained human operators and analysts, and extra safeguards during elevated abuse.[web:27][web:77]

---

## 2. Why it is relevant to Google Geo

The Program Manager, Policy Specialist – Geo role is described as:[web:14][web:15]

- Developing and maintaining geo data policies for new Maps features.
- Partnering with Product, Operations, Trust & Safety, Legal, and Government Affairs.
- Partnering with Tools and Machine Intelligence teams to integrate policy into algorithms.
- Managing sensitive policy escalations.
- Managing vendor relationships for ongoing policy execution.

Geo Policy Launch Console is a small, self-contained prototype of that operating model:

- It **turns policy and risk into a repeatable workflow**, not just guidelines.
- It **encodes cross-functional escalation logic** instead of relying on memory.
- It **connects policy decisions to ML/tooling and vendor operations** in one view.[web:27][web:61][web:80]
- It is designed so policy stakeholders can review and challenge the logic transparently, which is important in governance and trust contexts.

---

## 3. Core workflow

The app follows a five-step policy operations workflow:[web:27][web:77]

1. **Feature intake**  
   - Capture feature name, category (e.g., reviews, road edits, AI recommendations), region, launch type, content sources (user, vendor, partner, ML, internal), impact, abuse potential, privacy sensitivity, public/government sensitivity, vendor dependence, model/tool dependence, and known failure scenarios.

2. **Risk scoring**  
   - Compute a visible 0–100 policy risk score using fixed weights.
   - Map score into Low / Moderate / High / Critical risk bands.

3. **Escalation routing**  
   - Add Legal when privacy is High.
   - Add Government Affairs when government sensitivity is High.
   - Add Trust & Safety when abuse is High.
   - Add Tools / ML when model dependence is High or content includes ML-generated outputs.
   - Add Vendor Operations when vendor dependence is Partial or High.
   - Always include Product and Policy.[web:14][web:15]

4. **Enforcement planning**  
   - Split controls into:
     - **Policy rule / launch requirements** (e.g., restricted attributes, prohibited content examples).
     - **ML / tooling enforcement** (e.g., confidence thresholds, output auditing, rollback triggers).[web:26][web:34]
     - **Human review / vendor operations** (e.g., QA sampling, escalation queues, SLA tracking).

5. **Vendor readiness & monitoring**  
   - Estimate:
     - content guideline completeness (%),
     - SLA confidence (%),
     - ambiguity flags (missing description, missing failure scenarios, unclear ML scope, unclear vendor guidance).
   - Derive vendor status: Ready / Needs clarification / Blocked.[web:14][web:79]
   - Present four watch metrics (escalation volume, violation rate, false positive rate, vendor turnaround risk) and a brief 14‑day monitoring plan.[web:27][web:80]

---

## 4. Included scenarios

The app ships with three sample scenarios so a reviewer can understand the workflow immediately:

| Scenario                                        | Focus area                                                     |
| ---------------------------------------------- | -------------------------------------------------------------- |
| AI-generated place summary suggestions         | ML governance, content policy, hallucinations / bias, rollout |
| Bulk vendor-created business category update   | Vendor execution, QA, SLA, ambiguity handling                 |
| User-submitted road closure edits              | High impact, abuse potential, government sensitivity           |

Each scenario pre-fills the intake form and produces a different mix of risk, escalations, controls, and vendor status.

---

## 5. Tech details

- Single-page static web app (`geo-policy-launch-console.html`)
- HTML, CSS, vanilla JavaScript
- Client-side state only
- No backend, no login
- Preloaded scenarios and deterministic logic
- Printable one-page “launch brief” view (browser print)

The architecture is intentionally simple: the goal is **policy and program thinking**, not infra complexity.

---

## 6. How to run

1. Clone the repo or download it as a ZIP.
2. Open `geo-policy-launch-console.html` in any modern browser.
3. Choose a sample scenario from the **Sample Scenarios** dropdown.
4. Click **Run policy assessment** to view risk, escalations, controls, vendor readiness, and monitoring.
5. Use **Compare scenarios** to see two launch paths side by side.
6. Use **Download brief** (print) to generate a one-page launch summary for sharing.

---

## 7. What a recruiter / interviewer should see

- This is a **policy operations prototype**, not just a UI exercise.
- The project directly reflects the responsibilities in the Geo Policy Specialist JD (policy creation, escalations, ML integration, vendor management).[web:14][web:15]
- The logic is **transparent and reviewable**, which matters for governance and trust & safety.[web:27][web:61]
- It demonstrates:
  - product and program thinking,
  - risk and policy intuition,
  - ability to turn ambiguous requirements into a usable internal tool.

---

## 8. Disclaimer

This is a simulation prototype built only with publicly available information about Google Maps’ policies, trust & safety approach, and the Program Manager, Policy Specialist – Geo job description.[web:14][web:15][web:27][web:61][web:77]  
It does not use internal Google data, systems, or proprietary workflows.
