# ⚒️ Workshop 🪛 

---

🧠 Fantasy Baseball Custom Ranking Model – Full Google Sheets Lesson


---

🎬 Lesson Objective

> Learn to build a complete player evaluation model in Google Sheets using real stats, formulas, and tier logic.



We’ll cover:

Stat normalization using Z-scores

Weighted scoring by category

Adding contextual modifiers (injuries, age, role)

Creating a composite final score

Separating hitters and pitchers

Auto-assigning tiers



---

🔧 Step 1 – Set Up Your Columns

In a new Google Sheet, create two sections:

Hitters (Columns A to Z)

Pitchers (Columns AA to AY)



---

📊 Hitter Section – Columns A to Z

Cell	Label

A1	Player Name
B1	OPS
C1	HR
D1	Net SB
E1	Barrel%
F1	xOBP
G1	TB-HR
H1	RunImpact


In Row 2, paste real player data from FanGraphs or your league.


---

⚖ Step 2 – Normalize Stats Using Z-Score

> Z-Score = (PlayerStat - LeagueAverage) / StandardDeviation



In columns I to O:

Cell	Label	Formula (example)

I2	Z_OPS	=STANDARDIZE(B2, 0.725, 0.055)
J2	Z_HR	=STANDARDIZE(C2, 22.0, 6.5)
K2	Z_SB	=STANDARDIZE(D2, 10, 4.2)
L2	Z_Barrel	=STANDARDIZE(E2, 8.5, 2.0)
M2	Z_xOBP	=STANDARDIZE(F2, 0.340, 0.025)
N2	Z_TBHR	=STANDARDIZE(G2, 115, 35)
O2	Z_RunImpact	=STANDARDIZE(H2, 135, 30)


> Update these league averages as needed from your dataset.




---

🎯 Step 3 – Weight Each Stat

Cell	Label	Formula

P2	Weighted OPS	=I2 * 0.20
Q2	Weighted HR	=J2 * 0.15
R2	Weighted SB	=K2 * 0.10
S2	Weighted Barrel	=L2 * 0.10
T2	Weighted xOBP	=M2 * 0.15
U2	Weighted TBHR	=N2 * 0.15
V2	Weighted RunImpact	=O2 * 0.15



---

🧮 Step 4 – Calculate Base Score

W2: =SUM(P2:V2)

This is your pure performance score based on normalized + weighted categories.


---

🧠 Step 5 – Add Modifiers

Column	Label	Sample Formula

X2	Context Modifiers	=3 + 4 + (-2) + 0 + (-1)


Include:

Prospect Boost

Role Lock (+ if full-time starter)

Injury Penalty

Trade Rumors

Age Curve



---

🔒 Step 6 – Add Role Score

Y2: =Usage_Confidence * Role_Weight

Example:

Usage_Confidence = 0.9

Role_Weight = 10 (everyday starter)


=0.9 * 10 = 9


---

🏁 Step 7 – Final Score for Hitters

Z2: =(W2 * 0.5) + (X2 * 0.25) + (Y2 * 0.25)

This gives a composite 0–100 score.


---

🔁 Now for Pitchers – Columns AA to AY

Cell	Label	Description

AA1	xFIP	Pitching efficiency
AB1	K/BB	Strikeout-to-walk ratio
AC1	CSW%	Called Strikes + Whiffs
AD1	WHIP	Walks + Hits per Inning
AE1	SVH3	Saves + 0.7 × Holds
AF1	QA4	Quality Appearances (4+ IP ≤3 ER)
AG1	wOBAA	Weighted On-Base Allowed



---

🧪 Step 2 – Normalize Pitching Stats (Z-Scores)

Cell	Formula

AH2	=STANDARDIZE(AA2, 3.85, 0.45)
AI2	=STANDARDIZE(AB2, 3.5, 1.25)
AJ2	=STANDARDIZE(AC2, 28.5, 3.0)
AK2	=STANDARDIZE(AD2, 1.22, 0.15)
AL2	=STANDARDIZE(AE2, 18.0, 8.0)
AM2	=STANDARDIZE(AF2, 10.5, 3.5)
AN2	=STANDARDIZE(AG2, 0.305, 0.035)



---

⚖ Step 3 – Weighted Pitching Scores

Cell	Formula

AO2	=AH2 * 0.15
AP2	=AI2 * 0.15
AQ2	=AJ2 * 0.15
AR2	=AK2 * 0.10
AS2	=AL2 * 0.15
AT2	=AM2 * 0.15
AU2	=AN2 * 0.15



---

🧮 Step 4 – Pitcher Base Score

AV2: =SUM(AO2:AU2)


---

🧠 Step 5 – Pitching Modifiers

AW2: =Prospect + Injury + Trade + Role_Security + Age


---

🔒 Step 6 – Pitching Role Score

AX2: =Leverage_Index * Role_Weight

Example:

=1.6 * 10 = 16


---

🏁 Step 7 – Final Pitcher Score

AY2: =(AV2 * 0.5) + (AW2 * 0.25) + (AX2 * 0.25)


---

🧩 Step 8 – Tiering Formula (Optional)

=IF(Z2>=90,"Tier 1",IF(Z2>=75,"Tier 2",IF(Z2>=60,"Tier 3",IF(Z2>=45,"Tier 4","Tier 5"))))

> Adjust for pitchers: replace Z2 with AY2




---

🎨 BONUS – Visualization

Add conditional formatting to final scores

Highlight tiers in different colors

Use data filters to sort by position, team, or tier



---

✅ What You Now Have

Fully functional hitter and pitcher ranking system

Normalized, weighted, and contextualized scores

Customizable for any scoring system

Adaptable to real-time data



---

Would you like a pre-filled Google Sheet shared to your email or Google Drive?
Or should I generate an .xlsx download link and zip it with test player data?

Let me know how you want to use this.

