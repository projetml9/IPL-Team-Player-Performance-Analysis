# IPL-Team-Player-Performance-Analysis

# IPL Team & Player Performance Analysis

A data analysis project on the Indian Premier League (IPL) covering team results, player statistics, toss and venue effects, phase-wise scoring, and match outcome prediction, using ball-by-ball data from 2008 to 2026.

## Table of Contents
- [Overview](#overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Project Structure](#project-structure)
- [Tools and Technologies](#tools-and-technologies)
- [How to Run](#how-to-run)
- [Analysis Performed](#analysis-performed)
- [Key Findings](#key-findings)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Author](#author)

## Overview
This project analyses approximately 295,000 deliveries across 1,243 IPL matches. It cleans the raw data, builds team and player statistics, visualises the results, and trains machine learning models to predict match winners. The work was carried out in Python using Google Colab.

## Objectives
- Evaluate team performance through win percentage, season-wise results and head-to-head records.
- Analyse the impact of the toss and the venue on match outcomes.
- Identify leading batters and bowlers using runs, strike rate, average, wickets and economy rate.
- Compare scoring rate and wicket rate across the Powerplay, Middle and Death overs.
- Build and evaluate models that predict match winners.

## Dataset
- **File:** `IPL.csv` (ball-by-ball data, one row per delivery)
- **Source:** [add the link to your dataset source, e.g. Kaggle]
- **Coverage:** 2008 to 2026 seasons, 1,243 matches
- **Key columns:** `match_id`, `date`, `innings`, `batting_team`, `bowling_team`, `over`, `batter`, `bowler`, `runs_batter`, `runs_bowler`, `runs_total`, `valid_ball`, `wicket_kind`, `player_out`, `toss_winner`, `toss_decision`, `venue`, `match_won_by`, `player_of_match`

> The dataset file is not included in this repository because of its size. Download it from the source above and place it in the project folder.

## Project Structure
```
ipl-analysis/
├── IPL_Analysis.ipynb     # Main notebook with all code and charts
├── IPL.csv                # Dataset (download separately)
├── outputs/
│   ├── team_stats.csv
│   ├── batting_stats.csv
│   └── bowling_stats.csv
└── README.md
```

## Tools and Technologies
- Python 3
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Google Colab

## How to Run
1. Open `IPL_Analysis.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Run the cells in order from top to bottom.
3. When prompted by the upload cell, select `IPL.csv`.
4. The summary tables are saved as CSV files at the end of the notebook.

To run locally instead, install the dependencies and replace the Colab upload cell with a direct file path:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

## Analysis Performed
| Section | Description |
|---|---|
| Data cleaning | Standardised team and venue names, created a season column, removed super overs and no-result matches |
| Team analysis | Matches played, wins and win percentage per team |
| Season analysis | Matches per season and the most successful team each year |
| Toss analysis | Toss win versus match win, and toss decision trends over time |
| Venue and head-to-head | Busiest grounds and a team-versus-team win matrix |
| Batting analysis | Runs, strike rate, average, boundaries and sixes |
| Bowling analysis | Wickets, economy rate and bowling average |
| Phase analysis | Run rate and wickets in Powerplay, Middle and Death overs |
| Player of the Match | Most awards by player |
| Prediction | Logistic Regression and Random Forest models for match winners |

## Key Findings
- **Teams:** Among franchises with 50 or more matches, Chennai Super Kings have the highest win rate (about 56%), followed by Mumbai Indians (about 54%).
- **Toss:** Toss winners won about 51.6% of matches, so the toss has only a small effect.
- **Toss decisions:** Captains have moved strongly towards fielding first, from a near-even split in 2008 to fielding in about 83% of matches in 2026. Teams that chose to field won about 54.7% of the time, against 45.3% for those that chose to bat.
- **Batting:** V Kohli is the leading run scorer (about 9,300 runs) and CH Gayle has hit the most sixes (357).
- **Bowling:** YS Chahal has taken the most wickets (233), while SP Narine combines a low economy rate (about 6.8) with over 200 wickets.
- **Phases:** The run rate is about 8.1 in the Powerplay, 7.95 in the Middle overs and 10.1 in the Death overs. Wickets fall roughly twice as often in the Death overs as in the other phases.
- **Prediction:** The models achieved about 51 to 54% accuracy, which is no better than always predicting that the chasing team wins (about 55%).

## Limitations
- The data contains no information on player form, pitch conditions, weather or team line-ups for individual matches, which limits the prediction models.
- Franchise name changes were merged where the team is the same, while Deccan Chargers and Gujarat Lions are kept separate from Sunrisers Hyderabad and Gujarat Titans.
- Tied and no-result matches are excluded from win statistics, and super overs are excluded from player statistics.

## Future Work
- Add features such as recent form, head-to-head record and venue-specific team record to improve prediction.
- Build an interactive dashboard using Streamlit or Power BI.
- Extend the analysis to individual player impact, such as performance in chases versus first innings.
