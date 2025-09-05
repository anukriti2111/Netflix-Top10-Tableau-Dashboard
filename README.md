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
```text
Netflix-Top10-Tableau-Dashboard/
├─ data/
│  ├─ clean/
│  │  ├─ global_weekly_clean.csv
│  │  ├─ most_popular_clean.csv
│  │  ├─ all_weeks_by_country_clean.csv
│  │  ├─ netflix_full_clean.csv
│  │  ├─ movies_all_enriched.csv
│  │  └─ shows_all_enriched.csv
│  └─ raw/                      # (optional) raw source CSVs
├─ tableau/
│  ├─ Netflix_Dashboard.twb     # linked workbook (small)
│  └─ Netflix_Dashboard.twbx    # packaged (may be large)
├─ screenshots/
│  ├─ dashboard.png
│  └─ weekly_trend.png
├─ notebooks/
│  └─ Netflix_Clean.ipynb
├─ src/
│  └─ prep_netflix.py
├─ docs/
│  └─ report.pdf
└─ README.md
```


---

## 3) Data Files in `/data/clean`
| File | What it contains |
|---|---|
| `global_weekly_clean.csv` | Weekly global Top-10 with hours viewed |
| `most_popular_clean.csv` | Most-popular titles (first 28 days hours) |
| `all_weeks_by_country_clean.csv` | Country-level Top-10 coverage |
| `netflix_full_clean.csv` | Catalogue + IMDb ratings/votes, genres |
| `movies_all_enriched.csv` | Movie availability by platform |
| `shows_all_enriched.csv` | Show availability by platform |

**Join key used in Tableau:** `Title_key` (or `Show Title Key`) – lowercase/trimmed titles.

---

## 4) Rebuilding in Tableau (quick)
1. **Connect → Text file** and add the six CSVs from `/data/clean`.
2. Rename logical tables: *Catalogue*, *Weekly*, *CountryWeekly*, *Popular28*, *Movies*, *Shows*.
3. (Optional) **Union Movies + Shows** → **Platforms**.
4. Create relationships:
   - Catalogue ↔ Weekly : `Title_key` ↔ `Show Title Key`
   - Catalogue ↔ CountryWeekly : `Title_key` ↔ `Show Title Key`
   - Catalogue ↔ Popular28 : `Title_key` ↔ `Show Title Key`
   - Platforms ↔ Weekly : `Title_key` ↔ `Show Title Key`

---

## 5) Calculated Fields (used in the viz)
- **Is Latest Week (Wk)**: `[Week] = { FIXED : MAX([Week]) }`  
- **Country Title Count**: `COUNTD([Show Title Key])`  
- **IMDb Votes (k)**: `ZN([imdbNumVotes]) / 1000`  
- **Platform Count**: `[Netflix] + [Hulu] + [Prime Video] + [Disney+]`

## 6) Credits
Netflix Top-10 data · IMDb ratings · Platform availability (Kaggle/JustWatch).  
Built with Tableau Public and Python/pandas.

