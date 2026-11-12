# Netflix Data Analysis using Python

Project work for the **Auspify Technologies – Data Analysis Using Python** internship (4-week programme).
The project cleans and analyses a Netflix catalogue dataset (8,790 raw records, titles added up to September 2021) and turns it into business insights.
Built to run in **Google Colab** (also works in local Jupyter).

## Project structure (in Google Drive)

```
My Drive/
└── Netflix_Analysis/
    ├── Dataset.csv                                  <- raw data (you upload this)
    ├── netflix_cleaned.csv                          <- created by Task 1
    ├── Task1_Data_Cleaning_Preparation.ipynb
    ├── Task2_Content_Type_Analysis.ipynb
    ├── Task3_Country_Wise_Analysis.ipynb
    ├── Task4_Trend_Analysis_Release_Year.ipynb
    ├── Task5_Content_Rating_Genre_Analysis.ipynb
    ├── Task6_Business_Insights_Report.ipynb
    └── outputs/                                     <- charts, tables, HTML report (created automatically)
```

## How to run in Google Colab

1. In Google Drive, create a folder named **`Netflix_Analysis`** and upload `Dataset.csv` plus the six `.ipynb` notebooks into it.
2. Open a notebook: go to [colab.research.google.com](https://colab.research.google.com) -> **File -> Open notebook -> Google Drive** tab, and pick the notebook from `Netflix_Analysis`.
3. Run the first code cell (**Google Colab / Drive setup**). Click **Connect to Google Drive** and **Allow** when the pop-up appears. It should print `Working folder: /content/drive/MyDrive/Netflix_Analysis`.
4. **Run Task 1 first** (**Runtime -> Run all**). It creates `netflix_cleaned.csv` in the same Drive folder.
5. Open and run the other task notebooks the same way, in any order. Each one reads `netflix_cleaned.csv` from the Drive folder and saves its charts to `outputs/`.

Colab already includes pandas, NumPy, Matplotlib, Seaborn and Plotly, so there is nothing to install.

**Troubleshooting**
* `FileNotFoundError: Dataset.csv` / `netflix_cleaned.csv` -> the file is not in `MyDrive/Netflix_Analysis`, or the setup cell wasn't run first.
* Something looks stale or broken -> **Runtime -> Restart session**, then **Runtime -> Run all**.
* Session disconnected -> re-run the setup cell and then the cells below it. Files in Drive are not lost.

*Running locally instead?* `pip install pandas numpy matplotlib seaborn plotly jupyter`, put everything in one folder, and run Task 1 first. The Colab setup cell does nothing outside Colab.

## Tasks completed

| Task | Level | Notebook | Main outputs |
|------|-------|----------|--------------|
| 1 | Easy | Data Cleaning & Preparation | `netflix_cleaned.csv`, cleaning log |
| 2 | Easy | Content Type Analysis Dashboard | Movie vs TV charts, summary |
| 3 | Medium | Country-Wise Content Analysis | Country ranking, regional view |
| 4 | Medium | Trend Analysis by Release Year | Yearly trends, growth rates (CAGR) |
| 5 | Advanced | Content Rating & Genre Analysis | Interactive Plotly charts (HTML) |
| 6 | Advanced | Business Insights Report | 4 dashboards + HTML report |

> Edit this table so it lists only the tasks you completed (4 of the 6 are required).

## Data preparation highlights (Task 1)

* Found **hidden missing values**: `"Not Given"` placeholders in `director` and `country` (invisible to `isna()`).
* Removed **duplicate records** that differed only by `show_id`; fixed stray whitespace.
* Converted `date_added` to a real date; split `duration` into `duration_min` (movies) and `seasons` (TV).
* Standardised `type`, `country`, `rating`; created `rating_group` (Kids / Older Kids / Teens / Adults / Not Rated).

## Key findings

*(Write your own summary here after running the notebooks - 4 to 6 bullet points per task you completed.)*

## Tools

Python - pandas - NumPy - Matplotlib - Seaborn - Plotly - Google Colab

## Notes and limitations

* The dataset is a catalogue snapshot (to Sept 2021): it counts titles, not viewing hours or revenue.
* 2021 is a partial year and is flagged in the charts.
* Interactive Plotly charts do not display in GitHub's notebook preview; open the saved `.html` files in `outputs/task5_rating_genre/` instead.
