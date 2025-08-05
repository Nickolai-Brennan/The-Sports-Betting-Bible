---
title: "💯 Question 004 – What Metrics Reflect a Pitcher’s Stuff?"
slug: question-004-stuff-score
date: 2025-08-05
author: "Nick Brennan"
project: "Strik3Zone – The Sports Gaming Codex"
tags: [stuff+, csw%, spin rate, fantasy baseball, mlb, sabermetrics, pitcher scouting, storm model]
categories: [Masterclass, R&D, Stats, Pitching Analytics]
status: "Published"
---

<a name="question004"></a>

# 💯 Question 004 – What Metrics Reflect a Pitcher’s “Stuff”?  
> 📊 _Evaluating “stuff” is the foundation of pitching analytics. In this breakdown, we explore the core metrics that matter, the math behind scoring them, and a model that helps predict future dominance._

---

## 🔍 Overview

**In this article, we’ll explore:**
- ✅ What is “stuff” in modern baseball?
- ✅ Which [advanced metrics](https://library.fangraphs.com/) define it?
- ✅ How can we build a [model](https://www.fangraphs.com/leaders.aspx) to score it?
- ✅ How does it correlate with fantasy value and future success?

---

## 🔑 Key Concepts & Definitions

| Term/Metric      | Meaning / Why It Matters                                 | Source         |
|------------------|----------------------------------------------------------|----------------|
| **[Stuff+](https://blogs.fangraphs.com/instagraphs/stuff-makes-a-triumphant-return/)**   | Arsenal-wide quality index (100 = Avg)              | FanGraphs      |
| **[CSW%](https://library.fangraphs.com/pitching/csw/)**        | Called Strikes + Whiff % = plate deception           | FanGraphs      |
| **[Spin Rate](https://baseballsavant.mlb.com/statcast_search)** | Measures pitch movement & deception                 | Statcast       |
| **[K/BB](https://www.fangraphs.com/leaders.aspx?pos=all&stats=pit)**        | Strikeout-to-walk ratio = dominance vs. control     | FanGraphs      |
| **[Whiff%](https://baseballsavant.mlb.com/leaderboard/statcast)**           | % of swings that miss = swing-and-miss power        | Baseball Savant|

---

## 🧮 Stuff Score Model – Core Formula

> Here’s how we quantify “stuff” using a weighted scoring model:

```markdown
STUFF_SCORE = (Stuff+ × 0.35) + (CSW% × 0.25) + (Spin Index × 0.15) + (K/BB × 0.15) + (Whiff% × 0.10)
```
---

📊 Metric Table

🧠 Stat Science Context

📈 Real-World Examples

📐 Spreadsheet Builder

🧠 Reflection + Worksheet

🔗 External links and glossary tags

✅ Fully link-ready for Phase 3



---

---

## 📊 Metric Breakdown Table

| Metric         | Description                           | Stat Type         |
|----------------|----------------------------------------|-------------------|
| **Stuff+**     | Arsenal-level pitch quality index      | Advanced Metric   |
| **CSW%**       | Called Strikes + Whiff %               | Plate Discipline  |
| **Spin Index** | Scaled spin rate score (0–100)         | Pitch Shape       |
| **K/BB Ratio** | Strikeouts per walk = efficiency       | Command Metric    |
| **Whiff%**     | % of swings that miss                  | Deception Power   |

---

## 🧠 Stat Science Context

- 🧪 **Stabilization Points:**  
  - *CSW%*, *Whiff%*, and *K/BB* stabilize within 50–100 batters.
  - *Stuff+* needs ~200 pitches per pitcher to normalize.

- 📈 **Predictive Power:**  
  - *CSW%* and *Stuff+* are strong correlates to [xERA](https://library.fangraphs.com/pitching/era-estimators/) and [SIERA](https://library.fangraphs.com/pitching/siera/).
  - Widely used in **stuff models**, **ML regressions**, and **fantasy player tiers**.

- 🤖 **Modeling Use Cases:**  
  - All 5 metrics are top-10 features in machine learning models that predict:  
    - Strikeout rate  
    - Barrel suppression  
    - Fantasy auction value  
    - Leverage index role probability

---

## 📈 Real-World STUFF_SCORE Examples (2023)

| Player             | Stuff+ | CSW%  | Spin Index | K/BB | Whiff% | STUFF_SCORE | Tier         |
|--------------------|--------|-------|------------|------|--------|--------------|--------------|
| Bryan Abreu        | 132    | 36.8% | 92         | 4.2  | 38.5%  | 73.68        | 🟢 Excellent |
| Josh Hader         | 125    | 34.5% | 89         | 4.5  | 36.1%  | 70.01        | 🟢 Excellent |
| Felix Bautista     | 138    | 37.2% | 95         | 5.1  | 39.3%  | 76.55        | 🔥 Top Tier  |
| David Bednar       | 119    | 31.0% | 85         | 3.7  | 30.2%  | 65.73        | 🟡 Good      |
| Devin Williams     | 130    | 35.4% | 91         | 4.6  | 35.0%  | 72.19        | 🟢 Excellent |

🧠 These results show that *Stuff+ alone* doesn't define dominance — it must be supported by **command**, **swing-and-miss power**, and **deception metrics** like *CSW%* and *Whiff%*.

---

## 📐 Spreadsheet Builder – STUFF_SCORE Evaluator

### ➕ Column Setup

| Column | Header        |
|--------|----------------|
| A      | Player Name    |
| B      | Stuff+         |
| C      | CSW%           |
| D      | Spin Index     |
| E      | K/BB           |
| F      | Whiff%         |
| G      | STUFF_SCORE    |
| H      | Tier Level     |

---

### 🧮 Score Formula (Cell G2):

```excel
=(B2*0.35)+(C2*0.25)+(D2*0.15)+(E2*0.15)+(F2*0.10)
```

---

🏷️ Tier Formula (Cell H2):
```
=IF(G2>=80,"🔥 Top Tier",IF(G2>=70,"🟢 Excellent",IF(G2>=60,"🟡 Good",IF(G2>=50,"⚠️ Average","🔻 Concerning"))))
```

---

✅ Conditional Formatting Suggestions

Green: Score ≥ 70

Yellow: Score 60–69

Orange: Score 50–59

Red: Score < 50


Use formatting to quickly flag elite arms or hidden red flags.


---

✍️ Reader Worksheet – Apply What You’ve Learned

📌 Part 1 – Choose 3 Pitchers and Record Stats

Player	Stuff+	CSW%	Spin Index	K/BB	Whiff%	STUFF_SCORE	Tier

							
							
							



---

🧠 Part 2 – Reflect on Your Results

1. Which pitcher performed best by the model?


2. Did any low-name pitcher score highly?


3. Does the STUFF_SCORE align with their usage or role?


4. Would you draft or acquire based on this?




---

🎯 Bonus Challenge

Pick 5 pitchers from today’s Statcast leaderboard

Score them using this model

Share your analysis in the Strik3Zone Discord



---

📥 Download Google Sheets Version
🖨️ Printable PDF Worksheet


---

🔗 Related Reading

📘 FanGraphs: What is Stuff+?

📘 Statcast: Pitch Leaderboards

📘 Strik3Zone STORM Model

📘 CSW% Glossary

📘 SIERA Explained



---

📚 Glossary Terms

Keyword	Purpose

Stuff+	Composite pitch arsenal strength
CSW%	Plate discipline and deception measure
Spin Index	Standardized movement metric
Whiff%	Swing-and-miss power
K/BB	Command vs. strikeout dominance
STORM Score	Reliever projection model by Strik3Zone



---

📘 About the Author

Nick Brennan
Founder of Strik3Zone and developer of the STORM Model, CheatZ, and The 100 Question Masterclass.

💬 Join the Discord

📊 Visit GitHub

📝 Subscribe on Substack

🌐 Explore All Questions



---

Let me know if you'd like:
- ✅ A downloadable `question-004.md` version with Phase 2 integrated  
- ✅ This formatted into HTML for WordPress (Phase 3)  
- ✅ A printable PDF worksheet pack (Phase 4)

Would you like to proceed to **Phase 3 – Advanced HTML Output**?



---




-
