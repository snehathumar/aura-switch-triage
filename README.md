# 🛡️ A.U.R.A. (Autonomous Unified Response Agents)
**AI-Driven Cybersecurity Incident Triage & Mitigation Workflow built with Switch**

## 📌 Overview
Security and DevOps teams often lose critical response time sorting through noisy security alerts, server logs, and vulnerability reports across fragmented dashboards. **A.U.R.A.** brings automated, multi-agent cybersecurity incident triage directly into team chat using **Switch**.

By turning a Discord or Telegram channel into a shared Switch Room, A.U.R.A. connects two specialized AI agents that collaborate with human security engineers in real time to classify threats and generate immediate containment scripts.

---

## ⚙️ How We Used Switch

### 1. Connected Agents
We configured two collaborative agents inside our Switch room (`#aura-triage`):
* **`@aura-triager` (Lead Threat Triager):** Listens to incoming security alerts or suspicious logs reported by teammates, summarizes the threat vector in one clear line, classifies severity (`Critical Incident`, `False Positive`, or `Policy Question`), and routes critical threats directly to `@aura-repro`.
* **`@aura-repro` (Remediation & Reproduction Agent):** Triggered automatically by `@aura-triager` for critical incidents. It writes a minimal verification script or firewall/patch command to isolate the threat and posts the exact remediation steps in the same thread for human sign-off.

### 2. Room & Chat Setup
* **Platform:** Discord / Telegram bridged via Switch Console
* **Room Name:** `aura-triage`
* **Workflow:** Human teammates drop raw server logs or CVE alerts into the chat channel. Both agents read from the shared room log, hand off tasks autonomously via the Switch protocol, and wait for a human teammate to approve the final rollback or patch command.

---

## 🚀 How to Run It

### Prerequisites
* [Switch Console](https://github.com) installed on your machine (with Docker running)
* A Discord Server or Telegram Group bridge token
* Any Switch-compatible agent provider (Claude Code, OpenCode, or Codex)

### Setup Steps
1. **Clone this repository:**
   ```bash
   git clone [https://github.com/YOUR-USERNAME/aura-switch-triage.git](https://github.com/YOUR-USERNAME/aura-switch-triage.git)
   cd aura-switch-triage# aura-switch-triage
