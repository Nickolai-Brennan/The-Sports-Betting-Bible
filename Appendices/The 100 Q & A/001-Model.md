📝 Answer 1

## ⚾ Question #1: *How do we measure a hitter's consistency over a full season?*

---

### 🎯 Goal:

Create a “**Hitter Consistency Score**” that shows which batters produce steady weekly fantasy output, not just boom-or-bust games. This is especially useful in **weekly-lock** fantasy leagues.

---

## 📘 Step-by-Step Instructional Walkthrough

---

### 🧱 **Step 1: Define the Stat to Build — Consistency Index**

We’ll use this core formula:

```
Consistency Index (CI) = Mean Weekly Fantasy Points / Standard Deviation
```

This is a variation of the **coefficient of variation**, flipped to reward stability. Higher values mean greater reliability.

---

### 📥 **Step 2: Gather Weekly Data**

You’ll need:

* Weekly fantasy points per player (7-day splits)
* Weekly PA, AB, or Games Played to ensure meaningful sample size

**Where to pull from:**

* 📊 FanGraphs: "Game Log" → export weekly totals
* 🧠 Statcast (Baseball Savant): for raw game-by-game data
* 📈 Your league scoring export (Fantrax, Yahoo, etc.)

**Minimum Filter**:
Remove players with fewer than **8 weeks of play** or **<20 PA/week**.

---

### 📗 Step 3: Build the Sheet or Script

#### 🟩 In Google Sheets:

1. **Column A**: Player Name
2. **Columns B–O**: Weekly Fantasy Scores (Week 1 to Week 14)
3. **Column P**: Average

   ```excel
   =AVERAGE(B2:O2)
   ```
4. **Column Q**: Standard Deviation

   ```excel
   =STDEV(B2:O2)
   ```
5. **Column R**: Consistency Index

   ```excel
   =IF(Q2=0, 0, P2/Q2)
   ```

Sort by Column R (highest to lowest) to get your **most consistent hitters**.

---

#### 🐍 In Python (Pandas):

```python
import pandas as pd

df = pd.read_csv("weekly_hitter_points.csv")

# Assume weekly columns: Week1, Week2, ..., Week14
weekly_cols = [col for col in df.columns if 'Week' in col]

df["Mean"] = df[weekly_cols].mean(axis=1)
df["StDev"] = df[weekly_cols].std(axis=1)
df["ConsistencyIndex"] = df["Mean"] / df["StDev"]

# Optional: Filter min weeks with data
df["WeeksPlayed"] = df[weekly_cols].count(axis=1)
df = df[df["WeeksPlayed"] >= 8]

df.sort_values("ConsistencyIndex", ascending=False).head(20)
```

---

### 📊 Step 4: Add Context & Visuals

#### Chart Ideas:

* **Bar Chart**: Top 20 Consistency Scores
* **Scatter Plot**: HRs vs. Consistency (do power hitters sacrifice consistency?)
* **Bubble Chart**: Consistency vs. PA with bubble size = OBP

#### Additional Filters:

* By **position** (e.g. 2B vs. 1B)
* By **team or division**
* By **monthly splits** (early-season vs. late-season consistency)

---

### 📈 Step 5: Create Consistency Tiers

| CI Range  | Tier            | Label                  |
| --------- | --------------- | ---------------------- |
| 2.50+     | Elite           | Weekly Rock            |
| 2.00–2.49 | Strong          | Consistent Contributor |
| 1.50–1.99 | Mid             | Volatile but Startable |
| 1.00–1.49 | Risky           | Matchup-Only Option    |
| <1.00     | Highly Volatile | Bench/Fade             |

---

### 🧠 Step 6: Interpretation & Use Case

* Use **CI** to decide weekly starter over similar options.
* Helps in **points leagues** and weekly-rostered Roto leagues.
* Can influence waiver claims, trades, or playoff start/sit calls.

---

### 🔁 Step 7: Expand the Model

Consider adding:

* **Rolling 4-week CI** to see if trends are changing.
* **Injury filter** (ignore weeks with <10 PA).
* Combine with **Fantasy Floor Score** = MIN(weekly pts in 60% of weeks).
* Add percentile comparison to all MLB hitters.

---
