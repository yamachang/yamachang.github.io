---
author: Yama Chang
authorLink: https://yama-chang.netlify.app/about/
categories:
- Projects
date: "2023-06-30T03:33:33+08:00"
description: "A comprehensive ML project leveraging regression models to accurately predict real estate prices in New York state."
draft: false
images: []
lastmod: "2020-07-16T21:29:01+08:00"
lightgallery: true
resources:
- name: featured-image
  src: featured-image.jpg
- name: featured-image-preview
  src: featured-image-preview.jpg
tags:
- Python
- Data Visualization
- Predictive Analysis
- Machine Learning
title: "Predicting Real Estate Prices in New York State: A Machine Learning Approach"
toc:
  auto: false
weight: 1
---

In this project, I developed a machine learning model to accurately predict transaction prices for real estate properties in New York State. Leveraging regression models and extensive data analysis, the goal was to achieve a model with a mean absolute error (MAE) below the project's win condition of $70,000.

The project involved comprehensive data cleaning, exploratory data analysis, and feature engineering to ensure high-quality input data for the models. Various regression algorithms, including Lasso, Ridge, Elastic Net, Random Forest, and Gradient Boosting Trees, were trained and evaluated for their prediction performance.

Through careful feature engineering and preprocessing techniques, such as standardization and outlier handling, the models demonstrated impressive performance in predicting real estate prices. The Random Forest model emerged as the top-performing model, achieving the highest R2 score and the lowest MAE among the evaluated models.

The project's outcomes have significant implications for the real estate industry, enabling more accurate and data-driven pricing strategies. The model can assist real estate investment firms in optimizing pricing decisions, assessing risks, and reducing costs associated with manual appraisals. The next steps involve deploying the winning model, continuous monitoring, incorporating external data sources, evaluating model robustness, and collaborating with stakeholders for further improvements.

To explore the project in detail, please visit the ML-real-estate-prediction GitHub repository.

<!--more-->

## 0 Overview

{{< admonition tip "Problem that I tried to solve:" >}}
Can we build a model to better predict transaction prices of real estate prices?
{{< /admonition >}}

## 1 Business Background

A leading Real Estate Investment Trust (REIT) in a small county in New York state embarked on a data-driven initiative to modernize their property valuation process. They sought to develop a model that accurately predicts fair transaction prices before property sales, keeping pace with market trends. As a data science consultant, I was tasked with creating a model capable of predicting transaction prices with an average error of less than $70,000. To facilitate this task, the REIT provided an unused dataset from 2016 containing transaction prices of properties in their area of operation.

## 2 Machine Learning Background

* The dataset has 1883 observations in the county where the REIT operates.
* Each observation is for the transaction of one property only.
* Each transaction was between `$200,000` and `$800,000`.
* Target Variable: Transaction Price
* Input Features: 22 independent variable including Public records for the property, Property characteristics, Location convenience scores, Neighborhood demographics, Schools
* Machine Learning Task: Regression
* Win Condition: Mean Absolute Error (MAE) < $70,000

## 3 Exploratory Data Analysis / Data Cleaning / Feature Engineering

I performed data cleaning, exploratory data analysis, and feature engineering using the [Real Estate Prediction - Data Cleaning, Exploratory Analysis, & Feature Engineering.ipynb](https://github.com/yamachang/ML-real-estate-prediction/blob/main/README.md) notebook. The process involved various plots to assess distributions, segmentations, correlations, and outliers. Data cleaning tasks included dropping unwanted observations, rectifying structural errors, eliminating outliers, and addressing missing data. Feature engineering encompassed creating new features, grouping sparse classes, and creating dummy variables for categorical features.

The repository for this project is: https://github.com/yamachang/ML-real-estate-prediction.git.

<!--Please open the code block below to view the code for visualizing U.S. map here : -->

<!--```r
### Plotting!
        
```-->

![Figure 1](featured-image.jpg "Figure 1. 2022 U.S. County-Level Structural Stigma Index Map: Highlighting LGBTQ+ Discrimination") 


## 5 Conclusion

In undertaking this data science project, I gained valuable insights into the quantification of discrimination, particularly the attitudinal structural stigma faced by the LGBTQ+ community at the county level in the U.S. This project represents a unique approach, utilizing open, real-world data and applying data science techniques such as Confirmatory Factor Analysis. Through this process, I discovered that existing research often fails to capture the diversity within larger geographical regions, emphasizing the significance of local analyses.

One of the key findings of this project was the substantial variation in attitudes within the same state. This highlights the importance of delving into local contexts to understand the nuanced dynamics of structural stigma. By employing innovative visualization techniques, I transformed complex data into a comprehensive U.S. map, making the patterns and disparities in attitudes easily interpretable.

Engaging in this project has deepened my understanding of the pivotal role data science plays in uncovering and addressing social issues. By shedding light on the attitudinal structural stigma experienced by the LGBTQ+ community, this project serves as a testament to the power of data-driven insights and their potential for meaningful real-world applications.

Through the creative design and successful execution of this project, I have not only expanded my skill set in data science but also gained a profound appreciation for the importance of diversity, inclusion, and the need to challenge structural discrimination. This project has further solidified my commitment to leveraging data science as a catalyst for positive change in society.



