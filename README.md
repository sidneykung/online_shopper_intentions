# Online Shopper Purchase Intentions

```diff
Please note that this repository is incomplete and requires revision.
```

![banner](./visualizations/banner.jpg)

## Overview

The `online_shoppers_intention.csv` includes 12,330 sessions of online traffic to an unknown website over the period of a year. The column `Revenue` contains a True or False value that displays whether or not a website viewer purchases the product. This serves as the target variable for the classification problem. Using the other columns provided, we can create a classification model that can predict whether a site visitor will purchase the product. The company can use this model for future use.

The primary evaluation metric will be Recall because it indicates the amount of true positives that the model predicts. In this business context, false negatives are intolerable because that would inaccurately represent sales. We will also be looking at F1 score and AUC score because they have a direct relationship with Recall; especially AUC as it predicts the probability of true positives.

## Primary Business Problem

**What are the areas of opportunity to increase conversion among people who visit the website?**

![class](/visualizations/class_imbalance.png)

From the distribution of `Revenue` in this dataset, it's clear that 85% of people who visited the website that year did not convert to a customer. To solve this problem, we'll investigate what factors impact this decision.

## Business Questions

1. How does the number of visitors differ each month?
2. Do returning visitors have a higher revenue than one-time visitors?
3. What feature has the highest influence on revenue?

## Data & Methods

This project uses the [Online Shoppers Purchasing Intention Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset#) from the UCI Machine Learning Repository.

The research study gathered data from each session of website traffic over the 1-year period. The `Revenue` column was used as the target variable in this classification project. Below is a description of each column in the original dataset.

| Column Name | Description |
|-|-|
| **Administrative** | Administrative Page Value |
| **Administrative_Duration** | Duration in Administrative Page |
| **Informational** | Informational Page Value |
| **Informational_Duration** | Duration in Informational Page |
| **ProductRelated** | Product Related Page Value |
| **ProductRelated_Duration** | Duration in Product Related Page |
| **BounceRates** | Visitors who enter the site from that page and leave withrrrrrr visiting any other pages. |
| **ExitRates** | Calculated with all page views before exiting the website. |
| **PageValues** | Average value for a web page that a user visited before completeing an e-commerce transaction. |
| **SpecialDay** | Promximity to site visit to specific special day (e.g. Mother's Day, Valentine's Day) in which the sessions are more likely to be finalized with transaction. |
| **Month** | Month of the year |
| **OperatingSystems** | Operating system used |
| **Browser** | Internet browser used |
| **Region** | Region of the user |
| **TrafficType** | Traffic Type |
| **VisitorType** | Returning visitor or not |
| **Weekend** | Weekend or not |
| **Revenue** | Whether revenue was generated or not, as True or False |

## Results

![months](/visualizations/num_visitors.png)

- Promote the site during these peak months, focusing on spring up until early summer.

![visitors](./visualizations/visitor_types.png)

- Because a majority of purchasers are returning visitors, focus advertising efforts towards people who have already viewed the site to encourage them to return and convert to a customer.

![revenue](./visualizations/target_correlation.png)

- Since Page Value is a metric goal set by the company, this is the most crucial feature to focus on. Because the higher the page value, the higher the chance that they'll transact, meaning they viewed more pages.

## Final Model Performance

![metrics](/visualizations/final_metrics.png)

The final model will be the Decision Tree with `max_depth=3` and `class_weight=balanced`. Even though it had a worse recall the the RFECV model, this one is not as overfit. Therefore, it is ideal for testing on unseen data.

We tried performing grid search with cross validation to optimize other hyperparameters, but they perform almost exactly the same as this model.

## Next Steps
1. Collect more data, but include a legend for categorical variables to promote interpretability.
2. Webscrape similar data from other e-commerce stores within the industry to see how the model performs with that blind data.
3. A/B Testing the web design of the prominence of Administrative and Informational page links to increase length of user session.

## Repository Contents

```bash
.
├── EDA                                # contains EDA process
├── data                               # contains data files
├── models                             # contains model iterations
├── visualizations                     # contains visualizations and local images
├── README.md                          # public-facing preview
├── business_insights.ipynb            # notebook with final visualizations that answer the business problems
├── final_model.ipynb                  # notebook with iteration process for final model
└── presentation.pdf                   # slide deck

```

## For More Information

- Contact Sidney Kung at [sidneyjkung@gmail.com](mailto:sidneyjkung@gmail.com)

**Let's connect!**

<a href="https://www.linkedin.com/in/sidneykung/" target="_blank"><img alt="LinkedIn" src="https://img.shields.io/badge/linkedin-%230077B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white" /></a> <a href="https://twitter.com/sidney_k98" target="_blank"><img alt="Twitter" src="https://img.shields.io/badge/twitter-%231DA1F2.svg?&style=for-the-badge&logo=twitter&logoColor=white" /></a>
