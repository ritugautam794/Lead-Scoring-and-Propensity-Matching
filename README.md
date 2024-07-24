# Lead-Scoring-and-Propensity-Matching

## Introduction
This repository explores lead scoring and propensity score matching to evaluate and optimize marketing strategies. It involves preprocessing lead data, scoring leads based on conversion likelihood, and applying propensity score matching to compare treatment and control groups effectively.

## Problem Statement
An education organization offers online courses to industry professionals. On any given day, many professionals who are interested in these courses visit the website and browse through the offerings.The courses are promoted on various websites and search engines, such as Google. When individuals arrive at the website, they may browse courses, fill out a form, or watch videos.

When individuals complete a form providing their email address or phone number, they are classified as leads. Additionally, leads are also acquired through past referrals.Once leads are obtained, the sales team reaches out through calls, emails, etc. During this process, some leads are converted into paying customers, while most are not. The typical lead conversion rate is around 30%.

Although a significant number of leads are generated, the conversion rate remains low. For example, if 100 leads are acquired in a day, only about 30 are converted. To enhance this process, the organization aims to identify the most promising leads, also known as ‘Hot Leads.’ By successfully identifying these leads, the conversion rate is expected to improve, as the sales team will concentrate more on high-potential leads rather than contacting all leads indiscriminately. 

## Data Collection: 
A dataset of leads with approximately 9,000 data points has been provided. Various attributes, such as Lead Source, Total Time Spent on Website, Total Visits, and Last Activity, are included in the dataset, which may or may not influence the likelihood of lead conversion. The target variable, 'Converted,' indicates whether a lead was converted, with 1 representing conversion and 0 representing no conversion.

Additionally, attention should be given to the categorical variables present in the dataset. A level called 'Select' appears in many of these categorical variables and should be considered as a null value, requiring appropriate handling.

## Lead Conversion Process 
![image](https://github.com/user-attachments/assets/df8fc8a4-9e3b-4d8f-a59e-7de662e3e97a)

A typical lead conversion process can be represented using the above funnel. As can be observed, a large number of leads are generated in the initial stage (top), but only a few of these leads result in paying customers at the bottom.

In the middle stage, it is necessary to nurture the potential leads effectively (i.e., by educating them about the product, maintaining constant communication, etc.) to achieve a higher lead conversion rate.

X Education has tasked you with selecting the most promising leads—those most likely to convert into paying customers. A model needs to be developed to assign a lead score to each lead, where a higher lead score indicates a higher likelihood of conversion, and a lower lead score indicates a lower likelihood of conversion.

The CEO has specified a target lead conversion rate of approximately 80%


## Exploratory Data Analysis

- In the exploratory data analysis (EDA) phase, our primary objective is to understand the growth potential of our customers. We analyze various aspects such as the countries from which leads are generated, the percentage of leads converting from different industries, and the distribution of leads across various sources. Additionally, we examine which channels yield higher conversion rates for different types of leads. This comprehensive analysis helps in identifying trends and patterns that could inform strategies to optimize lead generation and conversion.
- Next, we evaluate how leads spend time across various channels and analyze the conversion rates associated with this engagement. We also investigate conversion patterns based on occupation and compare asymmetrical profile scoring to understand its impact on conversion likelihood. This analysis helps in identifying key factors that influence lead conversion and refining strategies to improve overall efficiency.
- For each channel, we create a matrix that includes metrics such as total leads, leads converted, profit, ROI, revenue, and marketing spend. This detailed matrix allows us to assess the performance of each channel comprehensively and make data-driven decisions to optimize lead generation and conversion strategies.


![image](https://github.com/user-attachments/assets/1185c745-a6f3-4c7d-8e13-b0ac6e7d6531)

![image](https://github.com/user-attachments/assets/2a41f758-328e-4b7c-ad04-60a92f3364bd)

![image](https://github.com/user-attachments/assets/827a3e62-ffea-4c14-a9ae-a045501fb80a)

## Model Building Process

The model-building process for logistic regression involves preparing the data through feature selection and cleaning, splitting it into training and testing sets, and then fitting the model to the training data to estimate feature coefficients. The model is evaluated on the testing set using metrics such as accuracy and ROC-AUC score. Logistic regression is chosen for its interpretability, as it provides clear insights into the relationship between features and the target variable through its coefficients, making it easier to understand the influence of each feature on the outcome. This simplicity and clarity make it a preferred choice when understanding model predictions is essential.

![image](https://github.com/user-attachments/assets/ed3d0743-6b89-442c-8202-5a3198eab6aa)

## Feature Importance
For feature importance, we highlight the top 10 and bottom 10 features based on their impact on the model’s predictions. The top 10 features are those with the most significant positive or negative coefficients, indicating their strong influence on the target variable. Conversely, the bottom 10 features have minimal impact, either because they have small coefficients or their effects are less pronounced. By showcasing these extremes, we provide a clear view of which features are most and least influential, helping to focus on key drivers and refine the model for better performance.
![image](https://github.com/user-attachments/assets/787fe02b-1b70-4daa-93a4-2f7baab47f7e)

## Propensity Score Matching 

Propensity score matching is used to compare conversion rates between two lead sources: 'Google' and 'Direct Traffic'.The propensity score is the predicted probability that a given lead comes from the 'Google' source rather than 'Direct Traffic'. These scores help match leads from both sources with similar characteristics.

- Objective: The goal is to determine the effect of the lead source (either 'Google' or 'Direct Traffic') on conversion rates while controlling for other variables.
- Data Preparation: The dataset is prepared by encoding lead sources into binary form: 'Google' as 1 and 'Direct Traffic' as 0. This binary encoding is necessary for logistic regression, which is used to calculate propensity scores.
- Logistic Regression: A logistic regression model is fit using the lead source as the dependent variable and other features as independent variables.
  

Matching Process: Using the PsmPy library, nearest neighbor matching is performed. Each lead from the 'Google' group is matched to a lead from the 'Direct Traffic' group with a similar propensity score within a specified caliper (0.2 in this case). This ensures that the matched leads are comparable.
Balance Assessment:After matching, the dataset should be balanced regarding covariates between the two groups, reducing the confounding effects.
Visualization by Plots:The plots are generated to assess and visualize the quality of the propensity score matching process and its impact on conversion rates.


Purpose of Propensity Score Matching
- Causal Inference: PSM helps in estimating causal effects in observational studies by mimicking randomized controlled trials. By matching similar leads, the analysis isolates the impact of the lead source on conversion rates.
- Bias Reduction: Balancing covariates between groups reduces selection bias and confounding, leading to more reliable estimates of the lead source effect.

![image](https://github.com/user-attachments/assets/6d0cda07-664b-4323-bf7b-fd16f1997af1)
![image](https://github.com/user-attachments/assets/87ad88be-5b83-4307-8d52-3a160076987c)
![image](https://github.com/user-attachments/assets/99cf5f63-ccc2-40a9-b755-7d67e24e1e4a)

## Summary
This strategy focuses on enhancing lead generation and sales effectiveness by measuring and optimizing return on investment (ROI) across marketing channels. By using logistic regression, the project identifies key drivers of lead conversion and quantifies the incremental revenue impact of different channels. This enables informed decision-making and a strategic approach to improving conversion rates.

Through the application of association rule models, the strategy uncovers feature combinations that significantly boost conversion chances, guiding an optimized budget allocation to maximize ROI and profitability. Additionally, by replacing ineffective lead scoring systems with predictive analytics, the strategy prioritizes high-potential leads for sales teams, ensuring resource allocation is both efficient and effective. This approach ultimately aims to attract higher-quality leads and enhance overall sales productivity.


















