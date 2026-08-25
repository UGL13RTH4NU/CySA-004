# Prompt for Creating CySA+ CS0-004 V4 (WGU Cybersecurity Analyst Course) Anki Flashcards

## Course Context

This is for the WGU cybersecurity analyst course preparing students for the **CompTIA CySA+ CS0-004 V4 certification exam**. The course covers security operations, vulnerability management, incident response and management, and reporting and communication.

The CS0-004 V4 exam is **a maximum of 85 questions in 165 minutes**, with a passing score of **750 on a 100–900 scale**. The exam includes both **multiple-choice** and **performance-based questions (PBQs)** — PBQs simulate real SOC/vuln-analyst work: reading logs, interpreting tool output (Nmap, tcpdump, Snort, Wireshark, SIEM alerts), analyzing packet captures, matching indicators to attack patterns, and reasoning through incident response steps. Recommended experience is approximately **4 years hands-on as a SOC analyst (level 2) or vulnerability analyst**, so scenarios are meant to feel operational, not academic.

Cards should focus on:

- Definitions and distinctions between commonly confused concepts (SIEM vs SOAR, EDR vs XDR, IDS vs IPS, SAST vs DAST, etc.)
- "Which tool/framework/process is best for X" scenario decisions
- **Reading and interpreting output** — logs, packet captures, command output, regex, YARA rules, Snort signatures, Nmap results
- **Framework structure and application** — Cyber Kill Chain phases, Diamond Model vertices, MITRE ATT&CK tactics, STRIDE categories, Pyramid of Pain levels, CVSS metric groups
- Indicator-of-compromise (IoC) recognition and classification (atomic vs behavioral)
- Incident response process ordering and technique selection
- Vulnerability prioritization criteria and scoring
- Reporting metrics, KPIs, and stakeholder-communication scenarios

## Exam Domain Weights (for prioritization)

| Domain                               | Weight |
| ------------------------------------ | ------ |
| 1.0 Security Operations              | 34%    |
| 2.0 Vulnerability Management         | 26%    |
| 3.0 Incident Response and Management | 24%    |
| 4.0 Reporting and Communication      | 16%    |

Domain 1 alone is a third of the exam — card volume should reflect this.

## Source Material

* **Primary**: CompTIA CertMaster Perform platform for CySA+ CS0-004 (14 Lessons/Modules — see mapping below)
* **Authoritative reference**: CompTIA CS0-004 V4 Exam Objectives (Version 2.0) — every sub-bullet in the objectives document should be covered by at least one card
* **Supplementary (as available)**: any WGU-provided study guide, Sybex CySA+ Study Guide (CS0-004), PBQ practice sets
* Cards will be created one module at a time (or grouped by domain)

### Handling CertMaster PDF vs. Online Discrepancies

If the CertMaster PDF and the online version conflict, the **online version is authoritative** (this pattern was true in the Data+ course and is likely to recur here). Note any discrepancies encountered while generating cards so they can be flagged during review.

## Output Format Requirements

* Tab-separated text file that can be imported directly into Anki
* Include these header lines at the top of the file:

```
#separator:tab
#html:true
#tags column:3
```

* Each card should have 3 columns separated by tabs:
  
  * Front (question)
  * Back (answer)
  * Tags (hierarchical format: `CySA004::ModuleXX::ObjX.Y::TopicName`)

* Use a Python script with a `card()` function that calls `.replace('\n', '')` on all content before writing each line to the file. Each card must be a single line in the output file.

* Validate output: exactly two tab characters per line, no internal newlines, three-line Anki header at top.

## Formatting Requirements

* Use HTML formatting (the file will have `#html:true`)
* Each card must be written as a single line — all HTML must be collapsed so there are no literal newlines within a card's front, back, or tag fields
* For **bold emphasis with color** (key concepts): `<b style="color:#2874A6">text here</b>`
* For **success/correct answer callouts**: `<b style="color:#27AE60">text</b>`
* For **warning/danger callouts**: `<b style="color:#C0392B">text</b>`
* For **technical terms / commands / code / syntax**: `<code style="color:#E74C3C; background:rgba(128,128,128,0.1); padding:2px 4px; border-radius:3px;">KEYWORD</code>`
* For **log excerpts / multi-line command output**: use a `<pre>` block styled with `background:rgba(128,128,128,0.15); padding:8px; border-radius:4px; font-family:monospace; font-size:0.9em; white-space:pre-wrap;` — but collapse to a single line inside the card by using `<br>` between "logical" lines (no literal newlines allowed in the card file)
* Use `<br>` for line breaks within a field
* Use `&nbsp;` for indentation where needed

### Emoji Palette (cyber-themed)

Use emojis where they aid memory or signal card category — not decoratively.

| Emoji | Use                                                                                                                                                              |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🛡️   | Defense, controls, protection                                                                                                                                    |
| 🎯    | Prioritization, targeting, SOC Analyst Perspective note                                                                                                          |
| 🔍    | Analysis, investigation, threat hunting                                                                                                                          |
| ⚠️    | Warnings, cautions                                                                                                                                               |
| 🚨    | Incidents, alerts                                                                                                                                                |
| 🕵️   | Threat hunting, adversary attribution                                                                                                                            |
| 🐛    | Vulnerabilities, malware, exploits                                                                                                                               |
| 🔐    | Encryption, secrets management                                                                                                                                   |
| 🔑    | Authentication, keys, credentials, PAM                                                                                                                           |
| 🌐    | Network concepts                                                                                                                                                 |
| 💻    | Endpoint, host indicators                                                                                                                                        |
| ☁️    | Cloud (native, hybrid, SASE)                                                                                                                                     |
| 🔗    | MITRE ATT&CK chains, BSCSIA Cross-Reference                                                                                                                      |
| 🧪    | Sandboxing, malware analysis, file analysis                                                                                                                      |
| 🚦    | Severity, risk levels, CVSS                                                                                                                                      |
| ⏱️    | Time metrics (MTTD, MTTR, MTTC)                                                                                                                                  |
| 🧠    | Threat intelligence                                                                                                                                              |
| 🪤    | Cyber deception, honeypots, honeytokens                                                                                                                          |
| 📊    | Metrics, KPIs, dashboards                                                                                                                                        |
| 📝    | Reporting, documentation, playbooks                                                                                                                              |
| 🧩    | Frameworks (Kill Chain, Diamond, MITRE, STRIDE)                                                                                                                  |
| 🔄    | Process/lifecycle (IR phases, vuln mgmt cycle)                                                                                                                   |
| 📛    | *Reserved* — used only for flagging genuinely defective source explanations (used in quiz cards; may appear here if a CertMaster passage is logically defective) |

## Dark/Light Mode Color Rules

**Non-negotiable — this bit the Data+ deck when solid pastel backgrounds inverted incorrectly in AnkiMobile dark mode.**

* Do **NOT** use hardcoded hex background colors in tables, callout boxes, or highlight boxes — these become unreadable in Anki's dark mode on mobile
* Use `background:rgba(128,128,128,0.15)` for highlighted rows/boxes (subtle neutral gray that works in both modes)
* Use `background:rgba(128,128,128,0.08)` for alternating rows (lighter variant)
* For colored borders on callout boxes (e.g., orange border for the 📛 flag), use `border-left:4px solid #E67E22` and pair with `rgba()` background — never a solid pastel fill
* All text must be readable in both Anki dark mode (mobile) and light mode (desktop)

## Card Content Guidelines

### Depth and Focus

* Cards should be **exam-oriented**: scenario-based recognition, definitions, tool/output identification, and "best choice" decisions for CompTIA-style multiple-choice questions **and** performance-based questions
* CompTIA loves **"which is the BEST"** and **"which is MOST appropriate"** phrasing — cards should train the student to distinguish between good and best answers, especially on close pairs (e.g., MTTD vs MTTR, containment vs eradication, IoC vs IoA)
* The exam is **vendor-neutral in concept** but **specific in tool naming** — you WILL be asked which tool does X (e.g., "Which tool would parse and decode a Base64 string?" → CyberChef). Cards must cover the specific tool names in the objectives (see Objective 1.3 for the full tool inventory)
* **PBQ readiness**: include cards that show a snippet of log/output/command and ask what it does or what attack it indicates — the exam does not require writing scripts or rules from scratch, but does require reading them
* **Acronym discipline**: CySA+ is acronym-heavy. Every acronym in the CS0-004 V4 acronym list should have a quick-recall card at minimum

### Card Types to Include

1. **Key Term Definitions** — concise definitions of tools, controls, frameworks, and concepts
   
   * Example: "What is a SIEM?" → definition + typical inputs + what it produces
   * Example: "What is EDR?" → definition + contrast with XDR

2. **Concept Distinction Cards** — commonly confused pairs
   
   * SIEM vs SOAR, EDR vs XDR, IDS vs IPS, SAST vs DAST, IoC vs IoA, atomic vs behavioral IoC, containment vs eradication, inherent vs residual risk, agent vs agentless scanning, credentialed vs non-credentialed, passive vs active scanning, internal vs external context

3. **"Which Tool" Scenario Cards** — given a scenario or output, pick the tool
   
   * Example: "An analyst needs to decode a Base64-encoded PowerShell command found in a suspicious log entry. Which tool is MOST appropriate?" → CyberChef
   * Example: "An analyst needs to search a corpus of files for a specific byte pattern indicating known malware. Which tool is MOST appropriate?" → YARA

4. **Framework Structure Cards** — for each of the frameworks, drill both the ordered list and the individual meaning of each step/vertex/tactic
   
   * Cyber Kill Chain: Recon → Weaponization → Delivery → Exploitation → Installation → C2 → Actions on Objectives
   * Diamond Model: Adversary, Capability, Infrastructure, Victim (four vertices)
   * MITRE ATT&CK: high-level tactics (Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, C2, Exfiltration, Impact) and how it differs from Kill Chain
   * STRIDE: Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege
   * Pyramid of Pain levels: Hash values → IP addresses → Domain names → Network/host artifacts → Tools → TTPs (and why higher = more painful for adversary)
   * CVSS metric groups: Base, Temporal, Environmental
   * NIST-style incident response phases: Preparation, Detection, Analysis, Containment, Eradication, Recovery, Post-incident

5. **Log/Output Interpretation Cards** — given a snippet, identify the activity
   
   * Example: Show a Windows Event Log entry (EVTX) with Event ID 4625 (failed logon) and ask what it indicates
   * Example: Show a Snort rule and ask what traffic it matches
   * Example: Show tcpdump output and ask what protocol/port is captured
   * Example: Show a Nmap flag combination and ask what scan type it performs (`-sS`, `-sT`, `-sU`, `-sV`, `-O`, etc.)
   * Example: Show a regex pattern and ask what it matches

6. **Indicator Recognition Cards** — given a described anomaly, identify the indicator category and likely activity
   
   * Example: "A host that normally sees 200MB/day of egress traffic suddenly generates 40GB in one hour to an unfamiliar external IP. What indicator category is this and what should be suspected?" → Anomalous activity / data exfiltration
   * Example: "A user account authenticates from Denver at 09:00 UTC and from Kuala Lumpur at 09:45 UTC. What is this indicator?" → Impossible travel

7. **IR Process Cards** — ordering and phase-appropriate actions
   
   * "Which IR phase is this activity part of?" cards
   * "What is the difference between short-term and long-term containment?"
   * "What is the correct order of steps in evidence handling to preserve chain of custody?"

8. **Vulnerability Scoring & Prioritization Cards**
   
   * CVSS Base metric components (AV, AC, PR, UI, S, C, I, A) — what each abbreviation means and its scoring impact
   * EPSS vs CVSS — what each measures, why they're used together
   * Prioritization scenario cards: given CVSS score + exploit availability + asset value + patch availability + context (internal/external/isolated), which vuln to remediate first

9. **Reporting & KPI Cards**
   
   * Mean time to detect (MTTD), respond (MTTR — note: "respond" not "recover" in CySA+ context), remediate, and close — definitions and formulas
   * Alert volume, false-positive rate, true-positive rate
   * Executive summary vs after-action report vs internal threat intel report — audience and content differences
   * Communication plan stakeholders and when each is engaged (legal, PR, regulators, law enforcement, customers)

10. **Governance/Third-Party Risk Cards**
    
    * Control types (administrative, technical, physical) and control functions (preventative, detective, responsive, corrective) — including two-axis classification cards ("A firewall is what type AND what function?" → Technical, Preventative)
    * Risk appetite vs residual risk vs inherent risk
    * SBOM, SCA, supply chain risk concepts

11. **AI in SecOps Cards** (Objective 1.6)
    
    * AI risks: hallucinations, data exposure, model poisoning, malicious prompts
    * Governance: AI usage policies, legal/regulatory compliance
    * Use cases: log analysis, event correlation, artifact comparison, incident investigation

### Card Content Rules

* Cards should be self-contained (Anki serves them out of order — no "as discussed in the previous card" references)
* Break content into logical, digestible groups — avoid walls of text on the back
* Include **mnemonic aids** where they land naturally:
  * STRIDE = **S**poofing, **T**ampering, **R**epudiation, **I**nfo disclosure, **D**oS, **E**oP
  * CIA triad (foundational) and its expanded IAAA (Identification, Authentication, Authorization, Accounting)
  * Cyber Kill Chain 7-step order — one letter mnemonic per step if useful
* When listing items (e.g., the 7 IR phases, the 6 STRIDE categories, the 6 levels of Pyramid of Pain), include brief descriptions, not just names
* For scenario cards, include a brief explanation of **WHY the answer is correct and why the alternatives are wrong** — the "trap analysis" pattern from Data+ carries over here
* **🎯 SOC Analyst Perspective** notes: when a concept has a distinctive operational reality in a real SOC (e.g., "In practice, alert tuning consumes most L1 analyst time"), add a brief italicized SOC Analyst Perspective note. Use sparingly — only when the perspective adds real value.



## Tag Structure

Tags follow this hierarchy: `CySA004::ModuleXX::ObjX.Y::TopicName`

Where:

* `CySA004` = certification prefix (swap for a WGU course code if preferred — this must be consistent across the deck)
* `ModuleXX` = zero-padded module number (01–14) matching the CertMaster course structure
* `ObjX.Y` = primary CS0-004 V4 exam objective the card covers (e.g., `Obj1.4` for Threat Intelligence, `Obj2.3` for vulnerability prioritization)
* `TopicName` = specific topic within the objective (PascalCase, no spaces)

Example: `CySA004::Module06::Obj1.4::PyramidOfPain`

For cards that cross-cut multiple objectives, tag by the primary objective. Add flat additional tags (space-separated in the tag column) only when a card is genuinely dual-purpose.

## Provisional Module → Exam Objective Mapping

*Refine each row after inspecting the actual CertMaster content for that module. This is a starting scaffold, not the final mapping.*

| #   | Module Title                                 | Primary Exam Objective(s)                                                                                                                                                                                      | Notes                                                                      |
| --- | -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| 01  | Identifying Security Operations Fundamentals | 1.1 (logging, OS concepts), some 1.5, 1.6                                                                                                                                                                      | Foundational SecOps concepts, log ingestion/retention, system processes    |
| 02  | Applying Risk Management Strategies          | 2.4 (control types, risk concepts, risk mgmt), 2.3 (mitigation)                                                                                                                                                | Administrative/technical/physical controls; accept/transfer/avoid/mitigate |
| 03  | Managing System Security and Configurations  | 1.1 (system hardening, encryption, data protection), 2.1 (baselines: PCI DSS, CIS, ISO 27000)                                                                                                                  | Hardening, encryption techniques, baselines                                |
| 04  | Comparing System Architectures               | 1.1 (network architecture: ZTNA, SASE, hybrid cloud; virtualization, containerization, APIs, critical infrastructure OT/ICS/SCADA)                                                                             | Architecture concepts across cloud/on-prem/OT                              |
| 05  | Applying Access Management                   | 1.1 (IAM, PAM, authn/authz, secrets mgmt)                                                                                                                                                                      | IAM depth                                                                  |
| 06  | Threat Intelligence and Threat Hunting       | 1.4 (threat actors, TTPs, Pyramid of Pain, MITRE ATT&CK, IoC types, STRIDE, threat modeling, cyber deception)                                                                                                  | Frameworks-heavy module                                                    |
| 07  | Assessing Network Vulnerabilities            | 2.1 (scanning methods, scan types), 2.2 (tool output: Nmap, Nessus, OpenVAS, Masscan, Angry IP, Maltego, Recon-ng), 2.3 (prioritization)                                                                       | Tool output interpretation — PBQ-relevant                                  |
| 08  | Managing Incident Response and Communication | 3.3 (IR techniques), 4.2 (IR reporting: executive summary, after-action, communication plan, stakeholders, KPIs like MTTD/MTTR)                                                                                | Bridges Domain 3 and Domain 4                                              |
| 09  | Executing Incident Response Plans            | 3.1 (attack frameworks: Kill Chain, Diamond, MITRE ATT&CK), 3.2 (IR process phases), 3.3 (IR techniques: chain of custody, legal hold, RCA)                                                                    | Core IR domain                                                             |
| 10  | Analyzing Malicious Activity                 | 1.2 (indicators: network, host, application, cloud, identity, email, social engineering), 1.3 (tools: CyberChef, Wireshark, tcpdump, Snort, Suricata, Zeek, SIEM, EDR/XDR, YARA, VirusTotal, sandboxing, UEBA) | Heaviest tool/output interpretation module                                 |
| 11  | Automating Data Analysis                     | 1.3 (file formats: JSON, XML, YAML, EVTX; scripting: Python, PowerShell, shell), 1.5 (data enrichment, rule/alert tuning)                                                                                      | Reading scripts and structured data                                        |
| 12  | Improving Processes with Automation          | 1.5 (SOAR, IaC, playbooks/runbooks, APIs, webhooks, plug-ins)                                                                                                                                                  | Automation and orchestration                                               |
| 13  | Assessing Application Vulnerabilities        | 2.2 (web app scanners: Burp Suite, ZAP, Nikto), 2.4 (SAST, DAST, SAMM)                                                                                                                                         | AppSec assessment tools                                                    |
| 14  | Securing Applications                        | 2.3 (secure coding, attack surface mgmt), 2.4 (SAMM, supply chain, SCA, SBOM)                                                                                                                                  | Secure-development lifecycle concepts                                      |

*Objective 1.6 (AI in security ops) and Objective 4.1 (vulnerability management reporting) may be sprinkled across multiple modules. Verify against actual CertMaster content and add explicit coverage cards if any objective sub-bullet is not addressed by the module cards.*

## What Will Be Provided for Each Module

* The module number and its topic areas
* The specific CertMaster Perform lesson content (PDF and/or online transcript)
* Any WGU-provided study guide sections
* Any supplemental materials (Sybex study guide sections, notes, screenshots) as available

## Estimated Card Counts Per Module

| Module | Topic                               | Est. Cards    |
| ------ | ----------------------------------- | ------------- |
| 01     | Security Operations Fundamentals    | 40–110        |
| 02     | Risk Management Strategies          | 35–90         |
| 03     | System Security & Configurations    | 40–100        |
| 04     | System Architectures                | 45–110        |
| 05     | Access Management                   | 40–100        |
| 06     | Threat Intel & Threat Hunting       | 50–120        |
| 07     | Assessing Network Vulnerabilities   | 50–120        |
| 08     | Managing IR & Communication         | 40–100        |
| 09     | Executing IR Plans                  | 45–110        |
| 10     | Analyzing Malicious Activity        | 55–130        |
| 11     | Automating Data Analysis            | 40–100        |
| 12     | Improving Processes with Automation | 35–90         |
| 13     | Assessing App Vulnerabilities       | 40–100        |
| 14     | Securing Applications               | 40–100        |
|        | **Estimated Total**                 | **~595–1480** |

*Modules 6, 7, 9, and 10 are weighted heavier because they map to the two largest exam domains (SecOps 34% and VulnMgmt 26%) and contain the highest density of testable specifics (frameworks, tools, indicators).*

## Example Cards (for reference)

### Example 1: Key Term Definition

**Front:**

```html
🛡️ What is <b style="color:#2874A6">SOAR</b> and what problem does it solve?
```

**Back:**

```html
<b style="color:#2874A6">Security Orchestration, Automation, and Response</b> — a platform that integrates disparate security tools, automates repetitive analyst workflows, and executes predefined response playbooks.<br><br>💡 Problem solved: SOC analysts drown in alert volume. SOAR takes the enrichment, triage, and containment steps that used to be manual and runs them in seconds via API integrations with EDR, SIEM, ticketing, IAM, and firewall tools.<br><br>Key traits:<br>• <b>Playbook-driven</b> — response workflows are codified, not ad-hoc<br>• <b>Integration-heavy</b> — relies on APIs, webhooks, and plug-ins to reach other tools<br>• <b>Metric-improving</b> — directly reduces MTTD and MTTR<br><br>🎯 <i>SOC Analyst Perspective: In a mature SOC, SOAR is what lets a 5-analyst team handle the alert volume of a 15-analyst team.</i>
```

**Tags:**

```
CySA004::Module12::Obj1.5::SOAR
```

---

### Example 2: Concept Distinction

**Front:**

```html
🔍 What is the difference between an <b style="color:#2874A6">IDS</b> and an <b style="color:#2874A6">IPS</b>?
```

**Back:**

```html
<div style="background:rgba(128,128,128,0.15); padding:8px; border-radius:4px;">• <b style="color:#2874A6">IDS</b> (Intrusion Detection System): <b>Passively monitors</b> traffic (typically via a SPAN port or network tap) and <b>generates alerts</b> when suspicious patterns are matched. Does <b>NOT</b> block traffic.<br><br>• <b style="color:#2874A6">IPS</b> (Intrusion Prevention System): Sits <b>inline</b> with the traffic flow and <b>actively blocks</b> traffic that matches signatures or anomaly rules. Can drop packets, reset connections, or reroute traffic.</div><br>💡 <i>Rule of thumb: IDS = detects and tells you. IPS = detects and stops it. IPS carries higher risk of false positives disrupting legitimate traffic, so tuning is critical.</i><br><br>🎯 <i>SOC Analyst Perspective: Snort and Suricata can operate in either mode depending on deployment; Zeek is fundamentally a network-monitoring/analysis tool, not a blocking device.</i>
```

**Tags:**

```
CySA004::Module10::Obj1.3::IDSvsIPS
```

---

### Example 3: "Which Tool" Scenario

**Front:**

```html
🧪 An analyst finds a suspicious binary on a compromised host and wants to determine what functionality it exhibits <b style="color:#2874A6">without executing it in the production environment</b>. The analyst needs both static and dynamic analysis in an isolated environment that captures network calls, file writes, registry changes, and API calls.<br><br>Which tool is <b style="color:#2874A6">MOST appropriate</b>?<br><br>A) VirusTotal<br>B) Strings<br>C) Cuckoo Sandbox<br>D) YARA
```

**Back:**

```html
✅ <b style="color:#27AE60">C) Cuckoo Sandbox</b><br><br>Cuckoo Sandbox is an <b style="color:#2874A6">automated malware analysis sandbox</b> that detonates a sample in an isolated VM and produces a report covering file system changes, registry modifications, network traffic (PCAPs), API calls, and process behavior.<br><br>❌ Why not the others:<br>• <b>VirusTotal</b> — hash lookup and multi-engine AV scanning; returns known-bad reputation but doesn't perform full behavioral analysis of a novel sample<br>• <b>Strings</b> — extracts printable ASCII/Unicode strings from a binary; useful for finding embedded URLs or commands but is <b>static-only</b> and gives no runtime behavior<br>• <b>YARA</b> — pattern-matching rule engine used to <b>identify or classify</b> samples by byte/string signatures; does not execute the sample<br><br>
```

**Tags:**

```
CySA004::Module10::Obj1.3::Sandboxing
```

---

### Example 4: Framework Structure

**Front:**

```html
🧩 List the <b style="color:#2874A6">seven phases of the Cyber Kill Chain</b> in order, with a one-line description of each.
```

**Back:**

```html
<div style="background:rgba(128,128,128,0.15); padding:8px; border-radius:4px;">1. <b style="color:#2874A6">Reconnaissance</b> — adversary identifies and researches targets (OSINT, scanning)<br>2. <b style="color:#2874A6">Weaponization</b> — coupling exploit with payload into a deliverable artifact<br>3. <b style="color:#2874A6">Delivery</b> — transmission of the weaponized payload (phishing, USB, watering hole)<br>4. <b style="color:#2874A6">Exploitation</b> — triggering vulnerability to execute code on the target<br>5. <b style="color:#2874A6">Installation</b> — establishing persistence (backdoor, service, scheduled task)<br>6. <b style="color:#2874A6">Command & Control (C2)</b> — beaconing out to attacker infrastructure for remote control<br>7. <b style="color:#2874A6">Actions on Objectives</b> — the adversary's actual goal: exfiltration, encryption for ransom, lateral movement, destruction</div><br>💡 Mnemonic: <b>R</b>eady <b>W</b>arriors <b>D</b>eploy <b>E</b>xtreme <b>I</b>nsults <b>C</b>ausing <b>A</b>nger<br><br>⚠️ Contrast with MITRE ATT&CK: Kill Chain is linear and pre-2015 in framing; ATT&CK is a matrix of tactics and techniques that reflects <b>how modern adversaries actually operate</b>, including techniques used repeatedly across phases (e.g., Defense Evasion, Lateral Movement).
```

**Tags:**

```
CySA004::Module09::Obj3.1::CyberKillChain
```

---

### Example 5: Log/Output Interpretation (PBQ-style)

**Front:**

```html
🔍 An analyst captures the following Nmap command output header. What scan type was performed and what does it tell you about how it interacts with the target?<br><br><code style="color:#E74C3C; background:rgba(128,128,128,0.1); padding:2px 4px; border-radius:3px;">nmap -sS -Pn -p 1-1000 192.168.10.5</code>
```

**Back:**

```html
<b style="color:#2874A6">TCP SYN scan (a.k.a. "half-open" or "stealth" scan)</b> against ports 1–1000 with host discovery disabled.<br><br>Flag breakdown:<br>• <code style="color:#E74C3C;">-sS</code> — <b>SYN scan</b>: sends a SYN, and if the target replies SYN/ACK the port is open; the scanner then sends RST rather than completing the handshake (never establishes a full connection)<br>• <code style="color:#E74C3C;">-Pn</code> — <b>skip host discovery</b>; treats the host as up and scans regardless (useful when ICMP is blocked)<br>• <code style="color:#E74C3C;">-p 1-1000</code> — scan only ports 1 through 1000<br><br>💡 Because the three-way handshake is never completed, SYN scans are less likely to appear in application-layer logs than a full-connect scan (<code style="color:#E74C3C;">-sT</code>) — but they are <b>readily detected by IDS/IPS</b> looking for SYN-without-ACK patterns.<br><br>🎯 <i>SOC Analyst Perspective: On the exam and on the job, "stealth scan" almost always means <code style="color:#E74C3C;">-sS</code>. Requires raw sockets, hence root/administrator privileges.</i>
```

**Tags:**

```
CySA004::Module07::Obj2.2::NmapScanTypes
```

---

### Example 6: Indicator Recognition

**Front:**

```html
🚨 A privileged user account authenticates successfully from an office in <b>Denver, CO at 14:00 UTC</b>, then authenticates successfully from <b>Kuala Lumpur, Malaysia at 14:35 UTC</b>. No VPN or bastion host is in use.<br><br>Which <b style="color:#2874A6">identity-based indicator</b> does this represent, and what is the appropriate initial response?
```

**Back:**

```html
✅ <b style="color:#27AE60">Impossible travel</b> (Objective 1.2 — identity-based indicators).<br><br>Denver → Kuala Lumpur is roughly 9,500 miles apart; commercial travel takes ~20+ hours. A 35-minute gap between successful authentications is physically impossible.<br><br>🚦 <b>Initial response</b>:<br>1. <b>Contain</b>: disable the account or force MFA re-challenge/session revocation immediately<br>2. <b>Investigate</b>: pull authentication logs, source IP reputation (WHOIS, AbuseIPDB, GeoIP), and any post-authentication actions (privilege changes, data access, lateral connections)<br>3. <b>Escalate</b> per the IR plan — this pattern often indicates <b>IAM account compromise</b> (credential theft, session token replay, or a valid federated-identity abuse)<br><br>⚠️ Watch for false positives: corporate VPN concentrators, mobile carrier gateways, and cloud NAT gateways can produce apparent geographic jumps that are benign — but the exam scenario should tell you if that's ruled out.
```

**Tags:**

```
CySA004::Module10::Obj1.2::ImpossibleTravel
```

---

### Example 7: Two-Axis Classification

**Front:**

```html
🛡️ Classify each of the following controls by both <b style="color:#2874A6">control type</b> (Administrative / Technical / Physical) and <b style="color:#2874A6">control function</b> (Preventative / Detective / Responsive / Corrective).<br><br>A) Security awareness training<br>B) Host-based IDS<br>C) Backup restoration procedure<br>D) Data-center mantrap<br>E) Firewall ACL
```

**Back:**

```html
<div style="background:rgba(128,128,128,0.15); padding:8px; border-radius:4px;">A) <b>Security awareness training</b> → Administrative + Preventative (reduces likelihood of phishing/social-engineering success)<br><br>B) <b>Host-based IDS</b> → Technical + Detective (alerts on suspicious activity; does not block it)<br><br>C) <b>Backup restoration procedure</b> → Technical (or Administrative depending on framing) + Corrective (restores state after an incident)<br><br>D) <b>Data-center mantrap</b> → Physical + Preventative (physically stops tailgating)<br><br>E) <b>Firewall ACL</b> → Technical + Preventative (blocks disallowed traffic before it reaches the target)</div><br>💡 The exam often gives a scenario and asks for <b>both axes</b>. Memorize the definitions:<br>• <b>Preventative</b> — stops the event from occurring<br>• <b>Detective</b> — identifies the event has occurred/is occurring<br>• <b>Responsive</b> — reacts to and contains an active event<br>• <b>Corrective</b> — restores normal state after the event<br><br>🔗 <i>BSCSIA Cross-Reference: This two-axis control classification also appears in your Security+ material and in NIST SP 800-53 control catalog structure.</i>
```

**Tags:**

```
CySA004::Module02::Obj2.4::ControlClassification
```

---

### Example 8: Regex / Rule Reading

**Front:**

```html
🔍 What does the following Snort-style signature match, and what attack category does it target?<br><br><code style="color:#E74C3C; background:rgba(128,128,128,0.1); padding:2px 4px; border-radius:3px;">alert tcp any any -> $HOME_NET 80 (msg:"SQLi UNION SELECT"; content:"union"; nocase; content:"select"; nocase; distance:0; sid:1000001;)</code>
```

**Back:**

```html
Matches inbound TCP traffic to any host on the internal network (<code style="color:#E74C3C;">$HOME_NET</code>) destined for port 80 (HTTP), where the payload contains the words <code style="color:#E74C3C;">union</code> and <code style="color:#E74C3C;">select</code> (case-insensitive, with <code style="color:#E74C3C;">select</code> appearing at or after <code style="color:#E74C3C;">union</code>).<br><br>Attack category: <b style="color:#2874A6">SQL injection (SQLi)</b> — specifically the classic UNION-based technique used to append attacker-controlled query results onto a legitimate query's output.<br><br>Rule breakdown:<br>• <code style="color:#E74C3C;">alert tcp any any -> $HOME_NET 80</code> — action, protocol, source, destination<br>• <code style="color:#E74C3C;">msg:"..."</code> — human-readable alert label<br>• <code style="color:#E74C3C;">content:"union"; nocase;</code> — payload must contain "union" (any case)<br>• <code style="color:#E74C3C;">content:"select"; nocase; distance:0;</code> — must also contain "select" (any case), appearing at or after "union"<br>• <code style="color:#E74C3C;">sid:1000001;</code> — unique signature ID<br><br>⚠️ Weakness: this signature is trivially bypassed with encoding, comment obfuscation (<code style="color:#E74C3C;">UN/**/ION</code>), or case-fragmentation of the keywords — real SQLi detection needs WAF-level parsing or DB query anomaly detection.<br><br>🎯 <i>SOC Analyst Perspective: You will see Snort/Suricata syntax on PBQs. The <code style="color:#E74C3C;">distance:0</code> modifier is a common exam trap — it means "at or after the previous content match," not "immediately adjacent."</i>
```

**Tags:**

```
CySA004::Module10::Obj1.3::SnortRules
```

---

### Example 9: CVSS Metric Recognition

**Front:**

```html
🚦 A vulnerability has this CVSS v3.1 Base vector:<br><br><code style="color:#E74C3C; background:rgba(128,128,128,0.1); padding:2px 4px; border-radius:3px;">CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:H/A:H</code><br><br>What does each metric mean, and what does the overall vector tell you about exploit conditions and impact?
```

**Back:**

```html
<div style="background:rgba(128,128,128,0.15); padding:8px; border-radius:4px;"><b>Base metrics:</b><br>• <code style="color:#E74C3C;">AV:N</code> — <b>Attack Vector: Network</b> — exploitable remotely across the network<br>• <code style="color:#E74C3C;">AC:L</code> — <b>Attack Complexity: Low</b> — no special conditions required<br>• <code style="color:#E74C3C;">PR:N</code> — <b>Privileges Required: None</b> — attacker needs no prior access<br>• <code style="color:#E74C3C;">UI:N</code> — <b>User Interaction: None</b> — no victim action required<br>• <code style="color:#E74C3C;">S:U</code> — <b>Scope: Unchanged</b> — exploit does not affect resources outside the vulnerable component's authority<br>• <code style="color:#E74C3C;">C:H</code> — <b>Confidentiality Impact: High</b><br>• <code style="color:#E74C3C;">I:H</code> — <b>Integrity Impact: High</b><br>• <code style="color:#E74C3C;">A:H</code> — <b>Availability Impact: High</b></div><br>💡 This is a <b style="color:#C0392B">critical, wormable-class vulnerability</b> — remotely exploitable, no privileges, no user interaction, full CIA impact. Real-world equivalents: EternalBlue (MS17-010), Log4Shell (CVE-2021-44228).<br><br>🎯 <i>SOC Analyst Perspective: This vector pattern is your "drop everything" signal. Combined with a high EPSS score (probability of active exploitation), it moves to the top of the remediation queue regardless of asset context.</i>
```

**Tags:**

```
CySA004::Module07::Obj2.3::CVSSBaseMetrics
```

---

### Example 10: Reporting Metric Distinction

**Front:**

```html
⏱️ Distinguish the following incident-response metrics: <b style="color:#2874A6">MTTD</b>, <b style="color:#2874A6">MTTR (respond)</b>, <b style="color:#2874A6">MTTR (remediate)</b>, and <b style="color:#2874A6">MTTC</b>.
```

**Back:**

```html
<div style="background:rgba(128,128,128,0.15); padding:8px; border-radius:4px;">• <b style="color:#2874A6">MTTD — Mean Time to Detect</b>: avg time between event occurrence (compromise, alert-worthy activity) and the SOC identifying it. Measures <b>detection maturity</b>.<br><br>• <b style="color:#2874A6">MTTR — Mean Time to Respond</b>: avg time between detection and first meaningful response action (triage, containment initiated). Measures <b>response readiness</b>.<br><br>• <b style="color:#2874A6">MTTR — Mean Time to Remediate</b>: avg time between detection and full remediation (root cause addressed, systems restored). Measures <b>end-to-end IR effectiveness</b>. <b>Note</b>: "MTTR" is overloaded — <b>read the context</b>.<br><br>• <b style="color:#2874A6">MTTC — Mean Time to Close</b>: avg time from incident opening to formal closure in the ticketing/case-management system. Measures <b>administrative throughput</b>, not just technical resolution.</div><br>⚠️ The exam <b>will</b> exploit the "MTTR" ambiguity. If a question says "mean time to respond," it means initial response action. If it says "mean time to remediate," it means full fix. Do not conflate them.<br><br>🎯 <i>SOC Analyst Perspective: MTTD is usually the most-scrutinized KPI in a SOC scorecard because it's a proxy for detection coverage — dwell time is what boards and auditors ask about.</i>
```

**Tags:**

```
CySA004::Module08::Obj4.2::IRMetrics
```

---

Please create the complete tab-separated file ready for Anki import, one module at a time.
