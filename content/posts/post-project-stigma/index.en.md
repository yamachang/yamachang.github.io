---
author: Yama Chang
authorLink: https://yama-chang.netlify.app/about/
categories:
- Projects
date: "2023-04-13T03:33:33+08:00"
description: "Developing Metrics for Structural-Level Discrimination: A Data Science Project Focused on LGBTQ+ Populations"
draft: false
images: []
lastmod: "2020-03-06T21:29:01+08:00"
lightgallery: true
resources:
- name: featured-image
  src: featured-image.jpg
- name: featured-image-preview
  src: featured-image-preview.jpg
tags:
- R
- Data Visualization
- Predictive Analysis
title: "Developing Metrics for Structural-Level Discrimination: A Data Science Project Focused on LGBTQ+ Populations"
toc:
  auto: false
weight: 1
---

In this data science project, I embarked on the challenge of quantifying discrimination using real-world data. Structural stigma, which encompasses discrimination embedded in societal-level conditions, cultural norms, and institutional policies, has a significant impact on LGBTQ+ individuals in the U.S. While established methods exist to measure individual and interpersonal stigma, quantifying structural stigma poses a unique challenge due to its complex macro-social nature.

To address this, I designed an approach using Confirmatory Factor Analysis, utilizing a variety of variables that represented both explicit and implicit attitudes specific to LGBTQ+ individuals from an open data set, Project Implicit. This allowed us to create an index of county-level structural stigma. The resulting factor, when visualized on a U.S. map, provides an illuminating representation of the structural stigma landscape across the country. It helps us better understand the macro-social context and pervasive challenges that LGBTQ+ populations in the U.S. encounter in their day-to-day lives.

<!--more-->

## 1 Overview

{{< admonition tip "Problem that I tried to solve:" >}}
Leveraging comprehensive open data sets from [Project Implicit](https://osf.io/y9hiq/), I was interested in exploring the feasibility of developing a metric that could encapsulate the macro-social context experienced by discriminated populations, such as the LGBTQ+ community in the U.S.
{{< /admonition >}}

## 2 Workflow

1. Import and preprocess the Sexuality IAT and Transgender IAT datasets from Project Implicit.
2. Conduct feature engineering to tailor indicators for the Confirmatory Factor Analysis (CFA).
3. Construct the CFA model using the preprocessed datasets.
4. Evaluate the model fit and make necessary adjustments to improve performance.
5. Generate a County-level Structural Stigma Index for each county using the refined model. Ensure the index follows a normal distribution.
6. Visualize the structural stigma landscape across U.S. counties by mapping the generated indices.

## 3 Data

Data for this project was sourced from the open-access repository of Project Implicit (https://osf.io/y9hiq/). We specifically utilized the most recent data, spanning from January to December 2022, with the aim of capturing current societal attitudes towards LGBTQ+. This was achieved by aggregating responses from two separate data sets — Sexuality IAT and Transgender IAT — where participants expressed their implicit and explicit attitudes towards the LGBTQ+ community. Importantly, the data included zip codes provided by the participants, enabling us to link the model-generated factor scores to the corresponding county-level structural stigma.

## 4 Visualization

After successfully quantifying structural stigma towards LGBTQ+ populations by creating a County-level Structural Stigma Index with a refined model, I visualized this landscape across U.S. counties using the generated indices.

I initially used the `urbnmapr` package to obtain comprehensive U.S. map data, including state and county shapefiles compatible with `ggplot2`. Then, I used the `geom_polygon()` function from the `ggplot2` package to create a detailed U.S. map visualization with regional boundaries.

The repository for this project is: https://github.com/yamachang/RISE_identity.git.

**This project is currently under preparation for journal submission. Once the preprint is submitted and published, I will update the visualization code below :(far fa-hand-point-down fa-fw)::**

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



