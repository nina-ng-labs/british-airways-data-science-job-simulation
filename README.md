# British Airways Data Science Job Simulation

## Overview

This repository documents my work and key learnings from the **British Airways Data Science Job Simulation on Forage**, completed in August 2026.

The simulation included two practical business problems:

1. **Modeling lounge eligibility at Heathrow Terminal 3**
2. **Predicting customer booking behaviour**

The experience combined business assumptions, data analysis, predictive modeling, model evaluation, data visualization, and communication of analytical findings.

---

## Task 1 — Lounge Eligibility Modeling

### Objective

Estimate lounge eligibility at Heathrow Terminal 3 by translating business requirements and assumptions into a structured analytical model.

### Key Learnings

- Developed assumptions from an ambiguous business problem
- Translated business requirements into measurable inputs
- Structured data to support lounge eligibility analysis
- Considered how analytical assumptions affect operational planning
- Communicated methodology and findings for business stakeholders

### Skills Practiced

`Assumption Development` `Data Modeling` `Business Analysis` `Communication`

---

## Task 2 — Predicting Customer Booking Behaviour

### Objective

Build a machine learning model to predict whether a customer will complete a flight booking.

The dataset contained **50,000 customer booking records**.

### Exploratory Data Analysis

I explored booking behaviour across:

- Sales channel
- Trip type
- Purchase lead time
- Booking origin
- Extra baggage preference
- Preferred seat preference
- In-flight meal preference

### Selected EDA Findings

- Internet bookings had a higher completion rate than mobile bookings.
- Round-trip bookings had a higher completion rate than one-way and circle trips.
- Customers booking within 30 days of departure had the highest completion rate among the purchase-lead groups analysed.
- Malaysia had the highest completion rate among the ten largest booking origins by booking volume.
- Customers requesting ancillary services generally showed higher booking completion rates.

---

## Data Preparation

Categorical variables were converted into numerical features using **one-hot encoding**.

The target variable was:

`booking_complete`

The data was divided into:

- **80% training data**
- **20% testing data**

A stratified split was used to preserve the target-class distribution.

---

## Machine Learning

I trained a **Random Forest Classifier** to predict booking completion.

Random Forest was selected because it can:

- Capture nonlinear relationships
- Handle a large number of features
- Provide feature importance for model interpretation

Class weighting was used because completed bookings represented a minority of observations.

---

## Model Performance

| Metric | Result |
|---|---:|
| Test ROC-AUC | **0.793** |
| 5-Fold CV ROC-AUC | **0.786** |
| Accuracy | **0.83** |
| Precision — Completed Booking | **0.42** |
| Recall — Completed Booking | **0.38** |
| F1-score — Completed Booking | **0.40** |

Because the target variable was imbalanced, **accuracy alone was not sufficient** to assess model quality.

The cross-validation ROC-AUC scores were highly consistent after using shuffled stratified folds, suggesting stable ranking performance.

---

## Feature Importance

The strongest predictive signals identified by the Random Forest model were:

| Feature | Importance |
|---|---:|
| Purchase lead | **12.67%** |
| Length of stay | **10.43%** |
| Flight hour | **10.31%** |
| Booking origin — Australia | **5.27%** |
| Flight duration | **4.25%** |
| Number of passengers | **4.01%** |
| Booking origin — Malaysia | **3.28%** |

The results suggest that **booking timing and trip characteristics were among the strongest predictors of booking completion**.

> Feature importance represents predictive contribution and should not be interpreted as causation.

---

## Business Interpretation

The model demonstrated useful predictive ability, but identifying customers who actually complete a booking remained more difficult than identifying non-completers.

Rather than immediately using the model as an automated decision rule, it could be explored as a **customer ranking or targeting signal**.

Potential next steps include:

- Classification threshold tuning
- Alternative class-balancing approaches
- Additional feature engineering
- Comparison with alternative classification models
- Further validation before operational deployment

---

## Tools & Skills

### Technical

`Python` `Pandas` `scikit-learn` `Random Forest` `Machine Learning` `Data Modeling` `Data Visualization` `EDA` `Cross-Validation` `Feature Importance`

### Business

`Assumption Development` `Analytical Communication` `Business Interpretation` `PowerPoint`

---

## Key Takeaway

This simulation reinforced that predictive modeling is not only about training a machine learning algorithm.

A complete analytical workflow also requires:

**Business Problem → Assumptions → Data Exploration → Data Preparation → Modeling → Validation → Interpretation → Communication**

The most valuable part of the exercise was connecting model performance and feature importance back to a business decision.

---

## Certificate

**British Airways Data Science Job Simulation — Forage**

Completed: **August 24, 2026**

Practical tasks completed:

- Modeling lounge eligibility at Heathrow Terminal 3
- Predicting customer buying behaviour

---

## Disclaimer

This repository documents my personal learning and analysis from the Forage job simulation. Original simulation datasets and proprietary materials are not redistributed.
