# Abbe Kibe

**SOC analyst and detection engineer.** I build detections for real attacks, test them until they break, and fix what the testing finds.

Most of my work starts from something that actually happened that week, a new CVE or a campaign in the news, and ends with a detection, a test that proves it works, and an honest write-up of where it still falls short. I come from software engineering, so I treat detections like code: version controlled, tested on every push, and reviewed when they fail.

## Selected work

**[black-october-lab](https://github.com/Abbe11/black-october-lab)** · one attack, the full security lifecycle

When the PHP2Shell bugs (CVE-2026-109618, CVE-2026-109619) hit in October 2026, I took them through every stage a security team would. I inventoried my own machine and found an Intel AMT management interface listening that I didn't know existed. I ran the vulnerable PHP version in a locked-down Docker lab, applied the vendor's emergency mitigation and proved it worked against the patched release. Then I treated the lab as compromised: contained it without destroying evidence, investigated with file diffs, process lists and logs, and wrote a tabletop incident report and a blameless postmortem. The fixes it called for are shipped and covered by tests.

**[Detection-Lab](https://github.com/Abbe11/Detection-Lab)** · six detections, tested on every push

Each detection has a PowerShell detector, sample data and Pester tests running in GitHub Actions, and most have a Sigma rule.

| Detection | MITRE ATT&CK | What makes it interesting |
|---|---|---|
| SSH brute force | T1110 | Escalates to critical if the attacking IP later logs in successfully |
| New root account | T1136 | Single-event alert: one UID 0 backdoor is already a full compromise |
| Web attacks | T1190 | Tested against OWASP Juice Shop, which exposed two gaps sample logs had hidden |
| Impossible travel | T1078 | Includes a test proving a legitimate long-haul trip is not flagged |
| Post-exploitation | T1059, T1105, T1496 | Caught PHP2Shell activity without being written for it; testing found a missed curl download, now fixed |
| Stolen cloud app keys | T1078.004 | Based on the November 2026 ARTEX campaign. Written in PowerShell and KQL, with the KQL validated in Azure Data Explorer |

The stolen-key detection taught me the most. My first version learned "normal" from the same log it was checking, so when the attacker's sign-in came first, the attacker became normal. Fixing that poisoned baseline, and writing a test so it can't come back, is in the README.

**[leaked-key-lab](https://github.com/Abbe11/leaked-key-lab)** · stopping the leak before it happens

A secret scanner plus a git pre-commit hook that refuses any commit containing an API key or private key. Tuned to cut the false positives a naive search produces (a plain `sk-` search flags words like "risk-"), and checked with planted canary keys so an empty result can be trusted.

**[sigma-detection-lab](https://github.com/Abbe11/sigma-detection-lab)** · four Sigma rules (LSASS credential dumping, security log cleared, svchost spawning cmd, whoami discovery) tested against real Windows EVTX attack recordings with a Python harness.

**[offensive-lab](https://github.com/Abbe11/offensive-lab)** and **[nexusbank-pentest-lab](https://github.com/Abbe11/nexusbank-pentest-lab)** · the attacker's side. HackTheBox write-ups, and a deliberately vulnerable Flask banking app attacked from Kali, each paired with how a defender would detect or stop it.

## Engineering

- **[sentinel](https://github.com/Abbe11/sentinel)**: Java / Spring Boot service for FHIR R4 health insurance claims, aimed at Saudi Arabia's NPHIES platform. Validates claims, applies denial rules and keeps a PHI-safe audit log. In progress.
- **[inventory-management-system](https://github.com/Abbe11/inventory-management-system)**: Flask REST API and CLI with a mocked pytest suite
- **[workout-tracker-api](https://github.com/Abbe11/workout-tracker-api)**: Flask API with session auth, bcrypt hashing and per-user data ownership
- **[secureops-cli](https://github.com/Abbe11/secureops-cli)**, **[netprobe](https://github.com/Abbe11/netprobe)**, **[sitecheck](https://github.com/Abbe11/sitecheck)**, **[scam-spotter-agent](https://github.com/Abbe11/scam-spotter-agent)**: smaller tools for team tracking, network diagnostics, security header grading and scam SMS detection

## Toolkit

**Detection and response:** Sigma, KQL, MITRE ATT&CK, incident response (PICERL), log and process analysis
**Testing and automation:** Pester, pytest, GitHub Actions, git hooks
**Languages:** PowerShell, Python, SQL, Java, JavaScript
**Lab:** Docker, Kali Linux, Nmap, Nikto, SQLMap, Hydra, Metasploit (lab use only)

## Contact

abbekibe2@gmail.com · open to SOC analyst, junior detection engineering and security-focused backend roles, remote or on-site.
