# Abbe Kibe

SOC and detection engineering · Python, PowerShell, Sigma · Nairobi, Kenya

I write detections for attacker behaviour, test them against logs, and document where they break. Most of what I build sits between software engineering and security operations: small, tested tools that turn a log file into an answer a SOC analyst can act on.



## Start here

**[Detection-Lab](https://github.com/Abbe11/Detection-Lab)**
Five detections, each with a PowerShell detector, a Sigma rule, a sample log and a Pester test that runs in GitHub Actions:
- SSH brute force, including whether the attacker eventually got in (T1110)
- A new account created with root privileges, a common backdoor (T1136)
- Web attacks such as SQL injection and path traversal (T1190)
- Impossible travel: the same account signing in from two countries too quickly to be the same person (T1078)
- A reverse shell or crypto miner started after a break-in (T1059, T1496)

**[sigma-detection-lab](https://github.com/Abbe11/sigma-detection-lab)**
Four Sigma rules (LSASS credential dumping, security log cleared, svchost spawning cmd, whoami discovery) tested against real Windows EVTX attack recordings with a Python harness.

**[offensive-lab](https://github.com/Abbe11/offensive-lab)**
HackTheBox write-ups: recon, foothold, why it worked and how a defender would stop it, for every box.

**[nexusbank-pentest-lab](https://github.com/Abbe11/nexusbank-pentest-lab)**
A deliberately vulnerable Flask banking app that I attacked from Kali (Nmap, Nikto, SQLMap, Hydra, Metasploit), plus a small detection engine that records what those attacks look like from the defender's side.

## Backend work

- **[inventory-management-system](https://github.com/Abbe11/inventory-management-system)**: Flask REST API and CLI with OpenFoodFacts enrichment and a mocked pytest suite
- **[workout-tracker-api](https://github.com/Abbe11/workout-tracker-api)**: Flask API with session auth, bcrypt password hashing and per-user data ownership
- **[secureops-cli](https://github.com/Abbe11/secureops-cli)**: OOP command-line tracker with JSON persistence and pytest

## Security tools

- **[netprobe](https://github.com/Abbe11/netprobe)**: explains IP subnets and MAC addresses in plain English, with a connection doctor. Pure standard library, 14 tests
- **[sitecheck](https://github.com/Abbe11/sitecheck)**: non-invasive website security header checker that grades a site and writes a fix-it report
- **[scam-spotter-agent](https://github.com/Abbe11/scam-spotter-agent)**: small LLM agent that flags scam SMS using a tool-calling loop

## In progress

**[sentinel](https://github.com/Abbe11/sentinel)**: an early-stage Java / Spring Boot service for FHIR R4 health insurance claims, aimed at the platforms used in Saudi Arabia (NPHIES) and the EU (EHDS). It validates claims against FHIR R4, runs NPHIES-style denial rules (missing preauthorization, totals that do not add up) and writes a PHI-safe audit log. More rules and an RBAC and encryption layer are next.

## Tools I have actually used

- **Languages:** Python, PowerShell, SQL, JavaScript
- **Detection:** Sigma, MITRE ATT&CK, Pester, pytest, GitHub Actions
- **Offensive, lab only:** Nmap, Nikto, SQLMap, Hydra, Metasploit, Kali Linux
- **Backend:** Flask, SQLAlchemy, Marshmallow, React
- **Currently studying:** TryHackMe SOC Level 1

## Contact

abbekibe2@gmail.com

Looking for SOC analyst, junior detection engineering and Python backend roles. Open to remote work, Kenya, and relocation to the UAE or Europe.
