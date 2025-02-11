# churn-prediction (model to deployment)
# Problem statement :
1st_Choice_Bank has been observing a lot of customers closing their accounts or switching to competitor banks over the past couple of quarters. As such, this has caused a huge dent in the quarterly revenues and might drastically affect annual revenues for the ongoing financial year, causing stocks to plunge and market cap to reduce by X %. A team of business, product, engineering and data science folks have been put together to arrest this slide.

# Objective: 
Can we build a model to predict, with reasonable accuracy, the customers who will churn in the near future? Being able to estimate when they are going to churn accurately will be a bonus

# Definition of churn: 
A customer having closed all their active accounts with the bank is said to have churned. Churn can be defined in other ways as well, based on the context of the problem. A customer not transacting for 6 months or 1 year can also be defined as having churned, based on the business requirements.

# From a Biz team/Product Manager's perspective :

(1) Business goal : Arrest slide in revenues or loss of active bank customers

(2) Identify data source : Transactional systems, event-based logs, Data warehouse (MySQL DBs, Redshift/AWS), Data Lakes, NoSQL DBs

(3) Audit for data quality : De-duplication of events/transactions, Complete or partial absence of data for chunks of time in between, Obscuring PII (personal identifiable information) data

(4) Define business and data-related metrics : Tracking of these metrics over time, probably through some intuitive visualizations

(i) Business metrics : Churn rate (month-on-month, weekly/quarterly), Trend of avg. number of products per customer, 
    %age of dormant customers, Other such descriptive metrics

(ii) Data-related metrics : F1-score, Recall, Precision
     Recall = TP/(TP + FN) 
     Precision = TP/(TP + FP)
     F1-score = Harmonic mean of Recall and Precision
     where, TP = True Positive, FP = False Positive and FN = False Negative
(5) Prediction model output format : Since this is not going to be an online model, it doesn't require deployment. Instead, periodic (monthly/quarterly) model runs could be made and the list of customers, along with their propensity to churn shared with the business (Sales/Marketing) or Product team

(6) Action to be taken based on model's output/insights : Based on the output obtained from the Data Science team as above, various business interventions can be made to save the customer from getting churned. Customer-centric bank offers, getting in touch with customers to address grievances etc. Here, also Data Science team can also help with basic EDA to highlight different customer groups/segments and the appropriate intervention to be applied against them

# Collaboration with Engineering and DevOps :

(1) Application deployment on production servers (In the context of this problem statement, not required)

(2) [DevOps] Monitoring the scale aspects of model performance over time (Again, not required, in this case)


# How to set the target/goal for the metrics?
Data science-related metrics :
Recall : >70%
Precision : >70%
F1-score : >70%
# Business metrics : 
Usually, it's top down. But a good practice is to consider it to make atleast half the impact of the data science metric. For e.g., If we take Recall target as 70% which means correctly identifying 70% of customers who's going to churn in the near future, we can expect that due to business intervention (offers, getting in touch with customers etc.), 50% of the customers can be saved from being churned, which means atleast a 35% improvement in Churn Rate
