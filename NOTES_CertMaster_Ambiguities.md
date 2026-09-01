# CertMaster Perform (CS0-004 V4) — Terminology Clarifications

Areas of CompTIA CertMaster Perform where the material is internally inconsistent or uses one
term at different levels of detail across modules. Each entry states what the source actually says,
cites the module, and gives the exam-relevant takeaway. Verified against CySA+ CertMaster Perform
V4, the CompTIA CS0-004 V4 Exam Objectives v2.0, and NIST SP 800-61.

---

## 1. "MTTR" means two different things across modules

CertMaster uses the abbreviation **MTTR** at two levels of granularity. Module 8 is the
authoritative KPI chapter and separates response from remediation. Module 12 (an automation
chapter) uses a single, broader "MTTR" that absorbs remediation into it.

### Module 8 — Managing Incident Response and Communication

Module 8 defines the full four-metric mean-time taxonomy:

| Metric | Name | What it measures |
|---|---|---|
| **MTTD** | Mean Time to Detect | Event occurrence → SOC becomes aware of it |
| **MTTR** | Mean Time to **Respond** | Detection → contain & mitigate (isolate hosts, block IPs, disable accounts, kill processes) |
| **MTTRm** | Mean Time to **Remediate** | Full elimination of root cause + restore to normal (patch, reconfigure, rebuild, verify no residual threat) |
| **MTTC** | Mean Time to Close | Detection → full closure through investigation, containment, remediation, and documentation |

Here, **respond** stops at containment and **remediate** is the separate, longer-running root-cause fix.

### Module 12 — Improving Processes with Automation

Module 12 tracks only MTTD and MTTR, and defines MTTR as the time from detection until the threat
is contained, mitigated, **and normal operations are restored**. 

That last clause — *and normal operations are restored* — is the work Module 8 assigns to **MTTRm**. So Module 12's single "MTTR" covers both response and remediation in one number. One of the best, or clearest instances I saw of this difference was in a Lesson 12-2 Practice Quiz question where it identified MTTR as Mean Time to Resolve.

### Resolution

This is a granularity difference between an efficiency chapter and the KPI chapter, not a redefinition. **Module 8's four-metric split is authoritative.** When the exam distinguishes the metrics, use Module 8. CertMaster Perform - Module/Lesson 8 - briefly touches on the many faces of MTTR but, unfortunately, somewhat leaves the reader in suspense in Lesson 12 with its transition in usage without a more declarative nature/ stronger acknowledgment of the switch from its prior usage.

### Exam takeaways

- CS0-004 **Objective 4.2** lists four distinct mean-time metrics — **mean time to close, mean time
  to detect, mean time to respond, mean time to remediate** — so treat them as four separate things.
- **Respond = first containment action.** "The analyst isolated the compromised host" is *respond*, not *remediate*.
- **Remediate = root cause fixed / operations restored** (reimaging, patching, restoring from backup).
- **Close = ticket closed and documented** — the metric that appears in SLAs and executive reporting.
- The bare abbreviation "MTTR" is ambiguous. **Read the verb in the stem** ("respond" vs. "remediate"), not the acronym.
- Clean cross-map: NIST CSF **Detect / Respond / Recover** ↔ **MTTD / Mean-Time-to-Respond / Mean-Time-to-Remediate.**

---

## 2. The incident lifecycle appears at three different granularities

CertMaster presents the incident lifecycle more than once, at different levels of detail and with
different phase names. The apparent 4 vs. 6 vs. 7 "step count" is granularity, not disagreement —
it is the same lifecycle described three ways.

### A. NIST SP 800-61r2 — official 4-phase model (the underlying standard)

| # | Phase |
|---|---|
| 1 | Preparation |
| 2 | Detection & Analysis |
| 3 | Containment, Eradication & Recovery |
| 4 | Post-Incident Activity |

### B. Module 1 — SOC operational lifecycle (6 steps)

> Detection → Triage → Investigation → Response → Eradication and Recovery → Post-Incident Improvement

This is the day-to-day SOC alert-handling workflow. Names specific to this model: **Triage**,
**Investigation** (not "Analysis"), **Response** (containment/isolation), and **Post-Incident
Improvement** (its lessons-learned stage).

### C. Modules 9 & 12 — Incident Response lifecycle (7 stages)

> Preparation → Detection → Analysis → Containment → Eradication → Recovery → Post-incident Activity

Module 9 (Lesson 9B) states this list explicitly and attributes it to **NIST SP 800-61** and
ISO/IEC 27001. Module 12 draws the same cycle as the "Incident Handling Lifecycle."

### How the three reconcile

The 7-stage model is NIST's 4 phases with the two compound phases unrolled:

- NIST **"Detection & Analysis"** → **Detection** + **Analysis**
- NIST **"Containment, Eradication & Recovery"** → **Containment** + **Eradication** + **Recovery**

The Module 1 SOC model is the same idea reorganized for alert handling: Preparation folded into
standing readiness, Triage split out, and Eradication and Recovery kept together as one step.

### Cross-model name map (approximate alignment)

Merged cells mark a single phase in one model that spans several finer-grained steps in another —
NIST's two compound phases, and Module 1's combined Eradication and Recovery step.

<table>
  <thead>
    <tr>
      <th align="left">Concept</th>
      <th align="left">NIST r2 (4)</th>
      <th align="left">Module 1 SOC (6)</th>
      <th align="left">Modules 9/12 IR (7)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Get ready</td>
      <td>Preparation</td>
      <td></td>
      <td>Preparation</td>
    </tr>
    <tr>
      <td>Find it</td>
      <td rowspan="3" align="left" valign="middle">Detection &amp; Analysis</td>
      <td>Detection</td>
      <td rowspan="2" align="left" valign="middle">Detection</td>
    </tr>
    <tr>
      <td>Validate / prioritize</td>
      <td><b>Triage</b></td>
    </tr>
    <tr>
      <td>Understand it</td>
      <td><b>Investigation</b></td>
      <td>Analysis</td>
    </tr>
    <tr>
      <td>Stop the spread</td>
      <td rowspan="3" align="left" valign="middle">Containment,<br>Eradication &amp; Recovery</td>
      <td><b>Response</b></td>
      <td>Containment</td>
    </tr>
    <tr>
      <td>Remove it</td>
      <td rowspan="2" align="left" valign="middle">Eradication and Recovery</td>
      <td>Eradication</td>
    </tr>
    <tr>
      <td>Restore</td>
      <td>Recovery</td>
    </tr>
    <tr>
      <td>Learn</td>
      <td>Post-Incident Activity</td>
      <td>Post-Incident Improvement</td>
      <td>Post-incident Activity</td>
    </tr>
  </tbody>
</table>

*Module 1's SOC model has no explicit Preparation stage; readiness is assumed standing. In the
7-stage model, validate/prioritize falls within Detection, so that cell is merged upward.*

### Exam takeaways

- Match phase names to the cue in the stem. "SOC workflow" / Module 1 language → the 6-step SOC
  model. "Incident response lifecycle" / NIST → the NIST phase names.
- **Containment ≠ Eradication** is the classic trap. Containment stops the spread; eradication
  removes the cause. Rebuilding a system before isolating it is a containment failure.
- The output of the final phase (post-incident) always **feeds back into Preparation.**
- When a scenario names NIST, use NIST's phase names and sequencing as the keyed-answer basis.

### Currency note (real world, not exam)

NIST **withdrew SP 800-61r2 on April 3, 2025** and replaced it with **Revision 3**, which
reorganizes incident response around the **CSF 2.0** functions (Govern, Identify, Protect, Detect,
Respond, Recover) and drops the classic four-phase diagram. **CS0-004 V4 and CertMaster are still
written to r2**, so r2's phase names remain exam-authoritative. Don't be thrown if current NIST
material looks nothing like the four-phase model when read outside the course.

---

## 3. "Playbook" vs. "runbook" — distinguished on different axes in two modules

CertMaster defines the playbook/runbook distinction twice, and the two lessons draw the line
differently. Module 11 separates them by **degree of automation**; Module 12 separates them by
**level of detail**. Same two words, two different defining properties.

### Module 11 — Automating Data Analysis (SOAR Workflows)

Distinguishes by **automation**:

- **Playbook** — a checklist of actions to perform in response to a specific event, made specific
  with query strings and signatures.
- **Runbook** — what a playbook is called when it "utilizes a high degree of automation from a SOAR
  system," automating as many stages as possible with defined human-interaction points. The module
  notes the terms are commonly used interchangeably.

Here, **automation is the whole differentiator**: a runbook is an automated playbook.

### Module 12 — Improving Processes with Automation (Designing Effective Playbooks/Runbooks)

Distinguishes by **level of abstraction**:

- **Playbook** — the high-level response plan, focusing on the **what and why**; conceptual, with
  diagrams and decision trees.
- **Runbook** — the **detailed step-by-step procedure**, focusing on the **how**; concrete click
  paths, commands, and scripts; written like a checklist and used by front-line operators.

Here, automation is **not** the differentiator. Module 12 lists "runbook" alongside SOP and checklist
as a type of manual procedure, so a Module 12 runbook can be executed entirely by hand.

### The discrepancy

| | Module 11 | Module 12 |
|---|---|---|
| **Defining axis** | Degree of automation | Level of abstraction |
| **Playbook** | Workflow/checklist for an event | High-level plan (what/why) |
| **Runbook** | Playbook **with SOAR automation** | Detailed step-level procedure (how) |
| **Is a runbook automated?** | **Yes — that is what makes it a runbook** | **Not necessarily — it can be a manual checklist** |

### Resolution

The two lessons agree on one thing: the **playbook is the higher-level plan** and the **runbook is
the more granular executor** that carries out the playbook's steps (Module 11: it automates the
playbook's stages; Module 12: it supports the playbook's steps). They diverge only on whether
**automation** is essential to the term "runbook" — Module 11 says yes, Module 12 says no.

### Exam takeaways

- **The shared through-line:** playbook = higher-level (decisions, what/why); runbook =
  lower-level (the executable step-by-step, the how). Both modules agree on this — it is the
  safe core of the distinction.
- **Detail and automation are one axis, not two.** A runbook's granularity is what makes it
  automatable: you can have a detailed *manual* runbook, but you cannot automate high-level
  guidance. Automation is the downstream consequence of reducing a procedure to deterministic,
  judgment-free steps — not a separate criterion. A runbook is essentially an algorithm;
  "automation" just names the case where a machine, not a person, executes it.
- **On a question:** if the contrast is *high-level vs. detailed step-by-step*, decide on that
  basis (Module 12's framing). If it specifically hinges on *SOAR / machine execution*, the
  runbook is the automated one (Module 11's framing). Do not treat "level of detail" as wrong —
  it is CertMaster's own Module 12 definition.

---

*Sources: CySA+ CertMaster Perform V4 — Module 1 (SOC lifecycle), Module 8 (mean-time KPIs),
Module 9 Lesson 9B (IR process / NIST attribution), Module 11 (SOAR workflows — playbook/runbook by
automation), Module 12 (automation, incident handling lifecycle, playbook/runbook by detail level).
CompTIA CS0-004 V4 Exam Objectives v2.0, Obj. 4.2. NIST SP 800-61r2 (withdrawn Apr 3, 2025) and r3.*

#### *Repo Author's note: I'm not certain whether the ambiguities I noticed are true ambiguities in the sense that if someone with actual SOC experience had read the material - I suspect - they may not have had any issues understanding what I point out above. But, to someone not experienced, such as myself doing this as part personal improvement/employability enhancement I had issues with these and it took some review and discussing/arguing with AI to come to what I think are the proper conclusions. The CompTIA objectives clearly state the work experience of the desired candidate, so I am more inclined to believe these were personal deficiencies, and not any type of actual flaw in the material.*


