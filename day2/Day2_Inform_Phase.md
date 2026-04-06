# Day 2: Inform Phase — Visibility & Allocation

## Goals for the session
- Understand cloud cost models, billing constructs, and why tagging matters.
- Design a tagging strategy that supports allocation and governance.
- Apply chargeback/showback models for accountability.
- Compare cost visibility tools (native + open-source).
- Build a basic cost dashboard and allocation report.

## 1) Cloud cost models & billing constructs
### Cost models
- **Pay‑as‑you‑go:** Variable cost tied to usage.
- **Committed use (Reserved/Committed/Savings Plans):** Discounted pricing for predictable workloads.
- **Spot / Preemptible:** Deep discounts for interruptible workloads.
- **Hybrid:** Mix of committed + on‑demand + spot for balance.

### Billing constructs (what shows up on the bill)
- **Subscription / Project / Account:** Billing boundary.
- **Resource Group / Tag / Label:** Allocation boundaries.
- **Meter / SKU:** The specific billable item.
- **Usage vs. fixed fees:** Consumption‑based vs. flat recurring charges.

## 2) Tagging strategy for visibility
Tagging is the backbone of allocation and accountability.

### Recommended tag set (minimum viable)
- `owner` — team or person
- `environment` — dev/test/prod
- `cost-center` — finance code
- `business-service` — product or workflow name
- `purpose` — why it exists
- `expiry` — review or deletion date
- `auto-shutdown` — true/false

### Tagging rules
- Make tags **mandatory at creation**.
- Enforce tags with policy (block if missing).
- Standardize values (drop‑downs or allowlists).

## 3) Chargeback vs. Showback
### Showback
- Report costs to teams but do not bill them.
- Best for early adoption or cultural change.

### Chargeback
- Costs are billed directly to team budgets.
- Strong accountability, but needs mature governance.

### When to use which
- **Start with showback** to build trust.
- **Move to chargeback** once data quality and ownership are strong.

## 4) Tools for cost visibility
### Native tools
- **Azure Cost Management** — budgets, alerts, allocation by tags.
- **AWS Cost Explorer** — reports, RI/SP analysis.
- **GCP Billing Reports** — usage and export to BigQuery.

### Open‑source / vendor‑neutral
- **OpenCost** — Kubernetes cost visibility.
- **Grafana + Prometheus** — custom cost dashboards.
- **FinOps dashboards** — lightweight CSV/BI‑based reporting.

## 5) Lab: Build cost dashboards & allocation reports
**Objective:** Create a basic cost visibility report and allocation view.

### Lab steps (60–75 minutes)
1. **Ingest data**
   - Use the provided monthly cost CSV.
2. **Normalize fields**
   - Ensure `owner`, `environment`, `cost-center`, `business-service`.
3. **Allocate spend**
   - Group costs by `owner` and `business-service`.
4. **Build dashboard**
   - Top 5 cost drivers
   - Waste candidates
   - Cost by team
   - Cost by environment
5. **Create a 1‑page report**
   - Summary + 3 insights + next actions

### Output checklist
- A cost summary table
- An allocation chart (owner or cost-center)
- A waste list with 2–3 recommendations
- A short narrative for leadership

## 6) Exercises (Hands‑On)
### Exercise 1: Tagging Audit (20 minutes)
**Objective:** Identify missing tags and define a remediation plan.
- Input: Monthly cost CSV or billing export.
- Task: List resources missing any of the required tags.
- Output: A remediation list with owner, missing tags, and deadline.

### Exercise 2: Showback Report (25 minutes)
**Objective:** Allocate costs to teams without charging them yet.
- Input: Cost data + tag mapping.
- Task: Group spend by `owner` and `business-service`.
- Output: A one‑page showback report (table + chart + 2 insights).

### Exercise 3: Chargeback Model Draft (30 minutes)
**Objective:** Build a chargeback policy proposal.
- Task: Define the rule for how costs will be billed (by team, service, or cost‑center).
- Output: One‑page policy draft including dispute process and escalation.

### Exercise 4: Dashboard Build (45 minutes)
**Objective:** Create a clear visibility dashboard.
- Must include:
- Top 5 cost drivers
- Cost by environment
- Cost by owner
- Waste candidates
- Output: Dashboard screenshot or exported report.

### Exercise 5: OpenCost Quickstart (Optional, 30 minutes)
**Objective:** Show cost visibility for Kubernetes workloads.
- Task: Explain how OpenCost would be deployed and which teams use it.
- Output: A 5‑bullet summary and a simple architecture diagram.

## 7) Tools Needed (Robust Setup)
### Data sources
- Cloud provider billing export (Azure/AWS/GCP)
- Cost & usage reports (daily or hourly)
- Tag policy export (current required tags)

### Core tools
- **Azure Cost Management** or equivalent native tool
- **Excel / Google Sheets** for quick analysis
- **Power BI / Looker / Tableau** for dashboards
- **OpenCost** for Kubernetes cost visibility

### Supporting tools
- **Policy engine**: Azure Policy / AWS Config / GCP Org Policy
- **Automation**: Azure Automation / AWS Lambda / Cloud Functions
- **Data warehouse**: BigQuery / Snowflake / Azure Synapse
- **Alerting**: Budget alerts + anomaly detection
- **Ticketing**: Jira / ServiceNow for remediation tracking

### Suggested minimum stack (fast to implement)
- Native cost tool + Sheets + Power BI
- Tag policy enforcement via cloud policy engine
- Weekly showback report

## 8) Discussion prompts
- Which tags are missing in your environment today?
- Who should own tagging policy enforcement?
- Which teams would resist chargeback and why?
- How would you explain “unit economics” to a non‑technical leader?

## 9) Wrap‑up summary
- Inform Phase is about **visibility and accountability**.
- Tagging quality drives the accuracy of every report.
- Showback builds culture; chargeback enforces accountability.
- Tools help, but **clean allocation logic** is what makes insights usable.

---
If you want, I can also generate lab templates, a sample dashboard, or a slide deck for Day 2.
