# Customer Segmentation Using RFM Analysis

## Project Overview

This project performs customer segmentation using the RFM (Recency, Frequency, Monetary) framework.  
The objective is to analyze customer purchasing behavior and classify customers into different loyalty categories. This helps businesses improve targeted marketing, retention and engagement strategies.

---

## Dataset Description

The dataset consists of customer transaction records. Each row represents a single purchase.

Key columns include:
- CustomerID – Unique ID of the customer  
- Item Code – Product identifier  
- InvoiceNo – Invoice or order number  
- Date of purchase – Date of the transaction  
- Time – Time of the transaction  
- Quantity – Units purchased  
- Price per Unit – Cost of one unit  
- Price – Total amount spent  
- Shipping Location – Delivery location  
- Cancelled_status, Reason of return, Sold as set – Indicators for returns/cancellations  

Columns used for RFM:
- CustomerID  
- InvoiceNo  
- Date of purchase  
- Price  

---

## What is RFM?

**RFM** stands for **Recency, Frequency, Monetary**, a technique used to evaluate customer value.

### Recency  
How recently a customer made a purchase.  
More recent = more active customer.

### Frequency  
How often a customer purchased.  
Higher frequency = more loyal.

### Monetary  
How much money the customer has spent.  
Higher monetary value = more valuable.

---

## Methodology

### 1. Data Preparation
- Converted purchase dates into datetime format  
- Removed unnecessary or null fields  
- Selected required columns for analysis  

### 2. RFM Metric Calculation
- **Recency:** Days since the customer’s last purchase  
- **Frequency:** Number of invoices per customer  
- **Monetary:** Total spending per customer  

### 3. Quartile Segmentation
- Customers divided into groups using quartiles for Recency, Frequency, Monetary  
- Lower Recency is better  
- Higher Frequency and Monetary are better  

### 4. RFM Scoring
Each customer receives:
- R score (1–4)  
- F score (1–4)  
- M score (1–4)

Where:
- **1 = Best customers**
- **4 = Least valuable customers**

### 5. Loyalty Score
R, F, M scores are summed to calculate the **Loyalty Score**.

### 6. Loyalty Badge Assignment
Customers are grouped into four categories:
- Platinum  
- Gold  
- Silver  
- Bronze  

These badges help identify customer value tiers for strategic business decisions.

---

## Final Output
The final output includes:
- CustomerID  
- Recency  
- Frequency  
- Monetary  
- Loyalty Badge (Platinum / Gold / Silver / Bronze)

This helps identify:
- High-value loyal customers  
- At-risk customers  
- Customers needing re-engagement  
- Low-value customers  

---

## Tech Stack
- Python  
- Pandas  
- NumPy  

---

## Use Cases
- Targeted marketing  
- Customer retention strategies  
- Personalized recommendations  
- Revenue and churn analysis  
- Loyalty program design  

 

