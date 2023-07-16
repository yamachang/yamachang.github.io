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

![Figure 1](featured-image.jpg "Real Estate Prices Prediction") 

In this project, I developed a machine learning model to accurately predict transaction prices for real estate properties in New York State. Leveraging regression models and extensive data analysis, the goal was to achieve a model with a mean absolute error (MAE) below the project's win condition of $70,000.

The project involved comprehensive data cleaning, exploratory data analysis, and feature engineering to ensure high-quality input data for the models. Various regression algorithms, including Lasso, Ridge, Elastic Net, Random Forest, and Gradient Boosting Trees, were trained and evaluated for their prediction performance.

Through careful feature engineering and preprocessing techniques, such as standardization and outlier handling, the models demonstrated impressive performance in predicting real estate prices. The Random Forest model emerged as the top-performing model, achieving the highest R2 score and the lowest MAE among the evaluated models.

The project's outcomes have significant implications for the real estate industry, enabling more accurate and data-driven pricing strategies. The model can assist real estate investment firms in optimizing pricing decisions, assessing risks, and reducing costs associated with manual appraisals. The next steps involve deploying the winning model, continuous monitoring, incorporating external data sources, evaluating model robustness, and collaborating with stakeholders for further improvements.

To explore the project in detail, please visit the ML-real-estate-prediction GitHub repository.

<!--more-->

## 0 Overview & Workflow

{{< admonition tip "Problem that I tried to solve:" >}}
Can we build a model to better predict transaction prices of real estate prices?
{{< /admonition >}}

* Business Background
* Machine Learning Background
* Exploratory Data Analysis / Data Cleaning / Feature Engineering
* Predicting House Prices using Regression Models
* Takeaways and Next Steps

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

### Summary Statistics

**Preliminary analysis and visualizations were conducted to gain insights into the data. Here are some of the key findings:**

* **Histograms** were used to understand the distribution of variables and identify any sparse data.
  
<p align="center">
  <img src="plots/histogram.png" alt="Plot 1" style="width:800px;height:800px;">
</p>

* **Box plots** were employed to examine the relationship between categorical and numeric features. In general, it looks like single family homes are more expensive than apartments.

<p align="center">
  <img src="plots/boxplot.png" alt="Plot 2" style="width:600px;height:350px;">
</p>
  
* **The correlation matrix** was visualized to explore the relationships between numeric features.

<p align="center">
  <img src="plots/heatmap.png" alt="Plot 3" style="width:850px;height:750px;">
</p>

**Next, we aimed to perform data cleaning tasks, which involved **grouping sparse data** to mitigate overfitting and **checking for outliers**.**

* **Grouping sparse data**: For categorical features, we reduced the number of items in `exterior_walls` from 16 to 8, and in `roof` from 16 to 5.

<div style="display:flex; justify-content:center;">
  <img src="plots/bar-plot-walls.png" alt="Plot 4" style="width:500px;height:350px; margin-right: 10px;">
  <img src="plots/bar-plot-roof.png" alt="Plot 5" style="width:500px;height:350px; margin-left: 10px;">
</div>

* **Checking for outliers**: It looks like `lot_size` has a potential outlier as it has a long and skinny tail, and we decided to remove observations with `lot_size` greater than 500,000 sqft for outliers.

<p align="center">
  <img src="plots/violin-plot-lotsize.png" alt="Plot 6" style="width:500px;height:400px;">
</p>

<!--Please open the code block below to view the code for visualizing U.S. map here : -->

<!--```r
### Plotting!
        
```-->

## 4 Predicting House Prices using Regression Models

Regression analysis was chosen as the optimal approach for predicting continuous house prices based on multiple independent variables.

Prior to training the models, preprocessing was performed. Standardization, a common technique in machine learning, was applied to ensure all features were on the same scale. This involved subtracting means and dividing by standard deviations. The preprocessing step was included in cross-validation.

After splitting the data into training and test sets, the training set was used to train three types of regression models (Ridge, Lasso, and Elastic Net Regression) as well as two ensembling models (Random Forest and Gradient Boosting Trees).

Next, hyperparameters for each model were tuned accordingly before fitting the training model. For Lasso and Ridge regularized regression, the strength of the penalty was the most impactful hyperparameter. In the case of Elastic Nets, tuning was done for the alpha parameter, along with the addition of a new hyperparameter called `l1_ratio`. For Random Forest, the number of decision trees (`n_estimators`) and the maximum number of features each tree can choose from (`max_features`) were tuned. Lastly, for Gradient Boosting Trees, tuning was done for `n_estimators`, `learning_rate`, and `max_depth`.

The evaluation of the models is shown in the plot below:

<p align="left">
  <img src="plots/model-metrics.png" alt="Plot 7" style="width:300px;height:250px;">
</p>

Analyzing the metrics, we observed that Random Forest achieved the highest R2 score and the lowest MAE. While Gradient Boosting Tree showed the best holdout R2 score during cross-validation, Random Forest's performance was only slightly lower. Importantly, Random Forest met the win condition of the project with an MAE below $70,000.

In conclusion, let's visualize the performance of the winning model on the test set.

<p align="left">
  <img src="plots/performance.png" alt="Plot 8" style="width:500px;height:400px;">
</p>


## 5 Takeaways and Next Steps

The ML-real-estate-prediction project aimed to develop a model to predict transaction prices for real estate properties. By leveraging regression models and extensive data analysis, we successfully achieved a model with an MAE below the project's win condition of $70,000. Here are some key takeaways:

*Data Science Perspective*:

* Random Forest emerged as the top-performing model, showcasing the highest R2 score and lowest MAE.
* Careful feature engineering, including creating new features and grouping sparse classes, improved prediction performance.
* Preprocessing steps, such as standardization and outlier handling, addressed overfitting and ensured reliable generalization.

*Business Perspective*:

* Improved Pricing Strategy: Accurate predictions optimize pricing decisions, maximizing profits and competitiveness.
* Risk Mitigation: Accurate estimates aid in informed investment decisions, minimizing overpaying or undervaluing properties.
* Cost Reduction: Accurate predictions reduce the need for costly manual appraisals, streamlining operations.

*Next Steps*:

* Deploy the Winning Model: Deploy the trained Random Forest model for real-time price prediction.
* Continuous Model Monitoring: Regularly monitor and update the model with new data for sustained accuracy.
* Incorporate External Data: Explore incorporating economic indicators and demographic data for enhanced predictions.
* Evaluate Model Robustness: Conduct stress testing under different scenarios to ensure model performance.
* Collaborate with Stakeholders: Gather feedback and refine the model in collaboration with the REIT and industry professionals.

Implementing these next steps will further improve the accuracy and usefulness of the real estate price prediction model, enabling informed decisions and optimized property valuation processes.