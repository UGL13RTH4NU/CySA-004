# CySA+ CS0-004 Interactive Trainers

Standalone browser-based study trainers for the CompTIA Cybersecurity Analyst (CySA+) CS0-004 V4 exam. Each is a single self-contained HTML file — no install, no dependencies, no data leaves the browser. Open directly via the links below, or clone the repo to run locally.

I built these to help in my weak areas. They're meant to help build a 'muscle-memory' type effect. As a person who does **not** have the multi-year experience that the exam objectives state the desired candidate should have ("4 years of hands-on experience in a SOC analyst (level 2) or a vulnerability analyst role"), I needed something to get my hands and brain to recognize certain terms and patterns and how they fit together. For me, these help me correlate these things and burn away the unfamiliarity.


## Trainers by CertMaster module

| Module / Lesson | Trainer | Coverage |
| --- | --- | --- |
| Module 1 | [SOC Roles](https://ugl13rth4nu.github.io/CySA-004/Trainers/Soc_Roles.html) | SOC job roles and the 6-step SOC incident lifecycle |
| Module 3 | [File Systems](https://ugl13rth4nu.github.io/CySA-004/Trainers/File_Systems.html) | Windows file system, registry root keys, registry hive files, Windows system processes, Linux standard subdirectories, Linux key directories, Linux system processes, cross-platform classification (8 modes) |
| Module 3 | [Nmap](https://ugl13rth4nu.github.io/CySA-004/Trainers/Nmap.html) | CertMaster high-yield options, scan techniques (-sS/-sT/-sU/-sA/-sN/-sF/-sX/-sW/-sM/-sI), host discovery and target specification, service/OS/NSE/output options, six Nmap port states, timing and evasion, function-category classification, command builder, scenario MCQ, output interpretation (10 modes) |
| Module 3 | [Processes](https://ugl13rth4nu.github.io/CySA-004/Trainers/Processes.html) | Windows expected process lineage (smss, wininit, services, lsass, svchost, csrss, winlogon, explorer), Linux expected lineage (systemd/init, sshd, cron, kthreadd, udevd, shells), Windows-vs-Linux platform sort, Windows expected-vs-suspicious relationships (LOLBin abuse, Office-to-shell, path/parent anomalies), Linux expected-vs-suspicious relationships (/tmp, /dev/shm, malicious systemd units, masquerading), exam-style triage MCQs covering P-P-P-S evaluation and 4688/Sysmon Event 1 (6 modes) |
| Lesson 4C | [OT / ICS / IIoT](https://ugl13rth4nu.github.io/CySA-004/Trainers/OT.html) | ICS protocol correlation (Modbus, DNP3, PROFINET, PROFIBUS, EtherNet/IP), protocol-to-system/vendor mapping, ICS components, SCADA-vs-DCS sort, OT security platforms (Dragos, Nozomi Guardian, Claroty CTD), platform discriminators, exam-style scenarios |
| Module 7 | [CVSS 4.0](https://ugl13rth4nu.github.io/CySA-004/Trainers/CVSS_4-0.html) | Base vector anatomy, full canonical vector order (Base → Threat → Environmental → Supplemental), Threat + Environmental metrics, Supplemental metrics, metric-group buckets, Base Exploitability vs Impact split, CVSS-B/BT/BE/BTE nomenclature, vector reading, CVSS vs EPSS, qualitative severity bands (10 modes) |
| Module 10 | [Wireshark](https://ugl13rth4nu.github.io/CySA-004/Trainers/Wireshark.html) | description to be added |
| Module 10 | [Snort](https://ugl13rth4nu.github.io/CySA-004/Trainers/SNORT.html) | description to be added |
| Cross-module | [Frameworks](https://ugl13rth4nu.github.io/CySA-004/Trainers/Frameworks.html) | Cyber Kill Chain (7 stages), Diamond Model (4 vertices), Pyramid of Pain (6 levels), STRIDE, STIX/TAXII — each with match, order/property, cue, and MCQ modes |
| Cross-module | [Logging](https://ugl13rth4nu.github.io/CySA-004/Trainers/Logging.html) | Priority Windows Event IDs (meaning↔ID both directions), additional high-yield Event IDs, Windows logon types, CertMaster log severity, Syslog/Cisco severity 0–7, Windows event levels 0–5, mixed-scheme severity drill, logging concepts, event correlation scenarios (10 modes) |
| Cross-module | [External Tools](https://ugl13rth4nu.github.io/CySA-004/Trainers/Tools.html) | External tool/service/software recognition with function-category filtering and scenario-to-tool matching (hard mode and exam-mix mode) |


## Usage

Click any link above to open the trainer in your browser. Progress is not persisted between sessions — closing the tab resets state.



## Related

- Parent repo: [CySA-004](https://github.com/UGL13RTH4NU/CySA-004) — Anki decks and other study assets



## How I Study & Prepare for the Exam

IMO, these trainers should be used after and as a supplement to doing the following:

1. Reading the study material
2. Doing the practice labs
3. Practice Quizzes and Tests
4. Flashcards
5. These 'Trainers'


## Disclaimer

Not affiliated with CompTIA or any other organization. These 'trainers' were built for my personal use. Anyone else choosing to use them should check information for accuracy. 

Made in collaboration with ChatGPT and Claude Opus 4.7. July/August 2026.

