# RFM Analysis Report
## Online Retail Transactions Dataset

**Dataset Source:** [Kaggle - Online Retail Transactions Dataset](https://www.kaggle.com/datasets/abhishekrp1517/online-retail-transactions-dataset)

---

## Executive Summary

This report presents a comprehensive RFM (Recency, Frequency, Monetary) analysis of customer behavior in an online retail dataset. The analysis segments customers into distinct groups based on their purchasing patterns, enabling targeted marketing strategies and customer relationship management.

**Key Highlights:**
- **Total Transactions:** 541,909 records (after data cleaning)
- **Customer Segments Identified:** Loyal Customers, Potential Loyal Customers, Cost-Conscious Customers, One-Time Purchasers, High-Value Customers, and Inactive Customers
- **Top Customer Segment:** Loyal customers with high frequency, monetary value, and recent purchases
- **Average Purchase Interval:** Loyal customers purchase approximately every 1.5 days

---

## 1. Methodology

### 1.1 Data Preparation

The analysis began with comprehensive data cleaning:
- **Initial Dataset:** 541,909 rows with 8 columns
- **Missing Values:** Removed rows with missing descriptions (typically had zero unit price)
- **Duplicates:** Removed 5,268 duplicate rows
- **Data Quality:** Excluded transactions with zero unit price and bad debt invoices (starting with 'A')
- **Customer ID Handling:** Missing CustomerIDs were temporarily assigned InvoiceNo values

### 1.2 RFM Framework

The RFM analysis uses three key metrics, each divided into 5 levels:

#### **RVC (Recency Value per Customer)**
- Measures days since last purchase
- **Level 1:** 1-75 days (most recent)
- **Level 2:** 76-150 days
- **Level 3:** 151-223 days
- **Level 4:** 225-299 days
- **Level 5:** 301-374 days (least recent)

#### **FVC (Frequency Value per Customer)**
- Measures number of unique invoices per customer
- **Level 1:** 1-41 invoices
- **Level 2:** 44-73 invoices
- **Level 3:** 86-124 invoices
- **Level 4:** Not present in dataset
- **Level 5:** 201-209 invoices (most frequent)

#### **MVC (Monetary Value per Customer)**
- Measures total expenditure per customer
- **Level 1:** £0.42 - £54,534.14
- **Level 2:** £56,252.72 - £91,062.38
- **Level 3:** £117,210.08 - £143,711.17
- **Level 4:** £168,472.50 - £194,390.79
- **Level 5:** £259,657.30 - £280,206.02 (highest value)

#### **RFM Score**
- Combined score created by concatenating RVC Level, FVC Level, and MVC Level
- Example: RFM 153 = RVC Level 1, FVC Level 5, MVC Level 3

---

## 2. Customer Segmentation Analysis

### 2.1 Loyal Customers

**Definition:** Customers with:
- FVC Level 3 or 5 (high frequency)
- MVC Level 3, 4, or 5 (high monetary value)
- RVC Level 1 or 2 (recent purchases)

**Key Statistics:**
- **Number of Unique Customers:** 1 customer (CustomerID: 14911.0)
- **Total Transactions:** 5,670 transactions
- **Unique Invoices:** 201 invoices
- **Average Time Between Purchases:** 1.47 days
- **Top Products:**
  - CARRIAGE (84 purchases)
  - REGENCY CAKESTAND 3 TIER (49 purchases)
  - WHITE HANGING HEART T-LIGHT HOLDER (33 purchases)
  - ROSES REGENCY TEACUP AND SAUCER (33 purchases)
  - GREEN REGENCY TEACUP AND SAUCER (28 purchases)

**Insights:**
- This customer demonstrates exceptional loyalty with purchases nearly every 1.5 days
- Strong preference for home decor and kitchenware items
- Consistent purchasing pattern suggests high engagement

### 2.2 Potential Loyal Customers

**Definition:** Customers with:
- FVC Level 1, 2, or 3 (moderate to high frequency)
- MVC Level 3, 4, or 5 (high monetary value)
- RVC Level 1 or 2 (recent purchases)
- FVC > 1 (not one-time purchasers)

**Key Statistics:**
- **Number of Unique Customers:** 6 customers
- **Average Time Between Purchases:** 4.6-204 days (varies significantly)
- **Notable Customer:** CustomerID 16446.0
  - Only 2 invoices but high value (£168,472.50 total)
  - 204 days between purchases
  - Large bulk purchase of "PAPER CRAFT, LITTLE BIRDIE" (80,995 units)

**Insights:**
- These customers show high value potential but need engagement strategies
- Mixed purchasing patterns suggest opportunity for frequency improvement
- Some customers make infrequent but very large purchases

### 2.3 Cost-Conscious Customers

**Definition:** Customers with:
- FVC Level 3 or 5 (high frequency)
- MVC Level 1, 2, or 3 (low to moderate monetary value)
- RVC Level 1 or 2 (recent purchases)

**Key Statistics:**
- **Number of Unique Customers:** 7 customers
- **Average Time Between Purchases:** 1.4-4.1 days
- **Average Expenditure:** Lower than high-value segments
- **Top Products:**
  - EDWARDIAN PARASOL NATURAL (30 purchases)
  - EDWARDIAN PARASOL BLACK (27 purchases)
  - GLITTER HANGING BUTTERFLY STRING (24 purchases)

**Insights:**
- High purchase frequency but lower transaction values
- Regular, consistent purchasers who may respond to volume discounts
- Opportunity for upselling strategies

### 2.4 One-Time Purchasers

**Definition:** Customers with FVC = 1 (only one invoice)

**Key Statistics:**
- **Number of Transactions:** 165,083 transactions
- **Average Recency:** 169.6 days since purchase
- **Average Expenditure:** £14.28 per transaction
- **Date Range:** December 2010 to December 2011

**Insights:**
- Large segment representing significant portion of customer base
- Low average spend suggests trial purchases
- High recency indicates many haven't returned
- **Recommendation:** Re-engagement campaigns needed

### 2.5 High-Value Customers

**Definition:** Customers with MVC Level 5 (highest monetary value)

**Key Statistics:**
- **Average Invoice Value:** Varies significantly (£4.44 - £942.17)
- **Top Customers:**
  - CustomerID 14646.0: Total MVC £280,206.02
  - CustomerID 18102.0: Multiple high-value transactions
- **Purchase Patterns:** Mix of frequent small purchases and occasional large bulk orders

**Insights:**
- Small but critical customer segment
- Some customers make very large bulk purchases
- Requires personalized account management

### 2.6 Inactive Customers

**Definition:** Customers with RVC Level 4 or 5 (225-374 days since last purchase)

**Key Statistics:**
- **Recency Range:** 225-374 days since last purchase
- **Distribution:** Spread across all MVC and FVC levels

**Insights:**
- Customers who haven't purchased in 7-12 months
- Risk of churn is high
- **Recommendation:** Win-back campaigns with special offers

### 2.7 Recent Customers

**Definition:** Customers with RVC Level 1 (1-75 days since last purchase)

**Key Statistics:**
- **Total Transactions:** 377,027 transactions
- **Distribution by MVC Level:**
  - MVC Level 1: 351,202 transactions (93.2%)
  - MVC Level 2: 11,540 transactions (3.1%)
  - MVC Level 3: 7,779 transactions (2.1%)
  - MVC Level 5: 2,507 transactions (0.7%)
  - MVC Level 4: 339 transactions (0.1%)

**Insights:**
- Large segment of recently active customers
- Most are low-value customers (MVC Level 1)
- Opportunity to increase value through cross-selling and upselling

---

## 3. Repeated Purchasers Analysis

### 3.1 Frequency Distribution

**Customers with FVC > 1:**
- **FVC Level 1:** 323,934 transactions
- **FVC Level 3:** 14,838 transactions
- **FVC Level 2:** 10,940 transactions
- **FVC Level 5:** 10,082 transactions

### 3.2 Average Expenditure

- **Overall Average for Repeated Purchasers:** £57.47 per transaction
- **By FVC Level:**
  - FVC Level 1: £20.33
  - FVC Level 2: £121.32
  - FVC Level 3: £12.35
  - FVC Level 5: £17.53

**Insights:**
- FVC Level 2 customers have the highest average expenditure
- FVC Level 3 customers purchase frequently but at lower values
- Opportunity to increase transaction values for frequent purchasers

### 3.3 Top Repeated Purchase Products

Most frequently repurchased items include:
- Home decor items
- Kitchenware
- Gift items
- Seasonal products

---

## 4. Basket Analysis & Cross-Selling Opportunities

### 4.1 Product Clustering

Products were clustered into 300 categories using AI-based semantic analysis (sentence transformers). This enables identification of complementary product groups.

### 4.2 Cross-Sell Patterns for Loyal Customers

**Top Cross-Sell Cluster Pairs:**
- Clusters (13, 21): 33 times
- Clusters (13, 47): 31 times
- Clusters (13, 114): 31 times
- Clusters (47, 114): 31 times
- Clusters (21, 31): 31 times

**Top Cross-Sell Cluster Trios:**
- Clusters (13, 47, 114): 28 times
- Clusters (13, 114, 154): 24 times
- Clusters (47, 114, 154): 23 times

**Top Cross-Sell Cluster Quartets:**
- Clusters (13, 47, 114, 154): 22 times

### 4.3 Cross-Sell Patterns for Cost-Conscious Customers

**Top Cross-Sell Cluster Pairs:**
- Clusters (21, 178): 95 times
- Clusters (43, 178): 87 times
- Clusters (16, 178): 86 times
- Clusters (178, 200): 81 times

**Insights:**
- Strong product associations identified
- Opportunities for bundle offers and recommendations
- Different patterns across customer segments suggest personalized approaches

---

## 5. Key Findings

### 5.1 Customer Behavior Patterns

1. **Loyalty Concentration:** Only 1 customer meets the strict "Loyal Customer" criteria, indicating opportunity to develop more loyal relationships
2. **One-Time Purchaser Challenge:** Large segment of one-time purchasers (165K+ transactions) with average 169 days since last purchase
3. **High-Value Customers:** Small but critical segment requiring personalized attention
4. **Purchase Frequency:** Most loyal customers purchase every 1-4 days, showing high engagement

### 5.2 Revenue Insights

1. **Average Customer Spend:**
   - Overall average: £57.47 (repeated purchasers)
   - One-time purchasers: £14.28
   - High-value customers: Variable, up to £942 per invoice

2. **Value Distribution:**
   - Most customers (93%) in recent segment are low-value (MVC Level 1)
   - High-value customers (MVC Level 5) represent small but significant revenue

### 5.3 Product Preferences

1. **Loyal Customers:** Prefer home decor, kitchenware, and gift items
2. **Cost-Conscious:** Focus on practical items like parasols and decorative strings
3. **High-Value:** Mix of bulk purchases and regular items

---

## 6. Recommendations

### 6.1 For Loyal Customers (RFM 153, etc.)

**Actions:**
- **VIP Program:** Create exclusive benefits and early access to new products
- **Personalized Recommendations:** Use basket analysis to suggest complementary products
- **Loyalty Rewards:** Implement points-based system for continued engagement
- **Priority Support:** Dedicated customer service channel

### 6.2 For Potential Loyal Customers

**Actions:**
- **Re-engagement Campaigns:** Targeted emails with personalized product recommendations
- **Frequency Incentives:** "Buy 3, get 1 free" or similar programs
- **Cross-Sell Opportunities:** Recommend products based on basket analysis patterns
- **Special Offers:** Time-limited discounts to encourage repeat purchases

### 6.3 For Cost-Conscious Customers

**Actions:**
- **Volume Discounts:** Bulk purchase incentives
- **Bundle Offers:** Create product bundles based on cross-sell patterns
- **Loyalty Points:** Reward frequent purchases even at lower values
- **Upselling:** Gently introduce higher-value alternatives

### 6.4 For One-Time Purchasers

**Actions:**
- **Win-Back Campaigns:** Special offers for returning customers
- **Follow-Up Communications:** Post-purchase surveys and product recommendations
- **Reactivation Offers:** Discount codes for customers inactive >90 days
- **Referral Programs:** Incentivize bringing in new customers

### 6.5 For Inactive Customers

**Actions:**
- **Win-Back Emails:** "We miss you" campaigns with special discounts
- **Survey:** Understand why they stopped purchasing
- **New Product Announcements:** Re-engage with exciting new offerings
- **Exit Interviews:** Learn from churned customers

### 6.6 For High-Value Customers

**Actions:**
- **Account Management:** Dedicated relationship manager for top customers
- **Custom Pricing:** Negotiated rates for bulk purchases
- **Exclusive Access:** Early access to sales and new products
- **Personalized Service:** Tailored shopping experiences

### 6.7 General Recommendations

1. **Segmentation Strategy:** Implement automated RFM scoring for ongoing customer classification
2. **Personalization:** Use basket analysis to power recommendation engines
3. **Communication:** Tailor messaging and offers based on RFM segments
4. **Monitoring:** Track segment migration over time
5. **Testing:** A/B test different strategies for each segment

---

## 7. Implementation Roadmap

### Phase 1: Immediate Actions (0-1 month)
- Set up automated RFM scoring system
- Launch win-back campaigns for inactive customers
- Create VIP program for loyal customers

### Phase 2: Short-term (1-3 months)
- Implement recommendation engine based on basket analysis
- Develop segment-specific marketing campaigns
- Create loyalty rewards program

### Phase 3: Long-term (3-6 months)
- Advanced personalization using AI/ML
- Predictive analytics for customer lifetime value
- Dynamic pricing strategies by segment

---

## 8. Conclusion

The RFM analysis reveals distinct customer segments with varying needs and behaviors. The key opportunity lies in:
1. **Converting one-time purchasers** into repeat customers
2. **Nurturing potential loyal customers** to increase frequency
3. **Retaining and growing high-value customers**
4. **Re-engaging inactive customers**

By implementing targeted strategies for each segment, the business can improve customer lifetime value, increase retention, and drive revenue growth.

The analysis demonstrates that a small number of highly engaged customers drive significant value, while a large base of one-time or inactive customers represents untapped potential. Strategic focus on segment-specific initiatives will yield the highest return on investment.

---

**Report Generated:** Based on analysis from `mkt analysis (2).ipynb`  
**Dataset:** Online Retail Transactions Dataset (Kaggle)  
**Analysis Period:** December 2010 - December 2011

