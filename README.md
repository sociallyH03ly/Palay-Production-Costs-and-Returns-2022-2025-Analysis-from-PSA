# Comparative Assessment of Production Cost Structures Between Irrigated and Rainfed Palay Farming in the Philippines, 2022–2025

## Overview

This project compares the production costs of irrigated and rainfed (non-irrigated) palay farming in the Philippines using Philippine Statistics Authority (PSA) data for 2022–2025. It asks which expenses contribute most to total production cost, how the two farming systems differ, and whether rice production is becoming more expensive.

## Objectives

- Compare total cost, cost per kilogram and returns between irrigated and non-irrigated palay.
- Identify which expenses contribute most to production cost, and how the mix differs by farm type.
- Test whether farm type, year, cropping season and region explain differences in cost (ANOVA).
- Estimate the size of the irrigated cost premium after controlling for region, year and season (regression).

## Data

- **Source:** PSA OpenSTAT, *Palay: Average Production Costs and Returns by Type, Geolocation, Item, Cropping Season and Year, 2022–2025*.
- **Raw table:** 2,346 rows covering 3 palay types, 17 geolocations and 46 items.
- **Analysis panel:** 256 observations (irrigated and non-irrigated palay × 16 regions × 4 years × 2 cropping seasons).
- **Cost groups:** 36 itemized costs combined into 9 groups (seeds, fertilizer, pesticides, labor, land, machinery and fuel, irrigation fee, interest, other).
- **Missing values:** about 5.2% of cells, all in itemized sub-costs. These were kept as missing in the source and treated as zero within cost groups.
- **Derived variables:** implied yield (total cost ÷ cost per kg) and implied price (gross returns ÷ implied yield).
- **Assumption:** costs are taken to be in PhP per hectare, which is usual for these tables although the file does not state it.

## Methods

- **Paired comparison:** irrigated vs non-irrigated in the same region, year and season (paired t-test, Wilcoxon signed-rank test, Cohen's dz).
- **Cost contribution:** each group's share of mean total cost and of the irrigated-minus-non-irrigated cost gap.
- **ANOVA:** type II ANOVA with partial η², plus Kruskal–Wallis, Levene and Shapiro–Wilk checks, Tukey HSD for years, and Bonferroni-corrected tests of cost shares.
- **Regression:** OLS with region fixed effects, year and season dummies, and region-clustered standard errors (Models A–D).

## Key Findings

- **Irrigated costs more per hectare, less per kilogram.** About PhP 7,400 more per hectare (+14.7%), but PhP 14.27/kg against PhP 15.45/kg (−7.6%), because implied yield is about 25% higher.
- **Labor is the largest cost.** About 44% of total cost on both farm types, followed by fertilizer (~14%) and land (~13%). Together they account for about 78% of the irrigated cost premium.
- **Cost structures are similar.** After multiple-test correction, only the irrigation fee differs significantly in share.
- **Nominal cost per hectare rose modestly.** Up 3.9% (irrigated) and 5.0% (non-irrigated) from 2022 to 2025, after peaking in 2024. Cost per kilogram fell 16.7% and 2.6%.
- **The cost mix is shifting.** Fertilizer spending fell about 41% while labor rose about 26% and interest about 30%.
- **Location matters more than farm type.** Region explains the largest share of variation in total cost (partial η² = 0.67) and cost per kilogram (0.37).
- **Irrigation works through yield.** Irrigation lowers cost per kilogram through higher yield, not cheaper inputs.

## Recommendations

- Give priority to labor-saving practices and mechanization, since labor is the largest and fastest-growing cost.
- Promote efficient fertilizer use and monitor input prices for both systems.
- Provide region-specific support, since regional differences exceed the irrigation difference.
- Use farm-level data, inflation-adjusted costs and measured yields in future studies.

## Limitations

- Observations are published regional averages, not individual farms.
- Costs are nominal, with no inflation adjustment.
- Yield and price are derived and carry rounding error.
- Missing items were treated as zero inside cost groups, which may understate in-kind and permanent-employee costs.
- Imputed costs (family labor, rental value of owned land) are estimates, not cash outlays.
- With only 16 regions, clustered standard errors may be too optimistic, and normality and equal-variance assumptions are not fully met.
- Irrigated and rainfed areas differ in soil, rainfall and region, so the irrigated effect is an association, not a causal estimate.

## Tools

Python (pandas, statsmodels, scipy) in Google Colab, and Microsoft Excel.

## Repository Contents

- `Palay_Complete_Analysis` – Colab notebook (Part 1: exploratory analysis; Part 2: research analysis).
- `palay_research_results.xlsx` – exported result tables.
- `Palay_EDA_Excel` – Excel workbook reproducing the exploratory analysis with live formulas.
- Full report (PDF).

## Data Source

Philippine Statistics Authority (PSA), OpenSTAT.
