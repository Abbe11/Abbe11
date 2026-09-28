# Abbe Kibe

SOC and detection engineering · Python, PowerShell, Sigma · Nairobi, Kenya

I write detections for attacker behaviour, test them against logs, and document where they break. Most of what I build sits between software engineering and security operations: small, tested tools that turn a log file into an answer a SOC analyst can act on.

Previously a security systems intern at Briminets and an ICT support intern at the Youth Enterprise Development Fund.

## Start here

**[Detection-Lab](https://github.com/Abbe11/Detection-Lab)**
Four detections, each with a PowerShell detector, a Sigma rule, a sample log and a Pester test that runs in GitHub Actions:
- SSH brute force, including whether the attacker eventually got in (T1110)
- A new account created with root privileges, a common backdoor (T1136)
- Web attacks such as SQL injection and path traversal (T1190)
- Impossible travel: the same account signing in from two countries too quickly to be the same person (T1078)

**[sigma-detection-lab](https://github.com/Abbe11/sigma-detection-lab)**
Four Sigma rules (LSASS credential dumping, security log cleared, svchost spawning cmd, whoami discovery) tested against real Windows EVTX attack recordings with a Python harness.

**[nexusbank-pentest-lab](https://github.com/Abbe11/nexusbank-pentest-lab)**
A deliberately vulnerable Flask banking app that I attacked from Kali (Nmap, Nikto, SQLMap, Hydra, Metasploit), plus a small detection engine that records what those attacks look like from the defender's side.

## Backend work

- **[inventory-management-system](https://github.com/Abbe11/inventory-management-system)**: Flask REST API and CLI with OpenFoodFacts enrichment and a mocked pytest suite
- **[workout-tracker-api](https://github.com/Abbe11/workout-tracker-api)**: Flask API with session auth, bcrypt password hashing and per-user data ownership
- **[secureops-cli](https://github.com/Abbe11/secureops-cli)**: OOP command-line tracker with JSON persistence and pytest

## In progress

**[sentinel](https://github.com/Abbe11/sentinel)**: an early-stage Java / Spring Boot service for FHIR R4 health insurance claims, aimed at the platforms used in Saudi Arabia (NPHIES) and the EU (EHDS). Right now it parses claims and rejects anything that is not valid FHIR. Business-rule validation is next.

## Tools I have actually used

- **Languages:** Python, PowerShell, SQL, JavaScript
- **Detection:** Sigma, MITRE ATT&CK, Pester, pytest, GitHub Actions
- **Offensive, lab only:** Nmap, Nikto, SQLMap, Hydra, Metasploit, Kali Linux
- **Backend:** Flask, SQLAlchemy, Marshmallow, React
- **Currently studying:** TryHackMe SOC Level 1

## Contact

abbekibe2@gmail.com

Looking for SOC analyst, junior detection engineering and Python backend roles. Open to remote work, Kenya, and relocation to the UAE or Europe.
