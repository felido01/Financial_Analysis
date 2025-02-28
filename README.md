## FINANCIAL ANALYSIS VOLUNTEERING PROJECT
### FELIX IDOWU
---
### OBJECTIVES
#### Your task is to combine and analyze the two datasets to answer the following questions:
1. #### Customer Demographics: What is the age distribution, gender ratio, and income distribution of the customers?
2. #### Credit Card Ownership: How many credit cards does the average user have? Identify customers with multiple credit cards.
3. #### Credit Risk Analysis: Identify customers with high total debt compared to their yearly income.
4. #### Insights for Marketing: Provide insights on which group of customers might be ideal for targeted marketing campaigns (based on credit scores, income, and card types).
---
### PROJECT OVERVIEW
#### This project analyzes financial data to gain insights into customer financial behavior and card usage. The findings help develop targeted marketing campaign strategies best suited each customer segment.
---
### DATASET
##### There are two datasets for this project [User_data](https://docs.google.com/spreadsheets/d/1baYcMQr-KCb9FwrY31mQC5ya8FblMHbY/edit?usp=sharing&ouid=102538990223331200198&rtpof=true&sd=true) and [Card_data](https://docs.google.com/spreadsheets/d/1azUzYFNynwX3KcyOT1sCXYD3BVz36eBd/edit?usp=sharing&ouid=102538990223331200198&rtpof=true&sd=true) Click the blue text to view Dataset
#### Users_data: 
##### This contains demographic and financial information about the users.
  ##### Columns:
* ##### main_id: Unique user identifier (foreign key for client_id in cards_data)
* ##### current_age, retirement_age
* ##### gender
* ##### address, latitude, longitude
* ##### per_capita_income, yearly_income, total_debt, credit_score
* ##### num_credit_cards: Number of credit cards the user owns

#### Cards_data:
##### Contains details about each credit card associated with a user.
##### Columns:
* ##### card_id: Unique identifier for each card
* ##### client_id: Foreign key linked to main_id in users_data
* ##### card_brand, card_type (e.g., Debit, Credit, Prepaid)
* ##### expires, acct_open_date
* ##### credit_limit, year_pin_last_changed
---
### ANALYSIS STEP
#### Data Preparation
* ##### There two data set with a column in common(main_id and client_id). I Merged the two data using .merge() function
#### Data Cleaning
* ##### The Merged data resulted in duplicated main_id but distinct card_id.
* ##### Checked for overall duplicated values and duplicates values in the card_id alone
###### Note: The scope of this merged dataset is that the data set has duplicated customer with different card_id(Same customer with multiple cards)
* ##### Checked for null values. Fortunately there was none
* ##### Something unusual was noticed. Some Customer had a yearly income of less than 5( it could be an outlier)
* ##### I dropped The Outlier
#### Data Analysis:
##### From my analysis, I was able to uncover the following insight
* ##### Gender ratio: According to the Objectives, The Data about the customer gender was needed. To Achieve this, The dataset was splited  into two sector(Male and Female). The Rows of each sector were counted using .shape function, Alternate method could be .count() function . The male to female ratio respectively was gotten to be 2996 : 3133. We can conclude from here that female customers area little more than the male
  
* ##### Age Distribution: Since we want to deal with  customer unique details rather than card details, we need to ensure that each customer is uniquely represented. To achieve this, we will remove duplicate records based on a unique customer identifier, Once we have a cleaned dataset, we will analyze the age distribution to better understand the range of ages among our customers. I analyzed the age distribution using the .min() and .max() functions. The results showed that our customers range in age from 18 to 101. using .pivot_table() function, i got the count of each age.The highest number of customers are aged 18, while the lowest are aged 101

* ##### Income Distribution: From my analysis, we have a very low number of customers with a high yearly income, specifically those earning $100,000 and above. The majority of customers fall into the lower income category, making up the largest portion of the dataset. When comparing this with credit scores, most customers with high yearly income have a fair credit score. Additionally, since low-income customers dominate the data, they also account for the highest number of bad, fair, and good credit scores.

* ##### Credit Risk Analysis: To assess credit risk, we use the **Debt-to-Income Ratio (DTI)** to understand a borrower's ability to manage debt compared to their income. A **higher DTI** means greater financial strain and a higher risk of default, A **lower DTI** indicates better financial stability and lower credit risk. (Note that: Lenders rely on this ratio to determine loan eligibility, set interest rates, and evaluate the likelihood of repayment). The **DTI** in this analysis ranged from a minimum of **0.13%** to a maximum of **497.86%**. A **DTI greater than 100%** means that a person’s debt payments exceed their income. This is a sign of **high credit risk**, as they may need to rely on savings or new debt to meet financial obligations. Lenders may see such borrowers as risky and could: **Deny credit**, **Offer loans with higher interest rates**, **Require collateral** to reduce their risk. A total of 1,340 customers are least likely to repay their debt due to a high debt-to-income (DTI) ratio

* ##### Insights for Marketing: From the Analysis, The majority of customers (4,107 general customers) require broad engagement strategies like loyalty programs, personalized recommendations, and awareness campaigns to maintain their interest. 1,962 growth potential customers present an opportunity for targeted upselling, cross-selling, and exclusive offers to encourage higher spending and engagement. Although high-value customers are few (60), they are the most profitable and should receive personalized attention through VIP programs, premium services, and special perks to ensure retention.

* ##### From My Analysis, There are 535 Customers with more than one credit card 
---

#### Conclusion: After indepth Analysis, I was able to uncover Insights on customer data and give recommendation for Marketing Strategies (based on credit scores, income, and card types). This was all done in the Data Analysis Stage of my Project
