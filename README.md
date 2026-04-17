# Fuel Efficiency Prediction
### Automotive Analytics & ML Regression

## Overview
A machine learning pipeline to predict vehicle fuel
efficiency (MPG) based on automotive attributes.
Built to help manufacturers optimize vehicle designs,
reduce costs, and improve competitive positioning
at the design stage — before physical prototyping.

Built as part of the BIA® Research Internship at
First Quadrant Labs. Project 5 of 6.

## Business Objective
- Predict MPG from automotive design attributes
- Identify highest-leverage design decisions for
  fuel efficiency improvement
- Compare performance across manufacturing regions

## Dataset
- **Source:** Auto MPG Dataset
- **Size:** 398 vehicles × 9 features
- **Period:** 1970–1982
- **Target:** `mpg` — Miles Per Gallon
- **Origins:** USA (1), Europe (2), Japan (3)

## Methodology
1. Data Loading & Inspection
2. Data Quality Assessment
   - Horsepower stored as string — converted to numeric
   - 6 missing values imputed with median
   - 0 duplicate records
3. Exploratory Data Analysis
   - Pearson correlation heatmap
   - Feature vs MPG scatter plots
   - MPG distribution analysis
   - Regional MPG boxplot comparison
4. Feature Engineering
   - Dropped car_name (identifier, no predictive value)
5. Model Development
   - Linear Regression (baseline)
   - Random Forest Regressor
   - Gradient Boosting Regressor
6. Model Evaluation — MAE, RMSE, R²
7. Overfitting Check — train vs test R² comparison
8. Feature Importance — Random Forest

## Model Results
| Model | MAE | RMSE | R² |
|---|---|---|---|
| Linear Regression | 2.255 | 2.863 | 0.848 |
| Gradient Boosting | 1.748 | 2.347 | 0.898 |
| **Random Forest** | **1.577** | **2.141** | **0.915** |

**Selected Model:** Random Forest Regressor
R² = 0.915 — explains 91.5% of variance in MPG

## Overfitting Check
| Model | Train R² | Test R² | Gap |
|---|---|---|---|
| Linear Regression | 0.814 | 0.848 | -0.034 |
| Random Forest | 0.981 | 0.915 | 0.066 |
| Gradient Boosting | 0.971 | 0.898 | 0.074 |

All gaps within acceptable range — no severe overfitting.

## Feature Importance
| Feature | Importance | Business Meaning |
|---|---|---|
| `displacement` | ~45% | Engine size is #1 driver |
| `weight` | ~15% | Heavier = less efficient |
| `cylinders` | ~12% | Engine configuration matters |
| `horsepower` | ~12% | Power output impacts consumption |
| `model_year` | ~11% | Newer cars are more efficient |
| `acceleration` | ~3% | Weak predictor |
| `origin` | ~1% | Captured by physical attributes |

## Regional Comparison
| Region | Median MPG |
|---|---|
| Japan | 31 MPG |
| Europe | 27 MPG |
| USA | 19 MPG |

## Key Findings
- Engine displacement alone accounts for ~45% of
  fuel efficiency prediction
- Reducing displacement and vehicle weight are the
  highest-leverage design decisions
- Japanese manufacturers consistently outperformed
  USA and Europe throughout 1970–1982
- Non-linear relationships dominate — tree-based
  models significantly outperform linear regression
- Model year captures regulatory and technological
  improvements over time

## Limitations
- Dataset spans 1970–1982 — may not generalize
  to modern vehicles, EVs, or hybrids
- 398 samples is relatively small
- Median imputation introduces slight bias in
  horsepower distribution

## Tech Stack
Python • Scikit-learn • Pandas • NumPy •
Matplotlib • Seaborn • Jupyter Notebooks

## Deliverables
- `Fuel_Efficiency.ipynb` — Full analysis pipeline
- `FuelEfficiency_Presentation.pptx` — Executive summary

## About
Part of a 6-month BIA® Research Internship at
First Quadrant Labs.
Project 5 of 6 — automotive analytics domain.
