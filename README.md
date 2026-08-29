# CySA+ CS0-004 V4 Study Materials

Personal study materials for the **CompTIA Cybersecurity Analyst (CySA+) CS0-004 V4** certification exam.

I originally built all of this for myself while studying for the exam. I'm making it available here in case anyone else finds it useful.

## 🌐 Study Site

### **[Open the CySA+ CS0-004 Study Materials](https://ugl13rth4nu.github.io/CySA-004/)**

The GitHub Pages site is now the easiest way to get to everything in this repo. From there you can:

* Launch any of the interactive HTML trainers
* Download the Anki deck
* Browse some of the visual study references
* Search the available trainers by topic

The trainers open in new tabs, so you can leave the main page open and bounce between them.

---

## What's Here

### Interactive HTML Trainers

These are standalone browser-based study trainers for the CySA+ CS0-004 V4 exam. Each is a single self-contained HTML file — no install, no dependencies, and no data leaves the browser.

They work best on laptop/desktop. Most also work on an iPad/tablet using either drag-and-drop or tap once to select / tap the destination to place. I would **not** recommend trying to use most of them on a phone-sized screen.

I built these to help in my weak areas. They're meant to help create a kind of **"muscle-memory" effect**.

As a person who does **not** have the multi-year experience that the exam objectives say the desired candidate should have ("4 years of hands-on experience in a SOC analyst (level 2) or a vulnerability analyst role"), I needed something that would get my hands and brain used to seeing certain terms, commands, relationships, processes, and patterns over and over again.

For me, these help correlate things and burn away the unfamiliarity.

Current trainers include:

* **SOC Roles** — SOC job roles and the 6-step SOC incident lifecycle
* **File Systems** — Windows and Linux file systems, registry keys/hives, system directories, system processes, and cross-platform recognition
* **Nmap** — scan techniques, host discovery, target specification, service/OS detection, NSE, port states, timing/evasion, command construction, typed CLI practice, and output interpretation
* **Processes** — Windows and Linux expected process lineage, suspicious parent/child relationships, LOLBin abuse, path anomalies, masquerading, Event 4688, and Sysmon Event 1
* **OT / ICS / IIoT** — industrial protocols, ICS components, SCADA vs. DCS, vendor/system relationships, and OT security platforms
* **CVSS 4.0** — Base, Threat, Environmental, and Supplemental metrics; vector reading; scoring terminology; CVSS vs. EPSS; and severity bands
* **Wireshark** — display filters, typed filter syntax, capture vs. display filters, packet colors, and analysis features
* **SNORT** — IDS vs. IPS, rule syntax, building and reading rules, alert output, operating modes, and Snort/Suricata/Zeek recognition
* **Frameworks** — Cyber Kill Chain, Diamond Model, Pyramid of Pain, STRIDE, and STIX/TAXII
* **Logging** — Windows Event IDs, logon types, Syslog/Cisco severity, Windows event levels, logging concepts, and correlation scenarios
* **External Tools** — recognition of external cybersecurity tools, services, and software and what they are actually used for

Rather than duplicate every launch link here, the current trainers can be opened from the **[main study site](https://ugl13rth4nu.github.io/CySA-004/)**.

---

## Anki Deck

The repo also contains my custom CySA+ CS0-004 Anki deck:

**`ScottsFreshDeckCySA-004.apkg`**

The cards come from two parallel workflows:

* **Textbook cards** — broad concept coverage from CompTIA CertMaster Perform courseware: definitions, framework structures, tool identification, log interpretation, indicator recognition, etc.
* **Quiz cards** — quiz questions with additional notes and reasoning added during review

All cards use custom HTML styling with dark-mode-compatible backgrounds for AnkiMobile.

The tag hierarchy begins with `CySA004`, then branches into module-hierarchical tags for textbook cards and domain-hierarchical tags for quiz cards.

### Importing the deck

1. Download the `.apkg` from this repo or from the [study site](https://ugl13rth4nu.github.io/CySA-004/)
2. In Anki Desktop: **File → Import**
3. Select the `.apkg`
4. Sync to AnkiWeb if you use AnkiMobile or AnkiDroid

I made the deck for me, based on what I felt I needed to learn and remember. Anyone else using it may have different weak areas and should adjust accordingly.

---

## Visual Study References

The `images` folder contains some graphics I created while studying, including:

* Cyber Kill Chain
* Diamond Model
* Pyramid of Pain
* STRIDE
* Admiralty Scale
* Ishikawa diagram
* Bash loop logic
* PowerShell loop logic
* Python loop logic
* Generic loop logic

Some of these are also displayed directly on the main study site.

---

## Resources I Used

This repo isn't based on one single source. I have been studying the material from several different directions:

* **Instructor-led CySA+ 004 training — NOVA Workforce**

  * Grants may be available that significantly reduce tuition
  * If you choose to go this route, look for classes conducted by **Professor Nick Pierce**. He's one of the best instructors I've had for tech/cybersecurity-related classes, even though the classes I've taken with him were conducted through Zoom rather than physically in a classroom.

* **CompTIA CertMaster Perform — CySA+ 004**

  * Course textbook
  * Labs
  * PBQs
  * Practice quizzes for each module
  * Mock exam

* **CompTIA CertMaster Practice**

  * Obtained through my WGU cybersecurity program

* **Jason Dion — CySA+ 004 on Udemy**

  * Also available to me through WGU

* **Sybex CySA+ CS0-004 Study Guide**

* **Anki**

  * Flashcards created by me, for me

* **HTML Trainers**

  * Created by me, for me

* **ChatGPT and Claude**

  * Used extensively in developing, reviewing, arguing about, correcting, and expanding the study material

**If you live in the Northern Virginia area, I highly recommend the NOVA Workforce program. Their instructors have all been top notch, and the program and material it provides have been excellent.**

---

## Repository Structure

```text
CySA-004/
│
├── index.html
│   └── Main GitHub Pages study site
│
├── README.md
│   └── What you're reading now
│
├── ScottsFreshDeckCySA-004.apkg
│   └── Anki deck
│
├── Trainers/
│   └── Standalone interactive HTML trainers
│
├── images/
│   └── Visual study references
│
└── AI_Prompts/
    └── AI prompts/instructions used in creating some of the material
```

---

## Disclaimer

These are personal study materials created for my own exam prep.

I am not affiliated with CompTIA, and this repo is not endorsed by CompTIA or any of the other companies or organizations referenced in it.

A lot of this material was produced or refined in collaboration with **ChatGPT and Claude**. I try to verify what goes into it, but AI can be wrong, I can be wrong, and the source material itself can occasionally be unclear or contradictory.

So: **verify things for yourself.**

As with everything else on the internet, information eventually goes stale and potentially bad.

If you come across this repo at some point in the future and the **CySA+ CS0-004 exam is no longer available**, you should probably move on to fresher, more relevant resources instead of relying on an old certification study repo.

Original creation: **July/August 2026**

---

## License

See [LICENSE](LICENSE).
