# Recommended Folder Structure & Digital Workflow

A well-organized digital workspace is critical for managing fantasy sports, betting strategies, and data modeling. Having a clean folder structure ensures you can quickly access projections, track bankrolls, and update models without losing valuable data. Below is a suggested setup.


---

## Folder Tree Structure
### See Content Folder 📂 
---

## Workflow Overview

### **1. Daily Workflow**
1. **Data Pulls:** Download updated player stats from FanGraphs/Baseball Savant and place them in `03_Data/Raw_Stats/`.
2. **Processing:** Clean and normalize data in Python/Excel, saving outputs to `03_Data/Processed_Stats/`.
3. **Fantasy Updates:** Update draft boards or DFS lineups in `01_Fantasy/`.
4. **Betting Updates:** Log bets and ROI data in `02_Betting/BetLogs/`.

---

### **2. Weekly Workflow**
- **Update Models:** Run your machine learning or projection models (`04_Models/`) and validate results.
- **Visualize:** Refresh Power BI/Looker dashboards in `05_Visuals/`.
- **Research Notes:** Document insights or trends in `06_Docs/Notes/`.

---

### **3. Backup Strategy**
- Keep a weekly backup of all critical spreadsheets and models in `07_Backups/Weekly/`.
- Create a monthly compressed archive (zip) for long-term storage in `07_Backups/Monthly/`.

---

## Recommended Tools for Workflow
- **Version Control:** GitHub (push scripts and models to repositories).
- **Automation:** Zapier or Python schedulers for daily data pulls.
- **Visualization:** Looker Studio or Tableau for dashboards.
- **Tracking:** Google Sheets for quick logs, Excel for deep modeling.

---

# Quick Setup Checklist
1. Create the folder structure above.
2. Link your Python or R scripts to the `03_Data` folder for smooth ETL (Extract-Transform-Load) flows.
3. Connect your dashboards (Looker/Tableau) to `03_Data/Processed_Stats/` for auto-refreshes.
4. Set reminders for weekly backups and model validation.
