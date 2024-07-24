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

![image](https://github.com/user-attachments/assets/1185c745-a6f3-4c7d-8e13-b0ac6e7d6531)

![image](https://github.com/user-attachments/assets/2a41f758-328e-4b7c-ad04-60a92f3364bd)

![image](https://github.com/user-attachments/assets/827a3e62-ffea-4c14-a9ae-a045501fb80a)

## Model Building Process
![image](https://github.com/user-attachments/assets/ed3d0743-6b89-442c-8202-5a3198eab6aa)
feature importance

![image](https://github.com/user-attachments/assets/787fe02b-1b70-4daa-93a4-2f7baab47f7e)

PROPENSITY MODELLING
![image](https://github.com/user-attachments/assets/6d0cda07-664b-4323-bf7b-fd16f1997af1)
![image](https://github.com/user-attachments/assets/87ad88be-5b83-4307-8d52-3a160076987c)
![image](https://github.com/user-attachments/assets/99cf5f63-ccc2-40a9-b755-7d67e24e1e4a)








