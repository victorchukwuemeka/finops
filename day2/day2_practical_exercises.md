# Day 2 Practical Exercises (No Cloud Account Needed)

Use `day2/day2_sample_costs.csv` as your input dataset.

## Exercise 1: Tagging Quality Audit
**Goal:** Identify missing or risky tags.

### Steps
1. Open the CSV in Excel or Google Sheets.
2. Check if every row has `Owner`, `Environment`, `Cost_Center`, and `Business_Service`.
3. Flag any row with missing or inconsistent values.

### Output
- A list of rows that need tag fixes.
- A short policy note: “Tags required at creation; block resources without tags.”

## Exercise 2: Showback Allocation
**Goal:** Allocate spend by team owner.

### Steps
1. Create a pivot table grouped by `Owner`.
2. Sum `Monthly_Cost`.
3. Add a second pivot grouped by `Business_Service`.

### Output
- Table: Cost by owner.
- Table: Cost by business service.
- 2 insights (e.g., top cost driver, unexpected cost).

## Exercise 3: Waste Candidate List
**Goal:** Identify probable waste and propose actions.

### Steps
1. Filter rows where `Status` is `Unused`, `Deprecated`, or `Batch`.
2. For each, propose a quick action (delete, schedule, or right-size).

### Output
- Waste list with 2–3 actions and estimated % savings.

## Exercise 4: Basic Dashboard
**Goal:** Create a clear visibility report.

### Must include
- Top 5 cost drivers
- Cost by environment
- Cost by owner
- Waste candidates summary

### Output
- Screenshot or export of the dashboard.
- 3‑bullet narrative for leadership.

## Exercise 5: Chargeback Draft (Policy)
**Goal:** Draft a simple chargeback model.

### Steps
1. Decide allocation rule (by `Owner` or `Cost_Center`).
2. Define dispute process and review cycle.

### Output
- One‑page chargeback policy draft.

---
If you want, I can add a filled‑in answer key and sample dashboard.
