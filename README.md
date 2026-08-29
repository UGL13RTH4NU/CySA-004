# CySA+ CS0-004 V4 Study Materials

Personal study materials for the CompTIA Cybersecurity Analyst (CySA+) CS0-004 V4 certification exam.

## Contents

### Anki Deck

Custom Anki deck covering the CS0-004 V4 exam objectives. Cards are built from two parallel workflows:

- **Textbook cards** — broad concept coverage from CompTIA CertMaster Perform courseware (definitions, framework structures, tool identification, log interpretation, indicator recognition)
- **Quiz cards** — quiz questions with custom card notes from Claude Opus 4.7

All cards use custom HTML styling with dark-mode-compatible `rgba()` backgrounds for AnkiMobile.

Tag hierarchy: All cards prefixed with `CySA004`, then module-hierarchical (textbook cards) or domain-hierarchical (quiz cards).


##### Usage

**Importing the Anki deck**

1. Download the `.apkg` file from this repo
2. In Anki desktop: File → Import → select the file
3. Sync to AnkiWeb if you use AnkiMobile or AnkiDroid


---

### Interactive HTML Trainers

Web-based practice trainers hosted via GitHub Pages. These work best on laptop/desktop. Most also work with iPad/tablet using tap touch to select and place.


| Module / Lesson | Trainer | Coverage |
| --- | --- | --- |
| Module 1 | [SOC Roles](https://ugl13rth4nu.github.io/CySA-004/Trainers/Soc_Roles.html) | SOC job roles and the 6-step SOC incident lifecycle |
| Module 3 | [File Systems](https://ugl13rth4nu.github.io/CySA-004/Trainers/File_Systems.html) | Windows file system, registry root keys, registry hive files, Windows system processes, Linux standard subdirectories, Linux key directories, Linux system processes, cross-platform classification (8 modes) |
| Module 3 | [Nmap](https://ugl13rth4nu.github.io/CySA-004/Trainers/Nmap.html) | CertMaster high-yield options, scan techniques (-sS/-sT/-sU/-sA/-sN/-sF/-sX/-sW/-sM/-sI), host discovery and target specification, service/OS/NSE/output options, six Nmap port states, timing and evasion, function-category classification, command builder, scenario MCQ, output interpretation (10 modes) |
| Module 3 | [Processes](https://ugl13rth4nu.github.io/CySA-004/Trainers/Processes.html) | Windows expected process lineage (smss, wininit, services, lsass, svchost, csrss, winlogon, explorer), Linux expected lineage (systemd/init, sshd, cron, kthreadd, udevd, shells), Windows-vs-Linux platform sort, Windows expected-vs-suspicious relationships (LOLBin abuse, Office-to-shell, path/parent anomalies), Linux expected-vs-suspicious relationships (/tmp, /dev/shm, malicious systemd units, masquerading), exam-style triage MCQs covering P-P-P-S evaluation and 4688/Sysmon Event 1 (6 modes) |
| Lesson 4C | [OT / ICS / IIoT](https://ugl13rth4nu.github.io/CySA-004/Trainers/OT.html) | ICS protocol correlation (Modbus, DNP3, PROFINET, PROFIBUS, EtherNet/IP), protocol-to-system/vendor mapping, ICS components, SCADA-vs-DCS sort, OT security platforms (Dragos, Nozomi Guardian, Claroty CTD), platform discriminators, exam-style scenarios |
| Module 7 | [CVSS 4.0](https://ugl13rth4nu.github.io/CySA-004/Trainers/CVSS_4-0.html) | Base vector anatomy, full canonical vector order (Base → Threat → Environmental → Supplemental), Threat + Environmental metrics, Supplemental metrics, metric-group buckets, Base Exploitability vs Impact split, CVSS-B/BT/BE/BTE nomenclature, vector reading, CVSS vs EPSS, qualitative severity bands (10 modes) |
| Module 10 | [Wireshark](https://ugl13rth4nu.github.io/CySA-004/Trainers/Wireshark.html) | description to be added |
| Module 10 | [SNORT](https://ugl13rth4nu.github.io/CySA-004/Trainers/SNORT.html) | description to be added |
| Cross-module | [Frameworks](https://ugl13rth4nu.github.io/CySA-004/Trainers/Frameworks.html) | Cyber Kill Chain (7 stages), Diamond Model (4 vertices), Pyramid of Pain (6 levels), STRIDE, STIX/TAXII — each with match, order/property, cue, and MCQ modes |
| Cross-module | [Logging](https://ugl13rth4nu.github.io/CySA-004/Trainers/Logging.html) | Priority Windows Event IDs (meaning↔ID both directions), additional high-yield Event IDs, Windows logon types, CertMaster log severity, Syslog/Cisco severity 0–7, Windows event levels 0–5, mixed-scheme severity drill, logging concepts, event correlation scenarios (10 modes) |
| Cross-module | [External Tools](https://ugl13rth4nu.github.io/CySA-004/Trainers/Tools.html) | External tool/service/software recognition with function-category filtering and scenario-to-tool matching (hard mode and exam-mix mode) |


These trainers emphasize pattern recognition and active recall, using repeated matching and categorization to build familiarity with how related concepts, tools, processes, and system artifacts fit together.

---

## Resources I Used:

- Instructor lead training (CySA+ 004) - NVCC Workforce (grants available for reduced tuition) [Workforce](https://www.nvcc.edu/academics/workforce/index.html)
  - If you choose to go this route, look for classes conducted by Professor Nick Pierce - he's one of the best in-person (vis-a-vis Zoom) instructors I've had for Tech/ Cybersecurity related classes 
- CertMaster Perform (CySA+ 004) - obtained through NVCC Workforce program, but purchasable directly from CompTIA
  - course textbook
  - labs
  - PBQ's
  - Practice Quizzes for each module
  - Mock Exam
- CertMaster Practice (CySA+ 003) - obtained via WGU BSCSIA, but purchasable directly from CompTIA
- Udemy, Jason Dion (CySA+ 004) - obtained via WGU BSCSIA, but purchasable directly from Udemy
- Anki flashcards, free for desktop and Android - created by me, for me
- HTML based Trainers, free - created by me, for me
- ChatGPT & Claude - $20 subscription model
- Sybex Study Guide (CySA+ 004) - Amazon

**If you live in the Northern Virginia area I highly recommend NVCC Workforce program. Their instructors have all been top notch; the program and material it provides is excellent.**

---

## Disclaimer

These are personal study materials created for my own exam prep. Content is derived from the CompTIA CS0-004 and was produced in collaboration with Claude Opus 4.7 and ChatGPT. All information in this repo should be verified by the user for accuracy.

As with everything on the internet, information eventually goes stale and potentially bad. If you come upon this Repo at a future date and the CySA+ 004 exam is no longer available, you should probably move on to fresher, more relevant resources.

Original creation date July/August 2026

---
