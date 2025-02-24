## FINANCIAL ANALYSIS VOLUNTEERING PROJECT
### FELIX IDOWU
---
### OBJECTIVES
#### Your task is to combine and analyze the two datasets to answer the following questions:
1. #### Customer Demographics: What is the age distribution, gender ratio, and income distribution of the customers?
2. #### Credit Card Ownership: How many credit cards does the average user have? Identify customers with multiple credit cards.
3. #### Credit Risk Analysis: Identify customers with high total debt compared to their yearly income.
4. #### Card Expiration Analysis: How many cards will expire within the next year?
5. #### Insights for Marketing: Provide insights on which group of customers might be ideal for targeted marketing campaigns (based on credit scores, income, and card types).
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
##### Data Preparation
