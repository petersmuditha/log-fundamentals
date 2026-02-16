# 📁 Log Analysis Fundamentals

**A practical guide and portfolio of log analysis projects for aspiring SOC analysts.**

👋 Hi, I'm Muditha an aspiring  **Cybersecurity Technical Writer**.  
This repository is my learning journal and portfolio, where I document my journey in mastering log analysis, from basic Linux commands to advanced SIEM investigations, based on the **TryHackMe SOC Level 1 path**.

I believe that **good documentation is as important as good detection**. Here you'll find not just commands, but structured methodologies, real-world use cases (with fake data), and reusable templates that I've built to help others (and myself) respond faster and smarter.

---

## 🛠️ Skills & Tools (TryHackMe-aligned)

🔹 **Core Log Analysis:** Linux Logs (`/var/log/auth.log`, `/var/log/syslog`), Windows Event Logs (Security, Application, System)  
🔹 **SIEM Platforms:** Splunk (SPL), Elastic Stack (Kibana queries), QRadar (basic correlation)  
🔹 **Network Traffic Analysis:** Zeek logs, `tcpdump`, Wireshark, NetworkMiner  
🔹 **Threat Detection Frameworks:** MITRE ATT&CK, Cyber Kill Chain, Pyramid of Pain  
🔹 **Scripting for Automation:** Python (log parsing), Bash (grep/awk one-liners), PowerShell (event log queries)  
🔹 **Incident Response Workflow:** Triage, investigation, escalation, reporting

---

## 🧭 About This Repository

This repository is structured to reflect the core modules of the **TryHackMe SOC Level 1 path**, with practical projects for each area.

| Section | TryHackMe Module Reference | Description |
|---------|----------------------------|-------------|
| **🔍 Linux Commands** | Linux Fundamentals, Security Onion | Essential commands for navigating and analyzing logs on Linux systems. |
| **🪟 PowerShell Logs** | Windows Fundamentals, Windows Event Logs | Techniques for extracting and investigating Windows event logs. |
| **📊 SIEM Queries** | Core SOC Solutions (Splunk/Elastic) | Example queries for Splunk and ELK, with explanations of detection logic. |
| **🚨 Use Cases** | Phishing Analysis, Malware Traffic Analysis, SIEM Triage | Step-by-step walkthroughs of common SOC scenarios. |
| **📝 Investigation Templates** | SOC Team Internals, Reporting | Ready-to-use templates for documenting your findings. |
| **⚙️ Scripts** | Automation | Python, Bash, and PowerShell scripts to speed up log analysis. |

---

## 🚨 Projects & Use Cases (TryHackMe-based)

Here are the main projects I've built, directly inspired by TryHackMe rooms and modules. Each includes a detailed write-up, commands, and screenshots.

| Project | TryHackMe Room / Module | Tools Used | Status |
|--------|-------------------------|------------|--------|
| [**SSH Brute Force Detection**] | Linux Log Analysis, Splunk 101 | `grep`, `awk`, `sort`, `Splunk` | ✅ Complete |
| [**Phishing Email Investigation**] | Phishing Analysis | Email headers, `jq`, `Kibana` | ✅ Complete |
| [**Malware C2 Traffic Analysis**] | Malware Traffic Analysis | `tcpdump`, `Wireshark`, `Zeek` | ✅ Complete |
| [**Windows Event Log - Pass-the-Hash**] | Windows Event Logs, Active Directory | PowerShell, `Get-WinEvent`, Event ID 4624/4625 | ✅ Complete |
| [**Splunk Correlation Search**] | Core SOC Solutions (Splunk) | Splunk SPL, Lookups | ✅ Complete |

> 🔒 *All data used in these projects is 100% synthetic and generated in isolated lab environments (TryHackMe rooms, custom VMs). No real customer or company data is ever used.*

---

## 📚 What I'm Learning & Demonstrating

Through this repository, I aim to show:

- **Practical log analysis skills** across Linux, Windows, and SIEM platforms, as taught in TryHackMe.
- **Understanding of SOC workflows** — triage, investigation, escalation, and reporting.
- **Documentation discipline** — clear, structured, and useful writing that helps teams.
- **Automation mindset** — using scripts to reduce manual work.
- **Continuous learning** — I update this repo as I progress through TryHackMe and gain new skills.

---

## 💡 My Philosophy on Technical Writing

> *"I write for clarity and structure. I'm interested in how writing can influence behavior, simplify the complex, and shift how people understand security."*  
> — inspired by [ananichoumchoum](https://github.com/ananichoumchoum)

In cybersecurity, clear documentation saves time during incidents and ensures that knowledge isn't lost. Every project here is an exercise in making technical concepts accessible and actionable, just like the excellent walkthroughs on TryHackMe.

---

## 📬 Connect with Me

I'm actively looking for opportunities as a **Cybersecurity Technical Writer** or **Junior SOC Analyst**. If you have feedback on my work, want to collaborate, or know of an opportunity, I'd love to hear from you.

- Remote.com Link: [https://remote.com/jobs/account/profile]
- Email: petersmuditha@gmail.com

---

## ⚠️ Disclaimer

All data, logs, and scenarios in this repository are **fictional and generated in controlled lab environments** (TryHackMe rooms or custom VMs). They do not contain any sensitive information from real organizations or individuals. The purpose is purely educational and for portfolio demonstration.

---

Special thanks to **TryHackMe** for providing an incredible hands-on learning platform that makes cybersecurity accessible to everyone.

---

**Last updated:** [16/02/2026]  
**Next planned update:** IDS Fundamentals

