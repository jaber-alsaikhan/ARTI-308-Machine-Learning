# ARTI-308-Machine-Learning
Machine Learning
Credit Card Customer Segmentation Project
In this project, you will use K-Means clustering to segment credit card customers based on their usage behavior. This is an unsupervised learning problem because the dataset does not contain a target label for customer groups.

You will use the CC_GENERAL.csv dataset.


1.  **Why is this an unsupervised learning problem?**
    This is an unsupervised learning problem because the dataset does not contain a target variable or labels indicating predefined customer segments. The goal is to discover hidden patterns and groupings within the data without prior knowledge of these groups.

2.  **Why did we remove the `CUST_ID` column?**
    The `CUST_ID` column was removed because it is a unique identifier for each customer and does not contain any behavioral information useful for clustering. Including it would add noise and not contribute to identifying customer segments.

3.  **Which columns had missing values?**
    The columns `CREDIT_LIMIT` and `MINIMUM_PAYMENTS` had missing values.

4.  **How did you handle the missing values?**
    Missing values in `CREDIT_LIMIT` and `MINIMUM_PAYMENTS` were handled by imputing them with the mean value of their respective columns.

5.  **Why is scaling important before applying K-Means?**
    Scaling is important for K-Means because it is a distance-based algorithm. Features with larger numerical ranges would disproportionately influence the distance calculations and, consequently, the clustering results. Scaling ensures that all features contribute equally to the distance metric.

6.  **Which K value did you choose? Explain your answer using the elbow method and silhouette score.**
    I chose **K = 3**. 
    *   **Elbow Method:** While not extremely sharp, the elbow plot showed a noticeable bend around K=3, suggesting a point of diminishing returns in reducing inertia. 
    *   **Silhouette Score:** The silhouette score for K=3 was the highest at approximately 0.25, indicating the best-defined and most separated clusters among the tested K values (2 to 10).

7.  **Based on the cluster summary table, describe each customer segment in your own words.**
    *   **Cluster 0:** These customers tend to have a **high balance** but relatively **low purchases** (especially installments). They show the highest `CASH_ADVANCE` and `CASH_ADVANCE_TRX` (transactions) and the lowest `PRC_FULL_PAYMENT`. This segment likely represents **'Cash Advance Users'** who carry high debt and rely on cash advances, paying minimum amounts.
    *   **Cluster 1:** This segment is characterized by **very high `PURCHASES`**, both one-off and installment, and high `PURCHASES_FREQUENCY` and `PURCHASES_TRX`. Their `BALANCE` is moderate, and `CASH_ADVANCE` is relatively low. They also have a higher `PRC_FULL_PAYMENT` compared to Cluster 0. This cluster represents **'High Spenders/Purchasers'** who actively use their credit cards for various purchases.
    *   **Cluster 2:** This is the largest cluster, characterized by **lower `BALANCE`**, `PURCHASES`, and `CASH_ADVANCE` compared to the other two clusters. They have moderate `PURCHASES_FREQUENCY` and `CASH_ADVANCE_FREQUENCY`, and their `CREDIT_LIMIT` is the lowest on average. This segment might represent **'Low Usage Customers'** or 'Balanced Users' who use their credit cards sparingly and manage their payments well.

8.  **Which cluster may represent high-value customers?**
    **Cluster 1** likely represents high-value customers. They have significantly higher purchase activity (`PURCHASES`, `ONEOFF_PURCHASES`, `INSTALLMENTS_PURCHASES`) and higher `CREDIT_LIMIT` on average, indicating a strong engagement with credit card spending.

9.  **Which cluster may represent customers who rely more on cash advance?**
    **Cluster 0** clearly represents customers who rely more on cash advance. They have the highest mean `CASH_ADVANCE` and `CASH_ADVANCE_TRX`, and the lowest `PRC_FULL_PAYMENT`, suggesting they frequently withdraw cash and struggle to pay their full balance.

10. **How can a company use these clusters for marketing strategy?**
    *   **Cluster 0 (Cash Advance Users):** Offer balance transfer options with lower interest rates, financial literacy resources, or targeted campaigns to encourage shifting from cash advances to purchases.
    *   **Cluster 1 (High Spenders/Purchasers):** Reward loyalty with premium benefits, higher credit limits, exclusive offers, or tiered rewards programs to encourage continued high spending and retention.
    *   **Cluster 2 (Low Usage Customers):** Implement campaigns to encourage more frequent card usage, personalized offers based on potential spending habits, or educational content about the benefits of credit card usage (e.g., rewards, purchase protection).
