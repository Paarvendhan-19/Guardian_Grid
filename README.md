<div align="center">

# 🛡️ GuardianGrid
**Parametric Insurance-as-a-Service (PIaaS) for the Gig Economy**

[![Guidewire DEVTrails](https://img.shields.io/badge/Guidewire-DEVTrails_2026-blueviolet?style=for-the-badge)](https://#)
[![Architecture](https://img.shields.io/badge/Architecture-B2B2C_Microservices-blue?style=for-the-badge)](https://#)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2-6DB33F?style=for-the-badge&logo=spring)](https://#)
[![Python FastAPI](https://img.shields.io/badge/Python-FastAPI-009688?style=for-the-badge&logo=fastapi)](https://#)
[![React](https://img.shields.io/badge/React-18.0-61DAFB?style=for-the-badge&logo=react)](https://#)

> [cite_start]*Automated, zero-touch income protection for India's 5 million delivery partners.* [cite: 2, 61]

**[ 📺 View Demo Video ](#) • [ 📖 API Documentation ](#) • [ 📊 Pitch Deck ](#)**

</div>

---

## ⚡ Executive Summary

### The Problem: Climate Vulnerability
[cite_start]Gig workers (Zomato, Swiggy, Zepto) earn strictly by the delivery[cite: 4, 73]. [cite_start]When external disruptions hit—severe floods, extreme heatwaves (45°C+), or localized curfews—platforms halt operations[cite: 6]. [cite_start]The worker loses their daily wage instantly[cite: 7]. [cite_start]Traditional insurance fails this demographic due to high upfront costs, lengthy paperwork, and manual adjusters[cite: 9]. [cite_start]**Workers need their money today, not next month.** [cite: 10]

### The Pivot: Why B2C Fails & B2B2C Wins
[cite_start]A standalone direct-to-consumer (B2C) insurance app fails due to massive customer acquisition costs, GPS spoofing, and restricted access to verified income data[cite: 29].

**GuardianGrid is a B2B2C PIaaS ecosystem.** We do not build apps for drivers. We provide a robust API engine embedded directly into the delivery aggregator's existing backend.
* [cite_start]**🔒 100% Data Integrity:** The aggregator securely feeds us the worker's verified hourly earnings and live GPS zone[cite: 29, 49, 50].
* [cite_start]**📡 Zero-Touch Execution:** We continuously poll environmental APIs (like the IMD)[cite: 17, 53]. [cite_start]If a zone floods, we trigger the payout[cite: 18, 54].
* [cite_start]**💸 No Claim Filing:** Payouts are pushed instantly to the worker's digital wallet[cite: 20].

---

## 🏗️ Enterprise Tech Stack & Architecture

Our architecture isolates high-velocity environmental data from strict financial ledgers to ensure ACID compliance at scale.

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Financial Engine** | `Java Spring Boot` | [cite_start]Orchestrates the weekly micro-premium deductions (2-3%), policy generation, and instant B2B UPI payout webhooks[cite: 35, 52]. |
| **Risk & AI Module** | `Python / FastAPI` | [cite_start]Dynamically adjusts risk tiers based on historical disruption data and prevents spatial fraud[cite: 15, 33]. |
| **Immutable Ledger** | `PostgreSQL` | [cite_start]Central relational database for active policies, B2B API keys, and strict financial transactions[cite: 47]. |
| **Velocity Sink** | `MongoDB` | NoSQL data sink for continuous JSON streams from environmental APIs (IMD Weather, CPCB Pollution). |
| **Frontend SDK** | `React / Tailwind` | [cite_start]Contains the "White-Label" rider UI SDK and the internal "God Mode" Admin Dashboard[cite: 21, 56]. |

---

## 🧠 The "Shift Block Guarantee" Innovation

[cite_start]Paying a flat 70% of a week's income for a 2-hour storm bankrupts the insurer[cite: 39]. Calculating payouts by the minute results in insulting ₹50 payouts.

**Our Mathematical Solution:** GuardianGrid utilizes **Shift Block Guarantees**.
If a weather API confirms a disruption lasting **> 45 minutes** during a critical earning block (e.g., *Dinner Rush: 7 PM - 11 PM*), the system triggers a **flat lump-sum payout (e.g., ₹400)**. This provides meaningful relief to the worker while protecting the startup's actuarial balance sheet.

---

## 🚀 Key Platform Features

* **🔌 Plug-and-Play Aggregator Sandbox:** Secure REST endpoints allowing any delivery platform to register riders and sync live earnings in under 24 hours.
* [cite_start]**⚡ Multi-Variable Parametric Triggers:** Built-in polling for Weather (IMD), Air Quality (CPCB), and hyper-local traffic gridlocks[cite: 15].
* **🤖 GenAI Multilingual Notifications:** Uses LLMs to instantly translate payout alerts into the worker's regional language via WhatsApp (e.g., *"Vanakkam, Zone 4 is flooded. ₹400 deposited for your lost shift."*).
* [cite_start]**🎮 "God Mode" Admin Panel:** A comprehensive React dashboard allowing administrators to inject simulated weather disruptions into specific city zones for system testing and auditing[cite: 21].

---

## 💻 Developer Quickstart

<details>
<summary><b>Click to expand local installation instructions</b></summary>

GuardianGrid is containerized for rapid deployment.
*Prerequisites: Docker, Docker Compose, JDK 17+, Python 3.10+, Node.js 18+.*

```bash
# 1. Clone the repository
git clone [https://github.com/your-team/GuardianGrid.git](https://github.com/your-team/GuardianGrid.git)
cd GuardianGrid

# 2. Spin up the databases (PostgreSQL & MongoDB)
docker-compose up -d

# 3. Start the Python AI Risk Engine
cd ai-engine
pip install -r requirements.txt
uvicorn main:app --reload --port 8000

# 4. Start the Spring Boot Financial Engine
cd backend
./mvnw spring-boot:run

# 5. Start the React Admin Dashboard
cd frontend
npm install
npm run dev
</details>

📡 API Reference Example
How a partner aggregator (e.g., Swiggy) registers a rider for an active shift block:

JSON
POST /api/v1/policies/activate
Content-Type: application/json

{
  "aggregatorId": "agg_swiggy_001",
  "workerId": "wk_998273",
  "currentZone": "CHE-ZONE-4",
  "shiftBlock": "DINNER_RUSH_1900_2300",
  "verifiedWeeklyBaseline": 4500.00,
  "riskTier": "TIER_1"
}
<div align="center">
<p><b>Built for the Guidewire DEVTrails 2026 Unicorn Chase</b></p>
<p><i>Phase 1 Submission</i></p>
</div>
