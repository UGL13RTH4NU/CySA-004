# CySA+ CS0-004 V4 Study Materials

Personal study materials for the **CompTIA Cybersecurity Analyst (CySA+) CS0-004 V4** certification exam.

I originally built all of this for myself while studying for the exam. I'm making it available here in case anyone else finds it useful.

## 🌐 Study Site

### **[Open the CySA+ CS0-004 Study Materials](https://ugl13rth4nu.github.io/CySA-004/)**

The GitHub Pages site is now the easiest way to get to everything in this repo. From there you can:

* Launch any of the interactive HTML trainers
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

The current trainers can be opened from the **[main study site](https://ugl13rth4nu.github.io/CySA-004/)**.

---

## Anki Deck

The repo contains my custom CySA+ CS0-004 Anki deck:

**`ScottsFreshDeckCySA-004.apkg`**

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

Below our the primary resources I used to study for the CySA+ 004 certification exam:

- **Instructor lead training (CySA+ 004)** - NVCC Workforce (grants available for reduced tuition) Workforce
   - If you choose to go this route, look for classes conducted by Professor Nick Pierce - he's one of the best in-person (vis-a-vis Zoom) instructors I've had for Tech/ Cybersecurity related classes
- **CertMaster Perform (CySA+ 004)** - obtained through NVCC Workforce program, but purchasable directly from CompTIA
course textbook
   - labs
   - PBQ's
   - Practice Quizzes for each module
   - Mock Exam
- **CertMaster Practice (CySA+ 003)** - obtained via WGU BSCSIA, but purchasable directly from CompTIA
- **Udemy**, Jason Dion (CySA+ 004) - obtained via WGU BSCSIA, but purchasable directly from Udemy
- **Anki flashcards**, free for desktop and Android - created by me, for me
- **HTML based Trainers**, free - created by me, for me
- **ChatGPT** & **Claude** - $20 subscription model
- **Sybex Study Guide** (CySA+ 004) - Amazon

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

## Post-Exam Review and Notes

I successfully passed the CySA+ CS0-004 exam on September 3, 2026, with a score of **812**.

My primary after-exam impression is that the **CertMaster Perform material was more than adequate preparation for the exam**. The tools trainer also helped considerably with recognizing tools and distinguishing between tools with similar or overlapping capabilities.

I only had one question on the exam that made me think, *WTF(?)*. Beyond that, I believe the questions I got wrong generally fell into one of two categories: questions I failed to interpret in the manner CompTIA intended, or questions where I had forgotten enough of the relevant material that I could no longer confidently distinguish the best answer from the other plausible choices or properly eliminate the incorrect ones.

Overall, I felt well prepared for the exam and did not come away believing that there were major areas of material I had simply never encountered.

I feel like the materials that prepared me best were the live instruction via Zoom, which provided my initial coverage of the CertMaster Perform material; the CertMaster Perform textbook and labs; my Anki flashcards; several of the HTML trainers I created to reinforce exposure to areas where I wanted additional repetition and recognition practice; and the Dion Training CySA+ 004 videos on Udemy. I only made it about halfway through the Dion course before taking the exam, but I found the portion I completed very useful and thought it contained a lot of good information.

---

## License

See [LICENSE](LICENSE).
