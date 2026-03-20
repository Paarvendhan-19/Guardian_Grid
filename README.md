<div align="center">

# 🛡️ GuardianGrid
**Parametric Insurance-as-a-Service (PIaaS) for the Gig Economy**

[![Guidewire DEVTrails](https://img.shields.io/badge/Guidewire-DEVTrails_2026-blueviolet?style=for-the-badge)](https://#)
[![Architecture](https://img.shields.io/badge/Architecture-B2B2C_Microservices-blue?style=for-the-badge)](https://#)
[![Backend](https://img.shields.io/badge/Backend-Java_Spring_Boot-6DB33F?style=for-the-badge&logo=spring)](https://#)
[![AI Engine](https://img.shields.io/badge/AI-Python_FastAPI-009688?style=for-the-badge&logo=fastapi)](https://#)

> *Automated, zero-touch income protection for India's 5 million delivery partners.*

**[ 📺 View Demo Video ](#) • [ 📖 API Documentation ](#) • [ 📊 Pitch Deck ](#)**

</div>

---

## 👥 The Persona: Who is our user, *really*?
The standard narrative treats gig workers as a monolith. In reality, our user is a highly vulnerable, cash-dependent micro-entrepreneur. 
* **The Reality of Multi-Homing:** They do not just drive for Zomato; they switch between Swiggy, Zepto, and Rapido depending on the hour. 
* **The Financial Tightrope:** A Tier-1 delivery partner earns ₹3500–₹6000 weekly, heavily reliant on peak "surge" windows (e.g., the Dinner Rush).
* **The Disruption Impact:** When a localized flash flood or sudden curfew hits, they don't just lose an hour of work—they lose the critical surge window that pays their rent. Traditional insurance, which requires 14 days to manually verify a claim, is useless to a worker who needs to buy groceries tonight. 

**GuardianGrid** abandons the flawed B2C app model. We are a **B2B2C API ecosystem** embedded directly into aggregator apps, ensuring instant, zero-touch payouts when the weather halts their shift.

---

## 🧠 The Strategy: How does the AI *actually* work?
Our system does not just blindly trust public weather APIs. It utilizes a **Spatial Anomaly Detection Engine** to prevent basis risk and fraud.

1. **The Ground Truth Mesh:** We ingest continuous JSON streams from the IMD (Weather) and CPCB (Air Quality) APIs into a high-velocity MongoDB database.
2. **Spatial Cross-Referencing:** When a severe event is flagged (e.g., Rainfall > 50mm/hr), the Python/FastAPI ML engine cross-references the environmental data grid against the worker's live GPS coordinates provided by the aggregator's API. 
3. **Anomaly Detection & Fraud Prevention:** Drawing on advanced pattern-recognition principles (similar to real-time road damage detection models), the AI evaluates the spatial validity of the claim. If the worker's phone telemetry shows them actively moving at 40km/h outside the flood zone, the AI flags it as a multi-homing fraud attempt and voids the payout.
4. **Local Hardware Acceleration:** Model training and inference prototyping are optimized for local GPU execution, leveraging a dedicated 6GB VRAM pipeline for rapid iteration before cloud deployment.

---

## 🏗️ The Foundation: How does it get built?
Handling automated micro-premiums alongside high-velocity data requires an enterprise-grade, strictly typed architecture to ensure transactional integrity.

* **Core Financial Engine (Java & Spring Boot):** The central orchestrator. It handles the weekly 2-3% micro-premium deductions, maintains state, and securely executes the instant B2B UPI webhooks when a payout is triggered. 
* **Dual-Database Architecture:**
    * **PostgreSQL:** The ACID-compliant immutable ledger for active policies, partner API keys, and strict financial transaction histories.
    * **MongoDB:** The NoSQL velocity sink handling the thousands of external environmental API pings per minute, keeping the main ledger completely unblocked.
* **The "Shift Block" Calculation:** To prevent the actuarial ruin of paying a full week's wages for a 2-hour storm, the Spring Boot engine calculates payouts using **Shift Blocks**. If a disruption lasts > 45 minutes during a critical earning window, it triggers a flat lump-sum payout (e.g., ₹400), dynamically balancing the startup's risk pool.

---

## 🚨 DEVTrails Economy & Meta-Game Strategy
*We recognize that building the code is only half the battle. Surviving the 6-week Guidewire startup simulation requires rigorous capital management.*

* **The Market Crash Protocol:** We have explicitly accounted for the mandatory DC 8,000 market crash fine scheduled by the simulation. We are immediately allocating DC 3,000 to purchase the **Sabotage Shield**, securing our capital runway.
* **Capital Efficiency:** By relying on our B2B2C embedded strategy, we drop simulated Customer Acquisition Costs (CAC) to near-zero. 
* **Expertise Investment:** We have budgeted DC 8,000 for the Phase 3 Architecture Review to ensure our Java/Spring Boot backend receives a 5-star validation from Guidewire engineers.

---

## 💻 Developer Quickstart

<details>
<summary><b>Click to expand local installation instructions</b></summary>

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
