# IPL Analytics Project

## Overview

This project is an **end-to-end analysis of IPL matches** using historical data. It covers:

* Match outcome analysis
* Batting impact
* Bowling impact, including death overs
* All-rounder impact score
* Machine learning model to predict match winners

The goal is to provide **data-driven insights** into team and player performance, as well as the factors influencing match outcomes.

---

## Dataset

The project uses the following CSV files:

1. `Ball_By_Ball_Match_Data.csv` — Detailed ball-by-ball match data
2. `Match_Info.csv` — Match metadata including teams, venue, toss, and result
3. `teams_info.csv` — Team information
4. `2024_players_details.csv` — Player profiles

---

## Folder Structure

```
IPL-Analytics/
├── data/
│   ├── Ball_By_Ball_Match_Data.csv
│   ├── Match_Info.csv
│   ├── teams_info.csv
│   └── 2024_players_details.csv
├── notebooks/
│   ├── 1_Match_Summary.ipynb
│   ├── 2_Batting_Impact.ipynb
│   ├── 3_Bowling_Death_Over.ipynb
│   ├── 4_All_Rounder_Impact.ipynb
│   └── 5_ML_Match_Prediction.ipynb
├── charts/
│   ├── overwise_run_rate.png
│   ├── top_death_over_bowlers.png
│   └── top_all_rounders_impact.png
├── README.md
└── requirements.txt
```

---

## Project Modules

### 1. Match Summary

* Summarized runs, wickets, and run rates per innings and per over.
* Generated charts such as **over-wise run rate comparison**.
* Insights included team performance trends and chasing vs. defending outcomes.

### 2. Batting Impact Analysis

* Computed runs, balls faced, strike rate, and dismissals for all players.
* Highlighted top batters and their contribution to match outcomes.
* Visualizations show **top performing batters** by runs and strike rate.

### 3. Bowling Impact & Death Overs

* Focused on **overs 16–20** (death overs) to identify impactful bowlers.
* Metrics: economy rate, wickets, runs conceded.
* Visualized **top death-over bowlers**.

### 4. All-Rounder Impact Score

* Combined batting and bowling metrics into a **custom impact score**:

  ```
  impact_score = (bat_runs * 0.4) + (strike_rate * 0.3) + (wickets * 20) - (economy * 10)
  ```
* Filtered for meaningful all-rounders (minimum balls faced/bowled).
* Visualized **top 10 all-rounders by impact score**.

### 5. Machine Learning: Match Winner Prediction

* Random Forest classifier trained on **pre-match features** only:

  * team1, team2
  * toss winner, toss decision
  * venue, city
* Target variable: whether team1 wins.
* Accuracy ≈ 46–50% (realistic for T20 cricket, reflects unpredictability).
* Feature importance highlights the influence of toss and venue.

---

## Key Insights

* Teams batting second win slightly more than teams batting first (~54% of matches).
* Toss winner advantage exists but is limited (~50% win rate).
* Death-over bowling is critical: top bowlers can significantly control match outcomes.
* Certain all-rounders contribute meaningfully in both batting and bowling, influencing match results.
* Machine learning confirms that **pre-match factors alone are weak predictors** of match outcomes.

---

## Charts

*![Over-wise Run Rate Comparison](charts/overwise_run_rate.png)
*![Top Death-Over Bowlers](charts/top_death_over_bowlers.png)
*![Top All-Rounders by Impact Score](charts/top_all_rounders_impact.png)

---

## Requirements

```text
pandas
numpy
matplotlib
scikit-learn
jupyter
```

---

## How to Run

1. Clone the repository:

```bash
git clone <your-repo-url>
cd IPL-Analytics
```

2. Install requirements:

```bash
pip install -r requirements.txt
```

3. Open Jupyter notebooks in `notebooks/` and run step by step.

## Notes

* This project uses **only pre-match data** for ML modeling.
* Accuracy below 50–55% is realistic for T20 cricket due to inherent unpredictability.
* Visualizations provide clear insights into player and team performance.
