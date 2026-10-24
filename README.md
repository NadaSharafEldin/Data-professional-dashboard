# Data Professional Survey Dashboard

An interactive Power BI dashboard that analyzes a survey of data professionals: who they are, where they live, what they earn, which tools they prefer, and how happy they are in their roles.

## What the dashboard shows

| Visual | Insight |
|---|---|
| **Survey takers & average age** (cards) | How many people responded and their typical age |
| **Average Salary by Job Title** (bar chart) | Which data roles pay the most |
| **Favorite Programming Language** (stacked column) | Language preferences, broken down by job title |
| **Country of Survey Takers** (treemap) | Where respondents are located |
| **Happiness with Work/Life Balance** (gauge) | Average satisfaction score, out of 10 |
| **Happiness with Salary** (gauge) | Average satisfaction score, out of 10 |
| **Difficulty to Break Into Data** (donut chart) | How hard respondents found it to enter the field |

## How to open it

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
2. Download `Data Professional Dashboard.pbix` from this repository.
3. Open it in Power BI Desktop. The data is embedded, so no extra setup is needed.

## Data

- **[`data/data_professional_survey_cleaned.csv`](data/data_professional_survey_cleaned.csv)**: the 630 survey responses (26 columns) exactly as they feed the dashboard, after cleaning. Respondents are anonymous.
- **[`power-query/data_professional_survey.m`](power-query/data_professional_survey.m)**: the full Power Query script used to clean the raw survey export.

Cleaning steps applied in Power Query:

1. Removed unused tracking columns (Browser, OS, City, Country, Referrer).
2. Trimmed "Other (please specify)" answers down to their main category for job title, industry, country and programming language.
3. Split salary ranges such as `41k-65k` into a minimum and a maximum (in thousands of USD). The open-ended `225k+` bracket was capped at 225.
4. Calculated **Average Salary** as the midpoint of each range.

## Repository structure

```
├── Data Professional Dashboard.pbix   # the Power BI report
├── data/
│   └── data_professional_survey_cleaned.csv
└── power-query/
    └── data_professional_survey.m
```

## Skills demonstrated

- Data cleaning and transformation in **Power Query** (splitting multi-choice answers, deriving an average salary from salary ranges)
- Data modeling and aggregations (averages, counts, distinct counts)
- Dashboard design with cards, bar/column charts, a treemap, gauges and a donut chart
- Cross-filtering between visuals for interactive exploration

## Tools

- Microsoft Power BI Desktop
- Power Query (M)
