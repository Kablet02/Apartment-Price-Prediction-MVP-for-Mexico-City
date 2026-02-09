# Mexico City Apartment Price Prediction MVP

## Overview

This project builds a **minimum viable machine learning model** to predict apartment prices in Mexico City. The goal is to demonstrate an end-to-end data science workflow—from raw data to a trained, interpretable model—using real estate listings and location-based features.

The project focuses on simplicity, interpretability, and practical modeling decisions rather than maximizing predictive accuracy.

---

## Problem Statement

Apartment prices in Mexico City vary significantly by size and location. Accurately estimating property values is challenging due to heterogeneous neighborhoods and incomplete listing information. This project explores whether a small set of structured features can produce a reasonable baseline price prediction.

---

## Data

The dataset consists of apartment listings from Mexico City. The data is filtered to properties located in **Distrito Federal**, limited to apartments below a defined price threshold to reduce extreme outliers.

Key preprocessing steps include:

* Filtering by property type and location
* Removing outliers in covered surface area
* Extracting latitude and longitude from raw location fields
* Engineering a borough feature from hierarchical location strings
* Dropping null-heavy, high-cardinality, and multicollinear columns

---

## Features

The final model uses the following features:

* Covered surface area (m²)
* Latitude
* Longitude
* Borough (one-hot encoded)

These features were selected to balance predictive signal with model simplicity.

---

## Modeling Approach

A **Ridge regression** model is trained using a scikit-learn pipeline that includes:

* One-hot encoding for categorical features
* Imputation for missing values
* Regularized linear regression for stability and interpretability

Model performance is evaluated using **Mean Absolute Error (MAE)** and compared against a mean baseline model.

---

## Results

The trained model outperforms the baseline by a meaningful margin, indicating that size and location capture real price signal. Coefficient analysis shows strong effects from surface area and borough-level location, highlighting the importance of neighborhood in price formation.

---

## Limitations

* Borough-level location is coarse and masks intra-neighborhood variation
* Property quality features (amenities, age, parking) are not included
* Predictions should be interpreted as approximate averages, not appraisals

---

## Future Improvements

* Add finer-grained location data (colonia level)
* Include property attributes such as bedrooms and amenities
* Explore nonlinear or tree-based models

---

## Purpose

This project is intended for **learning, experimentation, and portfolio demonstration**, showcasing practical data science fundamentals and model interpretability.

---

