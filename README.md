# AI-Controlled-VM
The inspiration behind this project came from reading an artical about a lady who had to frantically run to her Mac mini because she gave full control of her Operating sytem to Open Claw and the AI Agent procded to detail files off her her computer without her permission. 

## Goal
> Researching the behavior, capabilities, and security implications of artificial intelligence when given control of a live operating system — safely contained inside a virtual machine.

---

## Table of Contents

- [Overview](#overview)
- [Motivation](#motivation)
- [Setup & Environment](#setup--environment)
- [Experiment Log](#experiment-log)
- [Key Findings](#key-findings)
- [Security Observations](#security-observations)
- [Errors & Anomalies](#errors--anomalies)
- [Tools & Technologies](#tools--technologies)
- [Next Steps](#next-steps)

---

## Overview

**AI-Controlled-VM** is a personal research project documenting what happens when an AI model is given direct control over a virtual machine's operating system. The goal is to observe, log, and analyze AI behavior in a real computing environment — including its decision-making, tool usage, potential security risks, and failure modes.

All experiments are conducted inside an isolated virtual machine to ensure that no damage, data leakage, or unintended behavior can affect the host system or external networks.

---

## Motivation

The inspiration behind this project came from a desire to answer a few core questions:

- What does AI actually *do* when given unrestricted access to an OS?
- What security vulnerabilities emerge when an AI operates autonomously?
- What kinds of errors, hallucinations, or unexpected behaviors appear in a real system context?
- How does an AI navigate the file system, install software, run commands, and make decisions?

Rather than relying on simulations or sandboxed APIs, this project puts AI directly at the controls of a real operating system — with all the complexity, unpredictability, and risk that entails.

---

## Setup & Environment

| Component | Details |
|---|---|
| **Virtualization Platform** | VirtualBox |
| **Guest OS** | Ubuntu 22.04 |
| **Host OS** | Windows 11 |
| **AI Model Used** | Claude |
| **Interface / Access Method** | Terminal and API |
| **Network Isolation** | NAT / Bridged — outbound internet access confirmed via SMTP email test |
| **Snapshot Strategy** | After each major milestone or significant finding |

---

## Experiment Log

Each entry below represents a session or milestone in the project. Dates to be filled in.

---

### `04/23/2026` — Project Initialized

- Created the GitHub repository to log all findings and data.
- Defined the core research questions.
- Began initial reading and research into AI agent behavior on live systems.

---

### `05/16/2026` — Virtual Machine Setup

- Installed and configured the virtual machine environment.
- Selected guest OS and configured network isolation settings.
- Took a baseline snapshot before any AI interaction.

---

### `05/23/2026` — First AI Session

- Gave the AI its first set of instructions inside the VM.
- Observed initial navigation behavior: file system exploration, command usage.
- Logged all commands issued and outputs returned.
- Notable observations: Using Claude to co-write an email script, the code was saved to the Ubuntu VM and called via the terminal whenever needed. Once executed, the script accessed stored Gmail credentials and prompted for a recipient, email subject, and message body. The email was successfully sent and automatically included a "Best regards" sign-off. This demonstrates a human-AI collaboration workflow where Claude authors the code, which is then stored and run independently on the VM through the terminal.

---

### `05/23/2026` — Security Testing Begins

- Began probing for potential security issues arising from AI autonomy.
- Tested scenarios including: file modification, process spawning, permission escalation attempts.
- Documented any unexpected access patterns or behaviors.

---

### Error & Anomaly Logging

- Errors encountered during AI-controlled sessions will be catalogued here on an ongoing basis.
- Cases where the AI misinterprets system state or issues invalid commands will be noted.
- Hallucination events (AI asserting incorrect information about the system) will be identified and logged.

---

### `05/24/2026` — Ongoing Experiments / Latest Session

- After successfully sending emails through the terminal, research began into integrating Claude's API, which would allow the AI to autonomously write and send emails without any human input. The API uses a credit-based system billed to an Anthropic account, accessed via an API key. An initial budget of $10.00 in credits is planned to fund further experiments, with additional credits to be added as needed.

---

## Key Findings

> *(To be updated as experiments progress)*

- Finding 1: AI successfully performed email sending tasks via terminal using API key authentication.
- Finding 2: TBD
- Finding 3: TBD

---

## Security Observations

> *(To be updated as experiments progress)*

This section tracks any behaviors that raised security concerns during AI-controlled sessions.

- **Observation 1:** Outbound internet access is available inside the VM. Successfully sent an email via terminal using SMTP code, confirming the AI could theoretically exfiltrate data through the same method. This represents a potential data exfiltration pathway that would need to be addressed in a fully secured environment.
- **Observation 2:** TBD
- **Observation 3:** TBD

---

## Errors & Anomalies

A running log of unexpected errors, crashes, or anomalous behavior observed during experiments.

| Date | Description | AI Response | Resolution |
|---|---|---|---|
| `05/22/2026` | AI was unable to access Gmail account | An error code was returned in the terminal, causing the script to fail | Resolved by granting the AI access to the Google API key |
| `05/22/2026` | The email script required multiple revisions. The code initially defaulted to emailing a specific recipient automatically | The email was sent to the wrong recipient without prompting the user | Updated the code multiple times to prompt the user to input a recipient email address and subject line before sending |

---

## Tools & Technologies

- **Virtual Machine:** VirtualBox
- **Operating System:** Windows 11 Home
- **AI Model:** Claude Sonnet 4.6
- **Logging Tools:** Manual Logs
- **Version Control:** Git / GitHub

---

## Next Steps

- [ ] Make AI agents accomplish complex tasks
- [ ] Expand security testing scenarios
- [ ] Test with additional AI models for comparison
- [ ] Publish findings summary

---

## ⚠️ Disclaimer

All experiments in this project are conducted inside an isolated virtual machine. No AI interactions in this project target live systems, external networks, or real user data. This research is purely educational and is intended to better understand AI behavior and safety in autonomous computing environments.

---

*Last updated: May 31, 2026*
