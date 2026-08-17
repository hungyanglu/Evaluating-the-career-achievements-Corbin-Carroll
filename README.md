# Evaluating the Career Achievements of Corbin Carroll

This repository contains player-analysis presentation materials and predictive statistical modeling research evaluating the career achievements and major-league trajectory of MLB star outfielder Corbin Carroll.


## 1. Motivation & Background

* **WBC Context**: Due to flexible eligibility rules for citizenship in the World Baseball Classic (WBC), Taiwanese-American MLB star prospect Corbin Carroll attracted widespread attention over his potential eligibility to represent Chinese Taipei.
* **MLB Performance**: In his 2023 rookie season, Carroll delivered a breakout performance, making the MLB All-Star Game as a starting outfielder, winning the National League Rookie of the Year award, and entering the NL MVP conversation.
* **Objective**: To examine the caliber of performance Carroll would bring to Chinese Taipei and introduce his technical attributes and potential career archetypes to Taiwanese baseball fans (using Statcast data cut off before the 2023 MLB All-Star Break).


## 2. Methods to Predict Career WAR

Below is the detailed summary of the predictive statistical framework and career WAR projection results from that paper:

### (1) Two-Dimensional Predictive Statistical Framework

#### Dimension 1: Career WAR & Longevity Forecasting
* **Methodology**: Deploys Direct Multi-Year Split Conformal Prediction and Locally Adaptive (Mondrian) Conformal Regression (LACP) combined with binary Active Retention Classification to directly forecast horizons $h \in \{1, 2, 3, 4, 5\}$, avoiding compounding error traps typical of traditional single-step recursive models.
* **Statistical Rigor**: Provides non-parametric prediction intervals backed by strict $90\%$ coverage guarantees.
* **Data Partition**: Utilizes an $80\%$ Training ($L_1$), $10\%$ Calibration ($L_2$), and $10\%$ Testing ($L_3$) player-level split to prevent data leakage across correlated season rows, evaluating Linear Regression, Neural Network (MLP), and XGBoost models.

#### Dimension 2: Characteristic Metric Space & Peer Matching
* Constructs a high-dimensional feature space using Statcast tracking variables (`Swing%`, `Contact%`, `O-Contact%`, `Barrel%`, `Max EV`, `Sprint Speed`, `OAA/Inning`) and executes a Mahalanobis distance pipeline to match historical player comparables.


### (2) Specific Career WAR Projection Results

| Metric / Dimension | Projected Output & Trend |
| :--- | :--- |
| **Active Career Longevity** | Projected 15–16 active seasons in MLB (with a 10–14 year high-output prime window). |
| **Rookie & Early Phase** | 2022 (1.4 WAR) $\rightarrow$ 2023 (5.4 WAR), establishing an elite cornerstone foundation. |
| **Mid-20s Prime Phase** | Stable annual production ranging between 3.86 WAR and 5.14 WAR. |
| **Late Career Aging Curve** | Gradual output decline after age 30, tapering down to 1.15 to 2.57 WAR per season. |
| **Cumulative WAR Milestones** | Surpasses 20 WAR by Year 5 and crosses 40 WAR by Year 12. |
| **Total Accumulated Career WAR** | Eventually stabilizes between 44.0 and 49.0 total WAR (mean estimate $\approx 47.8\text{--}48.5$ WAR; within a $90\%$ confidence interval range of 33.15 to 55.79 WAR). |


### (3) Historical Player Comparables & Trajectories

The study identifies three historical benchmarks representing low-, mid-, and high-standard outcomes:

* **Draft Comp vs. Reality**: Scouting reports initially drew amateur comparisons to Andrew Benintendi, but Carroll's raw power, exit velocity (EV), and defensive range (OAA) far outperformed Benintendi's major league profile.
* **Low-Standard Benchmark (Jason Heyward)**: Shares advanced plate discipline, high contact metrics, elite sprint speed, and Gold Glove-caliber outfield defense.
* **Mid-Standard Benchmark (Hanley Ramirez)**: Combines elite contact skills with high exit velocities, multi-hit consistency, and impactful baserunning value.
* **High-Standard / Ceiling Benchmark (Francisco Lindor)**: Pairs a high-contact/low-strikeout bat with 30/30-level power-speed production and elite defense, representing Carroll's absolute MVP-tier ceiling.
