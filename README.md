# NFL Betting Odds Analysis: Can We Predict the Favorite Covering the Spread?
### Applied Data Analysis (STAT 5125) — University of Connecticut, Spring 2024

---

## Overview

This project investigates whether historical NFL betting odds data can predict if the **betting favorite will cover the point spread**. Using 20+ years of game data and four classification models, we evaluate the statistical signal available to bettors and analysts.

**Authors:** Giovanni Lunetta, Sam Lutzel
**Course:** STAT 5125 — Applied Data Analysis, University of Connecticut

---

## Research Question

> Can we predict whether the NFL betting favorite will cover the point spread?

---

## Data

- **Source:** Web-scraped from sportsoddshistory.com via `rvest`
- **Coverage:** NFL regular seasons 2002–2023 (~6,000+ games)
- **Key features:** Point spread, over/under, home/away, season, week, team matchup
- **Target variable:** Binary — did the favorite cover the spread? (1 = yes, 0 = no)

---

## Methods

Four classification models compared using 10-fold bootstrap cross-validation:

| Model | Implementation |
|---|---|
| Logistic Regression (MLE) | `glm()` in R |
| LASSO Logistic Regression | `glmnet` |
| K-Nearest Neighbors (k=10) | `class::knn()` |
| Random Forest | `ranger` |

**Primary evaluation metric:** ROC-AUC

---

## How to Run

**Prerequisites:**
```r
install.packages(c("tidyverse", "rvest", "glmnet", "ranger", "class", "pROC", "knitr"))
```

Open `submit.qmd` in RStudio and render with Quarto. Data files must be in the working directory.

---

## Repository Structure

```
.
├── submit.qmd                  # Main analysis (Quarto document)
├── Final Project/
│   └── final copy.qmd          # Final project submission
├── playoffs_2002_2020.csv      # Historical NFL game/odds data
└── README.md
```

---

## Authors

- **Giovanni Lunetta** — UConn MS Data Science
- **Sam Lutzel** — UConn MS Data Science
