# Netflix-Top10-Tableau-Dashboard
Python-cleaned Netflix Top-10 data + a Netflix-branded Tableau dashboard (movies, series, genres, countries) 


Turn Netflix’s public Top-10 CSVs into a polished, on-brand Tableau story.

**Live demo →** https://public.tableau.com/app/profile/anukriti.singh4823/viz/Tableau_final_17498533332510/Dashboard1 
*(opens in a new tab; best viewed on desktop)*

---

## 1 · Project Pitch
This repo shows the complete path from raw Netflix Top-10 CSVs to a fully interactive Tableau dashboard.  
All data-prep is done in Python (`pandas`), and the final workbook is styled in Netflix’s signature blacks and reds.

---

## 2 · Folder Structure
netflix-top10-tableau-dashboard/
├─ data/ # cleaned CSVs (<100 MB total)
│ ├─ weekly_clean.csv
│ ├─ country_clean.csv
│ └─ platforms_union.csv
├─ notebooks/
│ └─ Netflix_Clean.ipynb
├─ src/
│ └─ prep_netflix.py # end-to-end ETL script
├─ screenshots/
│ ├─ dashboard.png
│ └─ weekly_trend.png
├─ Netflix_Dashboard.twbx # finished Tableau workbook
├─ README.md
└─ LICENSE # MIT


---

## 3 · Data Sources
| File | Origin | Notes |
|------|--------|-------|
| `all-weeks-global.csv` | [top10.netflix.com](https://top10.netflix.com) | weekly global list & hours |
| `all-weeks-countries.csv` | Netflix | Top-10 per country |
| `netflix_full.csv` | Kaggle (IMDb scrape) | catalog + ratings |
| `movies_all.csv`, `shows_all.csv` | Kaggle (JustWatch) | Netflix/Hulu/Prime/Disney+ flags |

---

## 4 · Quick Start
### Requirements
```bash
python 3.10+
pip install pandas
# Tableau Public or Desktop installed

